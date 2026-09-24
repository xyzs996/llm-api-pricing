# GLM API pricing: what 8 models cost a coding agent

Every GLM model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-09-24**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep GLM discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What GLM charges per million tokens

8 GLM models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-09-24**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**GLM does not have one cache-read rate — it has 3.** Across 8 rows the discount runs from 18.6% to 22.2% of that row's own input price (18.6%, 20%, 22.2%). So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, GLM's list input price overstates what an agent pays by a median **4.2×** (range 3.8×–4.4×).

1 row is marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.0979** | $0.40 | $0.08 | $1.75 | [GLM 4.7](https://openrouter.ai/z-ai/glm-4.7) | 204K | — | #27 androidnative |
| **$0.0991** | $0.43 | $0.08 | $1.75 | [GLM 4.6](https://openrouter.ai/z-ai/glm-4.6) | 204K | — | #17 godotgamedev |
| **$0.1198** | $0.45 | $0.10 | $2.00 | [GLM 5.3](https://openrouter.ai/z-ai/glm-5.3:batch) `batch` | 1M | — | #7 python-pptxslides |
| **$0.1448** | $0.60 | $0.12 | $1.92 | [GLM 5](https://openrouter.ai/z-ai/glm-5) | 204K | — | #18 htmlslides |
| **$0.1477** | $0.6496 | $0.1206 | $2.0416 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2) | 1M | — | #10 agenticgamedev |
| **$0.191** | $0.84 | $0.156 | $2.64 | [GLM 5.3](https://openrouter.ai/z-ai/glm-5.3) | 1.3M | — | #7 python-pptxslides |
| **$0.2197** | $0.966 | $0.1794 | $3.036 | [GLM 5.1](https://openrouter.ai/z-ai/glm-5.1) | 204K | — | #2 agenticslides |
| **$0.29** | $1.20 | $0.24 | $4.00 | [GLM 5V Turbo](https://openrouter.ai/z-ai/glm-5v-turbo) | 202K | — | #4 androidnative |

Cheapest GLM row an agent can call normally is **GLM 4.7** at $0.0979 per million; the dearest is $0.29, 3× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## GLM against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| xiaomi | 1 | 0.8% | 18.4× | $0.0237 |
| DeepSeek | 1 | 8.3% | 7.9× | $0.1182 |
| Claude | 18 | 2.5–10% | 6.6× | $0.3017 |
| Gemini | 12 | 10% | 6.6× | $0.0769 |
| OpenAI | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 3 | 12% | 6.0× | $0.2067 |
| Grok | 5 | 15–25% | 5.0× | $0.2494 |
| Kimi | 5 | 10–27.4% | 4.9× | $0.0918 |
| **GLM** | 8 | 18.6–22.2% | 4.2× | $0.0979 |
| Qwen | 1 | 20% | 4.2× | $0.355 |
| upstage | 1 | 20% | 4.1× | $0.0219 |
| MiniMax | 1 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.2×, across 18 and 8 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about GLM while these were measured

3 figures in these field notes come from a sentence that names GLM. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **80%** — “A local proxy called OpenCodex redirects Codex requests to Chinese models such as DeepSeek and Zhipu GLM, which sidesteps the five-hour quota window and reportedly cuts cost by more than 80% — 10 yuan of DeepSeek credit lasting several days, with measured latency in the 100–200ms range and model switching that doesn't break conversation context.” (2026-09-16) [→](../articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md)
- **45.2%** — “GLM-5.1 does the same: sort by input and you take GMICloud, and pay 45.2% over Chutes.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10.00%** — “Now the other side. z-ai's GLM-5.1 is served by seventeen hosts, cache read ratios running 10.00% to 50.42%.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)

[All 565 figures, every kind](../figures.md)

- [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](../articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/73) · [telegra.ph](https://telegra.ph/63-Billion-Tokens-in-One-Month-Spent-Writing-Google-Ads-for-Amazon-Sellers-09-16)
- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)

**A GLM price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=GLM&title=%5Bcorrection%5D+GLM) — the form already knows it is about GLM; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
