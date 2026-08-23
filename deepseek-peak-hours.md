# DeepSeek peak and off-peak hours — weekdays only, weekends are off-peak all day

<div id="ds-now" data-windows="01:00-04:00,06:00-10:00" data-tz="Asia/Shanghai" data-clock="Beijing time" data-weekend-from="2026-08-22T16:00:00Z" style="border:1px solid currentColor;border-radius:6px;padding:.75em 1em;margin:1em 0">
<strong id="ds-now-line">Peak is 09:00–12:00 and 14:00–18:00 Beijing time, Monday to Friday. Off-peak — everything else, weekends included — is half price.</strong>
</div>

<script>
(function () {
  var el = document.getElementById("ds-now");
  if (!el || !window.Intl) return;
  var line = document.getElementById("ds-now-line");
  var tz = el.getAttribute("data-tz");
  var clock = el.getAttribute("data-clock");
  var from = Date.parse(el.getAttribute("data-weekend-from"));
  var wins = el.getAttribute("data-windows").split(",").map(function (w) {
    return w.split("-").map(function (hm) {
      var p = hm.split(":");
      return (+p[0]) * 60 + (+p[1]);
    });
  });
  var SHORT = ["Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"];
  var LONG = ["Sunday", "Monday", "Tuesday", "Wednesday", "Thursday",
              "Friday", "Saturday"];

  function vendorParts(d) {
    var out = {};
    new Intl.DateTimeFormat("en-US", {
      timeZone: tz, weekday: "short", hour: "2-digit", minute: "2-digit",
      hour12: false
    }).formatToParts(d).forEach(function (p) { out[p.type] = p.value; });
    return out;
  }

  function isPeak(d) {
    var day = SHORT.indexOf(vendorParts(d).weekday);
    if (d.getTime() >= from && (day === 0 || day === 6)) return false;
    var m = d.getUTCHours() * 60 + d.getUTCMinutes();
    for (var i = 0; i < wins.length; i++) {
      if (m >= wins[i][0] && m < wins[i][1]) return true;
    }
    return false;
  }

  function nextChange(d) {
    var cur = isPeak(d);
    for (var i = 0; i <= 8; i++) {
      for (var j = 0; j < wins.length; j++) {
        for (var k = 0; k < 2; k++) {
          var t = new Date(Date.UTC(d.getUTCFullYear(), d.getUTCMonth(),
                                    d.getUTCDate() + i, 0, wins[j][k]));
          if (t <= d) continue;
          if (isPeak(t) !== cur) return t;
        }
      }
    }
    return null;
  }

  function render() {
    var now = new Date();
    var peak = isPeak(now);
    var txt = peak
      ? "Right now it is peak \u2014 full price."
      : "Right now it is off-peak \u2014 half price.";
    var t = nextChange(now);
    if (t) {
      var mins = Math.round((t - now) / 60000);
      var h = Math.floor(mins / 60);
      var p = vendorParts(t);
      txt += " " + (peak ? "Off-peak starts " : "Peak resumes ")
        + LONG[SHORT.indexOf(p.weekday)] + " " + p.hour + ":" + p.minute
        + " " + clock + ", in " + (h ? h + " h " : "") + (mins % 60) + " min.";
    }
    line.textContent = txt;
  }

  render();
  setInterval(render, 30000);
}());
</script>

Peak hours are **09:00–12:00 and 14:00–18:00 Beijing time, Monday to Friday** — that is `01:00-04:00` UTC and `06:00-10:00` UTC. Every other hour is off-peak, and **off-peak is half of peak**, on every rate: cache hit, cache miss and output.

Since **00:00 on 2026-08-23 Asia/Shanghai** the whole weekend is off-peak as well — all day Saturday and all day Sunday. That weekend is bounded on the vendor's own clock (`Asia/Shanghai`), not in UTC: it runs from **16:00 UTC Friday** to **16:00 UTC Sunday**.

Read off DeepSeek's own pricing page on **2026-08-23**: <https://api-docs.deepseek.com/quick_start/pricing/>.

## The rates

| Model | | Cache hit | Cache miss | Output |
| --- | --- | --- | --- | --- |
| `deepseek-v4-pro` | peak | $0.044 | $1.32 | $3.96 |
| `deepseek-v4-pro` | off-peak | $0.022 | $0.66 | $1.98 |
| `deepseek-v4-flash` | peak | $0.014 | $0.44 | $1.32 |
| `deepseek-v4-flash` | off-peak | $0.007 | $0.22 | $0.66 |
| `deepseek-v4-flash-vision-exp` | peak | $0.014 | $0.44 | $1.32 |
| `deepseek-v4-flash-vision-exp` | off-peak | $0.007 | $0.22 | $0.66 |

Per million tokens, US dollars.

## Which side of the rate card am I on right now?

[The calculator](https://xyzs996.github.io/llm-cost-calculator/) answers that for the instant you open it — it resolves this clock, applies the long-context price cliff, and takes your own cache-hit share, so what it gives back is a bill rather than a rate. One page, nothing to install, no account.

## The English pricing page drops a timezone

The two language versions of DeepSeek's footnote do not say the same thing. In English:

> Peak hours are 01:00 - 04:00 and 06:00 - 10:00 UTC, Monday through Friday (all other hours are off-peak).

In Chinese:

> 高峰时段为北京时间周一至周五 9:00 - 12:00、14:00 - 18:00（其余为空闲时段）。

The hours agree. The calendar does not: the Chinese sentence puts the weekday in Beijing time, and the English one attaches `UTC` to the hours and leaves *Monday through Friday* unqualified. Read in English it says UTC weekdays, and the two readings differ over 16:00–24:00 UTC on Friday and on Sunday — sixteen hours a week.

Worse, nothing catches it. Both peak windows sit clear of 16:00–24:00 UTC, so the two calendars produce **identical prices at all 168 hours** of the current schedule. Code written from the English sentence is wrong in a way no test against the published windows can show — until a window moves past 16:00 UTC, and then it is wrong about money.

A dated table that pins those edges, public domain: <https://github.com/xyzs996/deepseek-peak-hours>. The two vectors that discriminate are `2026-08-28T16:30:00Z` and `2026-08-30T16:30:00Z`.

## What 46 implementations actually did with this rule

Between 2026-08-18 and 2026-08-23 I read the pricing code of every public project I could find that implements this schedule — dashboards, cost meters, routers, IDE plugins, billing libraries — and filed **53 reports across 46 repositories**. Nine are fixed already. The repositories run from 15 stars to 53,665; the median is 55, so this is not a big-project problem or a small-project problem.

They failed in four distinct ways, and they are worth knowing because the first one is not the interesting one.

**1. No weekday axis at all.** The common case by a wide margin: a function that reads the hour and nothing else, so all 14 weekend hours inside the windows bill at **2×**. Usually three or four lines to fix.

**2. The weekday read on the wrong clock.** Fixing (1) with `getUTCDay()` or `.weekday()` in UTC is correct *today* and silently wrong later, for the reason in the section above. It cannot be caught by any test written against the published windows, which means it will be found by a bill.

**3. The rule applied retroactively.** The weekend rule took effect 2026-08-23. Halve every past weekend along with it and historical usage is under-reported by half — the opposite sign from (1), and much harder to notice, because a bill that looks cheap does not generate a support ticket.

**4. Unknown models falling back to the priciest row.** Several projects resolve an unrecognised model id to a default that happens to be the expensive tier. `deepseek-v4-flash-vision-exp` shipped 2026-08-21 at flash rates; falling back to v4-pro is exactly **3×** on all three numbers, and **6×** stacked on top of (1) on a weekend.

One finding did not fit any of the four. In one project the regression test for peak pricing pinned both of its instants to `2026-08-16` — a Sunday — and asserted the peak rate. The suite was green *because of* the bug. Worth grepping your own test dates for a weekend before trusting a green run on this.

Maintainers were, almost without exception, quick and gracious about it; several shipped the same day. If your project is on this list and I have not reached it yet, the four checks above take about five minutes against your own code.

The daily price table these rates sit in, re-read every day: [the full catalog](https://xyzs996.github.io/llm-api-pricing/prices.html).

## If you came here because the bill surprised you

A schedule is one of four things that move an agent bill, and it is the smallest of them. These are worked examples with the arithmetic shown, not buying advice:

- [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) — same task, same verdict, 6× apart. Where the 6× actually comes from. ([also on telegra.ph](https://telegra.ph/Choosing-the-Right-AI-Code-Review-Tool-A-Developers-Guide-08-21) — no account, no scripts.)
- [AI Model Costs: Beyond Per-Token Pricing](articles/ai-model-costs-beyond-per-token-pricing.md) — the cache-hit share and the context cliff both move the number further than any rate card does. ([also on telegra.ph](https://telegra.ph/Beyond-Token-Pricing-How-Indie-Devs-Should-Really-Evaluate-AI-Model-Costs-08-19))
- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md) — why vendors started charging by the clock at all, of which this page is one instance. ([also on telegra.ph](https://telegra.ph/The-Token-Cost-War-Why-Price-per-Million-Tokens-Now-Decides-the-AI-Market-08-23))

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Does your own number disagree?** [This same table has a reply box](https://github.com/xyzs996/llm-api-pricing/discussions/44) — one line answers it. No template, no title, nothing to organise first.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=deepseek-peak-hours.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=deepseek-peak-hours.md) — corrections and counter-data are the point.
