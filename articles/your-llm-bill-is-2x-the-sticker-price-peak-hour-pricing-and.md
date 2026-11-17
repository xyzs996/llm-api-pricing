# Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff

![Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

In September and October 2026, a run of Chinese-language model price sheets started circulating with a line at the top that English cost write-ups still don't have: these are off-peak prices. The DeepSeek numbers in them apply on weekends and after hours. On weekday peak windows — 9:00–12:00 and 14:00–18:00 — you pay double the table. In the same sheets, the GPT-6 series carries a second trap: once input crosses 272,000 tokens, the entire request is repriced, input and cache rates double, output goes up 50%.

Stack those two mechanisms and a budget built on sticker price can miss by 2x by month end. This piece doesn't guess at it. It takes the two thresholds apart, computes what each one does to a bill, and shows where off-peak scheduling actually saves you money.

Stack's 2x feels overstated to me.

## A price sheet that quietly quoted the off-peak rate

Between October 3 and October 13, four separate Chinese price sheets repeated the same footnote word for word. DeepSeek's listed prices are off-peak prices — Saturday and Sunday all day, plus weekday 12:00–14:00 and everything after 18:00. Weekday peak 9:00–12:00 and 14:00–18:00 is billed at twice the table. The same wording shows up in the October 3, October 6, October 12, and October 13 editions. That's four independent sources agreeing on the same discount structure, which is the strongest signal available that this isn't one outlet's typo.

The October 13 sheet also refreshed the low end. Xiaomi's mimo-v2.6-pro is listed at 3 yuan input and 6 yuan output per million tokens, with a value score of 7.7 — first place in that sheet's ranking. Ant Group's Ling-3.0-flash sits at 0.12 yuan input and 0.38 yuan output, top of the lightweight tier. Qwen3.8-Flash, released 2026.08.14, is 0.2 yuan input and 2 yuan output, positioned explicitly as the cheap option for RAG and batch copy generation.

Then there's the GPT-6 threshold clause, which got pulled out and discussed on its own. It is not a linear surcharge on the tokens above the line. Cross 272,000 tokens and the whole request is repriced: input and cache rates double, output rises 50%. A modest bump in context past that line can more than double the cost of that call, because the repricing applies to the entire request rather than just the overflow.

Cross 272,000 doesn't touch me.

The reason this matters more than a single line item is that the same sheet format invites cross-model comparison on sticker price alone, and the sticker price is often the best case rather than the expected case. Take Qwen3.5 Plus: input runs 0.12–0.57 USD per million tokens and output 0.69–3.44 USD per million tokens, a spread of nearly 5x on both sides of the same model, alongside a 1M-token context window aimed at ultra-long text and multimodal agents. A developer budgeting from the low end of that range and then running long-context agent loops will land near the high end, which is the same failure mode as reading a DeepSeek off-peak number as an all-day number. The two pricing quirks rhyme: in one case the clock decides which rate applies, in the other the context length and workload profile do.

The mid-tier comparisons have the same shape. Notice that caching, not the headline rate, is what separates a cheap workload from an expensive one — the cached-input figure is 20x and 50x below the uncached input figure respectively, so any estimate that ignores cache hit rate will be wrong by an order of magnitude before it ever reaches the peak/off-peak question. That is the concrete reason to treat every number in this section as a ceiling-to-floor range rather than a price.

## Why the English side hasn't seen this bill yet

English-language cost comparisons are almost all built from the official price list, and the time-of-day layer gets skipped systematically. The peak/off-peak wording has been retransmitted in Chinese sources at least four times over; there is no corresponding breakdown on the English side. The result is that the same model reads as an off-peak price in an English blog post and as a 2x line item on a Chinese bill.

Threshold repricing is harder to spot for a structural reason: on the pricing page it's a footnote, and on the bill it's a jump. One detail worth flagging if you plan to recompute any of this yourself — the tier boundary needs to note which reasoning effort level it corresponds to, or your arithmetic will drift from the invoice.

The comparison unit is already shifting in Chinese sources, from price per million tokens to cost per successful task. DeepSeek V4.1 Flash scores 96.0 on coding and comes in at $0.181 per successful task. English-side write-ups are still quoting the former.

The English community has its own scattered evidence that sticker price isn't enough, but it hasn't hardened into a method. One estimate has two models both scoring 99/100 on writing tasks with monthly API bills of $462.60 and $116.10 — roughly a 4x gap on similar list prices. The same source notes that any estimate has to fold in prompt cache hit rate and reasoning token multipliers, or it will miss the actual invoice.

That gap between list price and billed price has a second cause the English side rarely names: the cache. The 2026 batch of Chinese models all shipped stronger KV Cache compression, and on a cache hit the real cost falls to one tenth of the sticker price. For a RAG pipeline that re-sends the same retrieved context on every turn, that is the difference between a budget that holds and one that doesn't — the discount is a function of your hit rate, not of the model you picked.

## Working the two thresholds into an actual bill

Start with time. DeepSeek V4.1-Flash, released 2026.09.10 and positioned for code and batch work, is 3 yuan input and 9 yuan output per million tokens off-peak, doubling during weekday daylight peak. If you're running batch jobs, moving them past 18:00 or onto the weekend puts the unit price back at the table rate. The 12:00–14:00 window is also billed off-peak — a two-hour discount slot in the middle of the workday that is the easiest one to miss.

The 12:00 window doesn't reach me.

Now the threshold. Because GPT-6's long-context rule reprices the entire request rather than surcharging only the excess, cutting long-context tasks below the line doesn't save you linearly — it saves you in a cliff. The moment just past the line is the one to keep in your head when you're deciding whether to stuff one more file into the context window.

The GPT-6 cliff still seems real to me.

Caching is the third variable, and it's the one that can pull real cost down to a tenth of sticker. The batch of Chinese models released in 2026 all strengthened KV cache compression, and a cache hit drops effective cost to roughly 1/10 of list. DeepSeek V4.1-Flash specifically compressed KV cache to a quarter of the previous generation's HBM footprint and an eighth of its SSD footprint. If your workload is RAG or an agent that re-sends the same system prompt, cache hit rate moves your bill more than model choice does.

Here's the counterexample that keeps this honest: the vendor saying cost is lower does not mean you pay less. DeepSeek V4.1 Flash's beta was billed identically to v4-flash, with peak output still at 9 yuan per million tokens. That beta also capped each account at 20 concurrent requests and auto-expired after September 10 — a two-day window. Rate limits change real throughput cost even when the per-token number looks fine, and a two-day evaluation window won't tell you what a month of production costs.

The 20-request cap cost me.

One structural escape hatch: put a flat-price model in the candidate set. GLM 5.3 Flash uses a flat token price for inputs above 100K tokens, which avoids the long-context cost jump that Haiku carries. If your agent regularly pushes past 100K, that's a different pricing shape, not a lower price.

## My bet: the price sheet gets rewritten before the bill does

First bet — budgeting off sticker price gets retired within 2026, because both layers are already live at once. The peak/off-peak wording appears identically across four independent sources; that's not a single outlet's error, it's the published structure.

Second bet — the absolute price of the cheap tier keeps falling, and it doesn't fix the bill structure problem. Ling-3.0-flash is already at 0.12 yuan input and 0.38 yuan output per million tokens.

Third bet — the comparison unit moves from per-million-token to per-successful-task. Sources are already presenting $0.181 per successful task next to a coding score of 96.0, side by side, which is the shape the conversation is heading toward.

The one thing you can do today without switching models: schedule non-realtime batch work past 18:00, onto weekends, or into the 12:00–14:00 window, and cap client-side input below 272,000 tokens. Both are scheduling changes, not migration projects.

*Also readable on [Telegraph](https://telegra.ph/Your-LLM-Bill-Is-2x-the-Sticker-Price-Peak-Hour-Pricing-and-the-272K-Token-Cliff-11-17).*


---

**Read next**

- [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md)
- [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)
- [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](the-hidden-cost-of-ai-automation-turning-human-instincts.md)

[All 73 write-ups](../README.md)

The 18 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 810 more, as JSON and CSV.

Topics: [AI](../topics/ai.md) · [Software Development](../topics/software-development.md) · [Token Optimization](../topics/token-optimization.md) · [AI Pricing](../topics/ai-pricing.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md&title=%5Bcorrection%5D+Your+LLM+Bill+Is+2x+the+Sticker+Price%3A+Peak-Hour+Pricing+and+the+272K+Token+Cliff) — that form knows
which write-up you came from too; corrections and counter-data are the point.
