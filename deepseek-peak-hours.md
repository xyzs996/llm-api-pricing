# DeepSeek peak and off-peak hours — weekdays only, weekends are off-peak all day

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

The daily price table these rates sit in, re-read every day: [the full catalog](https://xyzs996.github.io/llm-api-pricing/prices.html).

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Does your own number disagree?** [This same table has a reply box](https://github.com/xyzs996/llm-api-pricing/discussions/44) — one line answers it. No template, no title, nothing to organise first.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=deepseek-peak-hours.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=deepseek-peak-hours.md) — corrections and counter-data are the point.
