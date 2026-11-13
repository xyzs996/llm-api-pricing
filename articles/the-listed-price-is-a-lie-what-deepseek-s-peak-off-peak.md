# The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task

![The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/89) — that copy has a reply box under it, and this one does not.*

"DeepSeek V4.1 Flash is 3 yuan per million input tokens off-peak and 9 yuan output — cheap enough to run anything." That sentence is true on the price sheet. It is also the beginning of your bill, not the end of it. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

Here is where it goes wrong. The same batch of coding tasks, run at peak versus off-peak, can cost you double, and if you stack a rate-limit window and a credit expiry on top of that, your real cost per task can double again — or worse, which means the combined effect of timing and these two additional constraints can leave you paying far more than you would ever expect from the raw task count alone. <!-- [doc_5528073dd1f937283caedd2c3baea7bc] -->

This piece does one thing: puts peak/off-peak, rate limits, and credit expiry into a single cost model and shows you the arithmetic. Where I don't have a measured number, I say so.

## The Off-Peak Price Is Real, and It Is Genuinely Cheap

Let me give the claim its due, because the cheap part is not marketing.

DeepSeek V4.1 Flash launched 2026-09-10 with an off-peak rate of 3 yuan input and 9 yuan output per million tokens. Off-peak means all day Saturday and Sunday, plus weekday 12:00–14:00 and everything after 18:00. Peak is weekday 9:00–12:00 and 14:00–18:00, billed at twice the table rate. <!-- [doc_5528073dd1f937283caedd2c3baea7bc] --> My money is on Flash.

That is not the only cheap option on the board. Xiaomi's mimo-v2.6-pro sits at 3 yuan input and 6 yuan output, and Ant Group's Ling-3.0-flash comes in at 0.12 yuan input and 0.38 yuan output — among the cheapest lightweight tiers in China right now. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] --> I'd call 0.12 yuan aggressive.

Put it in dollars and the gap is stark. DeepSeek V4 Flash's output price of 2 yuan per million tokens is roughly 1% of Claude Opus. GPT-6.1 Sol charges $2 input and $10 output per million tokens; GPT-6 Astra charges $10 and $50. <!-- [doc_7b7a9d39c7edd7e338e85692ea3084a2] --> <!-- [doc_b267a847758ffcf7d7d37525673e3bda] -->

So yes — cheap is real. The problem starts after the price sheet. And the vendors themselves acknowledge a gap between list price and what you pay: across the 2026 model batch, KV Cache compression is standard, and a cache hit can drop real cost to one-tenth of list. That is the official admission that "list price" was never the whole number. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

## Peak Hours Double Your Rate, and Your Agent Works Peak Hours

 Weekday 9:00–12:00 and 14:00–18:00 bill at double the off-peak table rate. <!-- [doc_bb4977a25d3700b71ae2e8b5eeec2fdc] -->

This is not a one-off scraping error, because the same pricing rule appears identically in market tables dated 2026-10-03, 2026-10-06, and 2026-10-12: off-peak is half of peak, and weekday 9:00–12:00 and 14:00–18:00 are 2x the table price. <!-- [doc_c6529bc86a0b8c6e764c417e8433f153] --> <!-- [doc_a2038db8e4ae681c3866106c792fca3c] -->

Now look at when you actually run a coding agent. You sit down at your desk in the morning, you point the agent at a repo, and it burns tokens from 9 to 12, while you pick it back up after lunch and it burns tokens from 14 to 18. Your agent's working hours are, almost by construction, the peak window.

DeepSeek's own messaging says V4.1 Flash is cheaper to run. Developer-side reports say actual spend did not fall — peak output stayed at 9 yuan per million tokens. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] --> Both can be true at once: the model got cheaper to serve, and your invoice stayed flat because you were never buying at the off-peak rate.

Flash pricing doesn't reach me.

Run the same batch at peak and off-peak and the price difference is a factor of two. That is not an optimization problem. It is a scheduling problem.

The schedule is where the cheap models actually pay off. DeepSeek V4.1 Flash is 3 yuan per million input tokens off-peak, 9 yuan output; double both during the weekday windows above. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> Ant Group's Ling-3.0-flash sits at 0.12 yuan in and 0.38 yuan out, the cheapest light tier in the domestic lineup. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] --> A nightly cron job that reprocesses your repo at 2 a.m. buys the same tokens at the off-peak rate instead of the peak one — and if it hits KV cache, the 2026 batch compresses on hit down to one tenth of list price. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> For an agent doing email, calendar, and research, one developer's monthly bill came to roughly $3–5 on V4 Flash against $200–260 on Opus 4.7. <!-- [doc_a7947740a61f182190750b03d21aac3c] -->

Same workload, different clock.

## A Rate-Limit Window Turns "Will Finish" Into "Won't Finish," and the Rerun Is Off the Price Sheet

Rate limiting is not one monthly number. OpenCode splits limits across 5-hour, weekly, and monthly windows, and manages them separately, while the monthly credit for a given model is retained permanently — which is not the same as unlimited requests in every window, because retention of that credit does not mean that requests are unlimited in every window. <!-- [doc_aca61ff73451846f75e14d9e94317695] -->

The consequence for batch work is concrete. Hit the 5-hour ceiling mid-batch and you have three options: wait, split the batch, or rerun. The tokens you burn on the rerun appear on no price table anywhere.

Concurrency limits cut the same way, as DeepSeek V4.1 Flash's beta API was capped at 20 concurrent requests per account, and the beta auto-expired on September 10 — leaving developers a two-day window to try it at all. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] --> That is credit expiry in its most extreme form: the model itself expires.

So the cost of an interrupted task is not the cost of the successful run. It is consumed tokens plus rerun tokens. Budget accordingly.

And to be fair, this is not a China-only problem. Gemini's API rate limits are set at the project level and cannot be subdivided per developer, app, or agent, which makes it hard for a team to even locate which caller blew the limit. <!-- [doc_5681f797b78c92d5f7cccc241a08a2e3] -->

## "Permanent" Credits Are Permanent Credits — Not a Locked Price, Not Unlimited Speed

"Permanently valid" reads like free. It isn't.

OpenCode Go users pay $10/month and receive $60 of DeepSeek V4.1 Flash usage credit that never expires — up from the original $30/month allotment, upgraded in Phase 2 to $60 and kept long-term. <!-- [doc_aca61ff73451846f75e14d9e94317695] -->

Read the fine print on what "permanent" modifies. It modifies the credit's expiry date. It does not lock your unit price, and it does not lift the rate limits. You can hold $60 of credit forever and still be unable to spend it in a single 5-hour window. $60 won't buy me speed.

The rest of the credit-pack market is worth comparing against. Financial Datasets sells a $20 one-time credit pack, with Build at $200/month and Scale at $2,000/month. Refero's Pro subscription is $17/month or $120/year, with commercial documents at $0.001 per request and a $2,000 minimum commitment. Different shapes, same lesson: you are buying a bucket, and the bucket has a spout width.

Speed is a cost too, and peak makes it worse. Claude Opus 5.5 hit a 644-second time-to-first-token at peak in its deep-reasoning tier. For contrast, Step 5 Preview measured 0.9s, DeepSeek V4.1 Flash 1.1s, and GLM-5.3 1.9s. <!-- [doc_3e5fc44d8368b305e0bdb046c6eeaa03] --> Latency never shows up on an invoice, but it shows up in how many iterations you get through in a day. Wait ten extra minutes per task and you lose a whole round.

Long context has its own pricing trap. GLM 5.3 Flash uses flat per-token pricing above 100K tokens, avoiding the long-context premium that Haiku applies. <!-- [doc_821b28eca470cf387e599c30b7725f23] --> DeepSeek V4.1 Flash, meanwhile, supports a 1M-token context window, with official tests covering coding-agent tasks like NL2Repo and Cybergym. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> A 1M window means a single request can carry an enormous input — and the 2x peak multiplier scales that input right along with it.

The multiplier is the part a credit balance hides. On DeepSeek's published schedule, idle-time prices are half the peak rate: weekdays 9:00–12:00 and 14:00–18:00 bill at 2x the table price, while weekends and the 12:00–14:00 and post-18:00 weekday windows sit at the base rate. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] --> So the same batch job costs twice as much depending on when you press run. A pack of credits does not arbitrage that for you; only your cron schedule does.

DeepSeek's 2x window doesn't reach me.

That is the practical reading of the $60: it is a runway, not a price floor. Run nightly and the credit stretches; run at 10 a.m. on a Tuesday and it drains at double speed while the "permanent" label stays exactly as true as it was on day one.

## Multiply the Three, Then Schedule Your Own Tasks

The cost model is unit price × peak factor × rerun factor. Fill in all three columns. Filling in only the first is how people talk themselves into a bill they didn't expect.

Unit price: 3 yuan input / 9 yuan output off-peak. Peak factor: 2.0 at peak, 1.0 off-peak. Rerun factor: an interrupted task counts as consumed plus rerun. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> And keep one line for the only multiplier that moves down — KV Cache hits, which can push real cost to one-tenth of list. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

The scheduling rule that falls out of this: move batch, deferrable coding work to all day Saturday and Sunday, or to weekday 12:00–14:00 and after 18:00. Keep interactive, must-run-now work in the peak window and budget it at 2x. <!-- [doc_5528073dd1f937283caedd2c3baea7bc] -->

Xiaomi mimo-v2.6-pro carries an intelligence index of 46.3 — 10th globally, first among Chinese models, and first on price-performance at 7.7. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] --> <!-- [doc_c6529bc86a0b8c6e764c417e8433f153] --> I'd bet on Xiaomi's 46.3.

Which leaves you the real trade-off, and I won't pretend there's one answer: is the money you save by batching off-peak worth the iteration speed you give up during the day? It depends entirely on whether your tasks can wait.

One caveat on the numbers above: the price figures here were captured across market tables dated 2026-09-08, 2026-09-10, 2026-09-18, 2026-09-25, 2026-10-03, 2026-10-06, 2026-10-12, and 2026-10-13. Peak windows can shift with official changes — check the vendor page before you commit a budget. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] -->

*Also readable on [Telegraph](https://telegra.ph/The-Listed-Price-Is-a-Lie-What-DeepSeeks-PeakOff-Peak-Pricing-Rate-Limit-Windows-and-Permanent-Credits-Actually-Cost-Per-Task-11-13).*


---

**Read next**

- [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md)
- [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md)
- [Token Optimization for Indie Developers' AI API Bills](token-optimization-for-indie-developers-ai-api-bills.md)

[All 70 write-ups](../README.md)

The 31 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 738 more, as JSON and CSV.

Topics: [AI Costs](../topics/ai-costs.md) · [AI Programming](../topics/ai-programming.md) · [Chinese AI](../topics/chinese-ai.md) · [Developer Productivity](../topics/developer-productivity.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** How many hours per week you actually run your coding agent inside DeepSeek's peak windows — reply with one word (none, few, most) saying where your usage falls. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/89).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md&title=%5Bcorrection%5D+The+Listed+Price+Is+a+Lie%3A+What+DeepSeek%27s+Peak%2FOff-Peak+Pricing%2C+Rate-Limit+Windows%2C+and+%22Permanent%22+Credits+Actually+Cost+Per+Task) — that form knows
which write-up you came from too; corrections and counter-data are the point.
