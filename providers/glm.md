# GLM API pricing: what 7 models cost a coding agent

Every GLM model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-08-25**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep GLM discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What GLM charges per million tokens

7 GLM models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-08-25**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**GLM does not have one cache-read rate — it has 2.** Across 7 rows the discount runs from 18.6% to 20.0% of that row's own input price (18.6%, 20%). So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, GLM's list input price overstates what an agent pays by a median **4.1×** (range 4.1×–4.4×).

1 row is marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.0979** | $0.40 | $0.08 | $1.75 | [GLM 4.7](https://openrouter.ai/z-ai/glm-4.7) | 204K | — | #27 androidnative |
| **$0.1218** | $0.50 | $0.10 | $2.00 | [GLM 4.6](https://openrouter.ai/z-ai/glm-4.6) | 204K | — | #13 godotgamedev |
| **$0.1448** | $0.60 | $0.12 | $1.92 | [GLM 5](https://openrouter.ai/z-ai/glm-5) | 204K | — | #16 godotgamedev |
| **$0.2706** | $1.19 | $0.221 | $3.74 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2) | 1M | — | #10 fullstack |
| **$0.2866** | $1.26 | $0.234 | $3.96 | [GLM 5.1](https://openrouter.ai/z-ai/glm-5.1) | 204K | — | #3 agenticslides |
| **$0.29** | $1.20 | $0.24 | $4.00 | [GLM 5V Turbo](https://openrouter.ai/z-ai/glm-5v-turbo) | 202K | — | #4 androidnative |
| **$0.3184** | $1.40 | $0.26 | $4.40 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2:batch) `batch` | 1M | — | #10 fullstack |

Cheapest GLM row an agent can call normally is **GLM 4.7** at $0.0979 per million; the dearest is $0.29, 3× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## GLM against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| DeepSeek | 1 | 8.3% | 7.9× | $0.0731 |
| Claude | 18 | 10% | 6.6× | $0.3017 |
| Gemini | 10 | 10% | 6.6× | $0.0566 |
| OpenAI | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 2 | 12% | 6.0× | $0.2067 |
| Qwen | 2 | 12.5–20% | 5.0× | $0.3379 |
| Grok | 4 | 15–25% | 5.0× | $0.2494 |
| Kimi | 5 | 10–28.4% | 4.7× | $0.1288 |
| **GLM** | 7 | 18.6–20% | 4.1× | $0.0979 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.1×, across 18 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about GLM while these were measured

2 figures in these field notes come from a sentence that names GLM. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **45.2%** — “GLM-5.1 does the same: sort by input and you take GMICloud, and pay 45.2% over Chutes.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10.00%** — “Now the other side. z-ai's GLM-5.1 is served by seventeen hosts, cache read ratios running 10.00% to 50.42%.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)

[All 493 figures, every kind](../figures.md)

- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)

**A GLM price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=GLM&title=%5Bcorrection%5D+GLM) — the form already knows it is about GLM; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
