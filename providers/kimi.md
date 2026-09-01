# Kimi API pricing: what 5 models cost a coding agent

Every Kimi model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-09-01**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep Kimi discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What Kimi charges per million tokens

5 Kimi models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-09-01**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**Kimi does not have one cache-read rate — it has 4.** Across 5 rows the discount runs from 10.0% to 27.3% of that row's own input price (10%, 15.6%, 16.8%, 27.3%). So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, Kimi's list input price overstates what an agent pays by a median **4.9×** (range 3.2×–6.6×).

1 row is marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.0918** | $0.45 | $0.07 | $2.25 | [Kimi K2.5](https://openrouter.ai/moonshotai/kimi-k2.5) | 262K | — | #9 godotgamedev |
| **$0.2033** | $0.95 | $0.16 | $4.00 | [Kimi K2.6](https://openrouter.ai/moonshotai/kimi-k2.6) | 262K | — | #2 agentichtmlslides |
| **$0.2089** | $0.66 | $0.18 | $3.40 | [Kimi K2.7 Code](https://openrouter.ai/moonshotai/kimi-k2.7-code) | 262K | — | #7 htmlslides |
| **$0.4525** | $3.00 | $0.30 | $15.00 | [Kimi K3](https://openrouter.ai/moonshotai/kimi-k3) | 1M | — | #1 webapps |
| **$0.4525** | $3.00 | $0.30 | $15.00 | [Kimi K3](https://openrouter.ai/moonshotai/kimi-k3:batch) `batch` | 1M | — | #1 webapps |

Cheapest Kimi row an agent can call normally is **Kimi K2.5** at $0.0918 per million; the dearest is $0.4525, 5× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## Kimi against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| DeepSeek | 1 | 8.4% | 7.9× | $0.2035 |
| Claude | 18 | 10% | 6.6× | $0.3017 |
| Gemini | 10 | 10% | 6.6× | $0.0769 |
| OpenAI | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 2 | 12% | 6.0× | $0.2067 |
| Qwen | 2 | 12.5–20% | 5.0× | $0.3379 |
| Grok | 4 | 15–25% | 5.0× | $0.2494 |
| **Kimi** | 5 | 10–27.3% | 4.9× | $0.0918 |
| GLM | 6 | 18.6–20% | 4.2× | $0.0979 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.2×, across 18 and 6 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about Kimi while these were measured

4 figures in these field notes come from a sentence that names Kimi. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **10.00%** — “Kimi K2.6 has nineteen, 10.00% to 50.00%.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$3,000** — “While we are here: budgeting a billion tokens at Kimi K3's list input predicts $3,000.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$0.4525** — “Kimi K3 prices at $0.4525 effective.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **60 percent** — “Microsoft's evaluation of Kimi K3 landed on a number that should change how you read a pricing page: about 60 percent of the cost difference between models comes from the thinking depth a task requires, not from the price per token.” (2026-08-05) [→](../articles/ai-model-costs-beyond-per-token-pricing.md)

[All 500 figures, every kind](../figures.md)

- [AI Model Costs: Beyond Per-Token Pricing](../articles/ai-model-costs-beyond-per-token-pricing.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/20) · [telegra.ph](https://telegra.ph/Beyond-Token-Pricing-How-Indie-Devs-Should-Really-Evaluate-AI-Model-Costs-08-19)
- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)

**A Kimi price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=Kimi&title=%5Bcorrection%5D+Kimi) — the form already knows it is about Kimi; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
