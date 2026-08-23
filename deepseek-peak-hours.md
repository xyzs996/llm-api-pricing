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

The whole weekend is off-peak as well — all day Saturday and all day Sunday. That weekend is bounded on the vendor's own clock (`Asia/Shanghai`), not in UTC: it runs from **16:00 UTC Friday** to **16:00 UTC Sunday**.

**The page carries no effective date today.** It states the rule in the present tense in both languages, with no "in effect from" anywhere: <https://api-docs.deepseek.com/quick_start/pricing/>, re-read **2026-08-23**. It did carry one. On **2026-08-22**, hours before the rule went live, the same page ran an announcement line — *Effective 00:00 (Beijing Time) on Sunday, August 23* — and that line was pulled once the rule took effect. So **2026-08-23** Beijing time is a dated first-hand observation, not a citation you can re-check: the notice it came from is gone, and the archived copies of this page are script-only shells with none of the text in them. That distinction decides exactly one thing, below.

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

**3. The rule applied retroactively.** Halve every past weekend along with the current one and historical usage is under-reported by half — the opposite sign from (1), and much harder to notice, because a bill that looks cheap does not generate a support ticket. The patch is an effective date, and the awkward part is where you have to get it: **not from the page, which no longer carries one**, but from the announcement quoted above, which is gone. A rate table that stores only `off_peak_multiplier: 0.5` has nowhere to put that, so it silently claims the rule always held. Give the schedule an `effective_from` field, put the observed date in it, and make the repricer refuse — loudly — on any window that starts before it, rather than falling through to the current rule. The field also has to be nullable and honoured when null: the next rule change may well be one you notice a week late, and a repricer that treats "unknown start" as "since forever" gets that one wrong in the same direction.

**4. Unknown models falling back to the priciest row.** Several projects resolve an unrecognised model id to a default that happens to be the expensive tier. `deepseek-v4-flash-vision-exp` shipped 2026-08-21 at flash rates; falling back to v4-pro is exactly **3×** on all three numbers, and **6×** stacked on top of (1) on a weekend.

One finding did not fit any of the four. In one project the regression test for peak pricing pinned both of its instants to `2026-08-16` — a Sunday — and asserted the peak rate. The suite was green *because of* the bug. Worth grepping your own test dates for a weekend before trusting a green run on this.

Maintainers were, almost without exception, quick and gracious about it; several shipped the same day. If your project is on this list and I have not reached it yet, the four checks above take about five minutes against your own code.

## Nine of them, as a program you can run

Prose about other people's bugs is worth exactly as much as the reader's willingness to take your word for it, so nine of the forty-six are re-runnable. Each is a DeepSeek billing plugin whose peak predicate is a pure function of an instant plus its own window config, which is what makes this possible at all:

```
git clone https://github.com/xyzs996/deepseek-peak-hours && cd deepseek-peak-hours
node conformance/run.mjs --detail
```

No dependencies, no network, Node 16+. `conformance/adapters.mjs` holds a commit-pinned transcription of each project's own predicate — same branches, same operators, type annotations dropped where the original is TypeScript — and the runner puts 15 boundary vectors through all of them. As of **2026-08-23**:

| project | score | not run |
| --- | --- | --- |
| [dsh-cost-meter](https://github.com/Han-1413141/dsh-cost-meter) | **15/15** | — |
| [dsh-deepseek-balance](https://github.com/lancecheney/dsh-plugins) | **12/12** | 3 |
| [dsh-billing-tui](https://github.com/Ethanz11-creat/dsh-billing-tui) | 9/12 | 3 |
| [dsh-board](https://github.com/dfkai/dsh-board) | 9/12 | 3 |
| [dsh-calculator](https://github.com/bobcat848/dsh-calculator) | 9/12 | 3 |
| [dsh-gauge](https://github.com/noone89A/dsh-gauge) | 10/15 | — |
| [dsh-token-billing](https://github.com/2006spy/dsh-token-billing) | 10/15 | — |
| [dsh-token-price](https://github.com/spoon-man569/dsh-token-price) | 10/15 | — |
| [dsh-whale-meter](https://github.com/Shiye-10Pages/dsh-whale-meter) | 10/15 | — |

Every failure is the same three weekend instants, plus two more wherever the project's windows are configurable enough to be pointed at a second schedule. **`not run`** is not a failure and not a pass: it means that project's windows are written into the function, so it cannot be aimed at another schedule from the outside, and the calendar axis is untestable in it without changing the signature.

That second schedule is the part worth stealing whatever you make of the rest. Three vectors run against a synthetic schedule whose peak window is `16:00-22:00 UTC`, and it is synthetic on purpose: the real windows both close before 16:00 UTC, and `16:00-24:00 UTC` is the only stretch where the two calendars disagree about the date. So failure mode (2) above — patching the weekday in with `getUTCDay()` — passes every vector you can write against the published schedule. The synthetic one is the only way to make it fail in a test instead of in a bill.

Two of the nine pass everything they can run, and both encode something the pricing page does not say: a timezone on the weekday **and** an effective instant for the weekend rule. One spells it `WEEKEND_OFFPEAK_EFFECTIVE_AT = '2026-08-22T16:00:00Z'`, the other `weekendFrom: "2026-08-23T00:00:00+08:00"`. Same instant, two spellings, both right.

If a transcription is wrong, that is a bug in the harness and not a finding about anyone's project — say so and it gets fixed and re-run. Each of the seven has an issue open on its own tracker with its failing instants and a patch in its own language; the table follows the vectors, so a row moves when the code does.

That table is kept current in the open, one row per project, each linked to its own tracker: [the scoreboard](https://github.com/xyzs996/deepseek-peak-hours/issues/1). If you maintain one of the nine and have fixed it, or think the transcription of your code is wrong, or think a vector's expectation is wrong — that is the thread. It is the only place on this page where you can answer back, which is the point.

### The schedule itself, as a file

Everything above turns on one axis that most rate cards do not have a slot for: **which days the windows run on, and which calendar that day is counted on.** Seven of the nine had the hour arithmetic right and still billed the weekend at double, because there was nowhere in their data to put a weekday. So here is the schedule as data, public domain, re-generated with the rest of this site every day:

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/schedule.json
```

`peak_weekdays` is `[1,2,3,4,5]`, ISO-8601, Monday first. `weekday_read_on` is `calendar_timezone`, and that second field is not decoration: an implementation that reads the weekday off the UTC instant matches this file at every hour of the live schedule and is still wrong from 16:00 UTC onward the day a vendor moves a window. The two effective instants — when time-of-use billing started, and when the weekend rule started — are separate fields for the same reason: they are five days apart, and a bill re-computed across that gap with only one of them is wrong at one end. The reference implementation named in the file consumes exactly this shape, and it refuses a schedule with no `peak_weekdays` rather than assuming Monday-to-Friday on your behalf.

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
