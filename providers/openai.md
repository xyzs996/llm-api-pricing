# OpenAI API pricing: what 9 models cost a coding agent

Every OpenAI model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-08-24**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep OpenAI discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What OpenAI charges per million tokens

9 OpenAI models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-08-24**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**OpenAI does not have one cache-read rate — it has 2.** Across 9 rows the discount runs from 10.0% to 10.4% of that row's own input price (10%, 10.4%). So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, OpenAI's list input price overstates what an agent pays by a median **6.3×** (range 6.1×–6.5×).

**4 of these 9 rows cost more than the price in their own row once the prompt is long enough.** The threshold reprices *every* token in the request, including the ones under it, so one token over the line roughly doubles the call. The thresholds are in the table.

3 rows are marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.1396** | $0.875 | $0.0875 | $7.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2:batch) `batch` | 400K | — | #18 godotgamedev |
| **$0.1922** | $1.25 | $0.125 | $7.50 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4:batch) `batch` | 1.1M | $2.50 past 272k | #22 godotgamedev |
| **$0.2042** | $1.25 | $0.13 | $10.00 | [GPT-5.1-Codex](https://openrouter.ai/openai/gpt-5.1-codex) | 400K | — | #24 mobileapps |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2) | 400K | — | #18 godotgamedev |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.2-Codex](https://openrouter.ai/openai/gpt-5.2-codex) | 400K | — | #19 godotgamedev |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.3-Codex](https://openrouter.ai/openai/gpt-5.3-codex) | 400K | — | #24 godotgamedev |
| **$0.3843** | $2.50 | $0.25 | $15.00 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4) | 1.1M | $5.00 past 272k | #22 godotgamedev |
| **$0.3843** | $2.50 | $0.25 | $15.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5:batch) `batch` | 1.1M | $5.00 past 272k | #7 agenticslides |
| **$0.7687** | $5.00 | $0.50 | $30.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5) | 1.1M | $10.00 past 272k | #7 agenticslides |

Cheapest OpenAI row an agent can call normally is **GPT-5.1-Codex** at $0.2042 per million; the dearest is $0.7687, 4× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## OpenAI against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| DeepSeek | 1 | 8.3% | 7.9× | $0.0664 |
| Claude | 18 | 10% | 6.6× | $0.3017 |
| Gemini | 10 | 10% | 6.6× | $0.0566 |
| **OpenAI** | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 2 | 12% | 6.0× | $0.2067 |
| Qwen | 2 | 12.5–20% | 5.0× | $0.3379 |
| Grok | 4 | 15–25% | 5.0× | $0.2494 |
| Kimi | 5 | 10–28.4% | 4.7× | $0.0918 |
| GLM | 7 | 18.6–20% | 4.1× | $0.0979 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.1×, across 18 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about OpenAI while these were measured

3 figures in these field notes come from a sentence that names OpenAI. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **10%** — “Anthropic, Google and OpenAI each charge 10% of input for a cache read — flat, every model, and stable across sellers too.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$0.19 per million tokens** — “Chinese AI models provide a cost-effective alternative to their American counterparts, with input costs as low as $0.19 per million tokens, compared to OpenAI's $5-12.” (2026-08-07) [→](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)
- **4 hours** — “He used OpenAI Codex's Record & Replay to automate monthly report generation, taking it from 4 hours to a few minutes.” (2026-08-05) [→](../articles/how-chinese-developers-are-using-codex-record-replay-to.md)

[All 493 figures, every kind](../figures.md)

- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)
- [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/10) · [telegra.ph](https://telegra.ph/How-Chinese-AI-Agent-Tools-Leverage-16-Billion-Free-Tokens-08-19)
- [How Chinese Developers Are Using Codex Record & Replay to Streamline Repetitive Workflows](../articles/how-chinese-developers-are-using-codex-record-replay-to.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/25) · [telegra.ph](https://telegra.ph/How-Chinese-Developers-Are-Using-Codex-Record--Replay-to-Streamline-Repetitive-Workflows-08-19)

**A OpenAI price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=OpenAI&title=%5Bcorrection%5D+OpenAI) — the form already knows it is about OpenAI; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
