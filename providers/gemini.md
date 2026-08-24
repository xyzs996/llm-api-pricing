# Gemini API pricing: what 10 models cost a coding agent

Every Gemini model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-08-24**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep Gemini discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What Gemini charges per million tokens

10 Gemini models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-08-24**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**Gemini charges one cache-read rate across every row that publishes one: 10% of that row's own input price.** All 8 of them use it, so within Gemini the cheapest row on list price is also the cheapest row an agent actually pays — the ordering does not change. Repriced at a coding agent's mix, Gemini's list input price overstates what an agent pays by a median **6.6×** (range 6.5×–6.6×).

⚠ **2 of these 10 rows publish no cache-read price at all** (`Gemini 3 Flash Preview`, `Gemini 3.1 Pro Preview`), so the agent-mix column is empty for them. That is not a zero and not a discount — it is a number the catalog does not carry, and filling it in with the list input price would make those rows look five to six times dearer than they are.

**2 of these 10 rows cost more than the price in their own row once the prompt is long enough.** The threshold reprices *every* token in the request, including the ones under it, so one token over the line roughly doubles the call. The thresholds are in the table.

5 rows are marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.0283** | $0.1875 | $0.0187 | $0.9375 | [Gemini 3.7 Flash](https://openrouter.ai/google/gemini-3.7-flash:batch) `batch` | 1M | — | #2 agenticgamedev |
| **$0.0566** | $0.375 | $0.0375 | $1.875 | [Gemini 3.6 Flash](https://openrouter.ai/google/gemini-3.6-flash:batch) `batch` | 1M | — | #7 agenticgamedev |
| **$0.0566** | $0.375 | $0.0375 | $1.875 | [Gemini 3.7 Flash](https://openrouter.ai/google/gemini-3.7-flash) | 1M | — | #2 agenticgamedev |
| **$0.0769** | $0.50 | $0.05 | $3.00 | [Gemini 3 Flash Preview](https://openrouter.ai/google/gemini-3-flash-preview) | 1M | — | #9 agenticslides |
| **$0.1131** | $0.75 | $0.075 | $3.75 | [Gemini 3.6 Flash](https://openrouter.ai/google/gemini-3.6-flash) | 1M | — | #7 agenticgamedev |
| **$0.1153** | $0.75 | $0.075 | $4.50 | [Gemini 3.5 Flash](https://openrouter.ai/google/gemini-3.5-flash:batch) `batch` | 1M | — | #3 agenticslides(python-pptx) |
| **$0.2306** | $1.50 | $0.15 | $9.00 | [Gemini 3.5 Flash](https://openrouter.ai/google/gemini-3.5-flash) | 1M | — | #3 agenticslides(python-pptx) |
| **$0.3075** | $2.00 | $0.20 | $12.00 | [Gemini 3.1 Pro Preview](https://openrouter.ai/google/gemini-3.1-pro-preview) | 1M | $4.00 past 200k | #5 agentichtmlslides |
| — | $0.25 | — | $1.50 | [Gemini 3 Flash Preview](https://openrouter.ai/google/gemini-3-flash-preview:batch) `batch` | 1M | — | #9 agenticslides |
| — | $1.00 | — | $6.00 | [Gemini 3.1 Pro Preview](https://openrouter.ai/google/gemini-3.1-pro-preview:batch) `batch` | 1M | $2.00 past 200k | #5 agentichtmlslides |

Cheapest Gemini row an agent can call normally is **Gemini 3.7 Flash** at $0.0566 per million; the dearest is $0.3075, 5× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## Gemini against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| DeepSeek | 1 | 8.3% | 7.9× | $0.0664 |
| Claude | 18 | 10% | 6.6× | $0.3017 |
| **Gemini** | 10 | 10% | 6.6× | $0.0566 |
| OpenAI | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 2 | 12% | 6.0× | $0.2067 |
| Qwen | 2 | 12.5–20% | 5.0× | $0.3379 |
| Grok | 4 | 15–25% | 5.0× | $0.2494 |
| Kimi | 5 | 10–25.4% | 4.7× | $0.0918 |
| GLM | 7 | 18.6–20% | 4.1× | $0.0979 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.1×, across 18 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about Gemini while these were measured

1 figure in these field notes comes from a sentence that names Gemini. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **$0.0566** — “Gemini 3.7 Flash is the cheapest of the 40 at $0.0566 effective, and DeepSeek V4 Pro sits right next to it — a fact that turned out to be the loose thread in this whole piece.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)

[All 493 figures, every kind](../figures.md)

- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)

**A Gemini price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=Gemini&title=%5Bcorrection%5D+Gemini) — the form already knows it is about Gemini; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
