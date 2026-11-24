# OpenAI API pricing: what 11 models cost a coding agent

Every OpenAI model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-11-24**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep OpenAI discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What OpenAI charges per million tokens

11 OpenAI models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-11-24**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**OpenAI does not have one cache-read rate — it has 3.** Across 11 rows the discount runs from 5.0% to 10.4% of that row's own input price (5%, 10%, 10.4%). So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, OpenAI's list input price overstates what an agent pays by a median **6.5×** (range 6.1×–9.7×).

**6 of these 11 rows cost more than the price in their own row once the prompt is long enough.** The threshold reprices *every* token in the request, including the ones under it, so one token over the line roughly doubles the call. The thresholds are in the table.

4 rows are marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.103** | $1.00 | $0.05 | $5.00 | [GPT-6.1 Sol](https://openrouter.ai/openai/gpt-6.1-sol:batch) `batch` | 1.1M | $2.00 past 272k | #2 blender3d |
| **$0.1396** | $0.875 | $0.0875 | $7.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2:batch) `batch` | 400K | — | #20 godotgamedev |
| **$0.1922** | $1.25 | $0.125 | $7.50 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4:batch) `batch` | 1.1M | $2.50 past 272k | #23 godotgamedev |
| **$0.2042** | $1.25 | $0.13 | $10.00 | [GPT-5.1-Codex](https://openrouter.ai/openai/gpt-5.1-codex) | 400K | — | #26 mobileapps |
| **$0.206** | $2.00 | $0.10 | $10.00 | [GPT-6.1 Sol](https://openrouter.ai/openai/gpt-6.1-sol) | 1.1M | $4.00 past 272k | #2 blender3d |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2) | 400K | — | #20 godotgamedev |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.2-Codex](https://openrouter.ai/openai/gpt-5.2-codex) | 400K | — | #19 androidnative |
| **$0.2792** | $1.75 | $0.175 | $14.00 | [GPT-5.3-Codex](https://openrouter.ai/openai/gpt-5.3-codex) | 400K | — | #26 godotgamedev |
| **$0.3843** | $2.50 | $0.25 | $15.00 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4) | 1.1M | $5.00 past 272k | #23 godotgamedev |
| **$0.3843** | $2.50 | $0.25 | $15.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5:batch) `batch` | 1.1M | $5.00 past 272k | #6 agenticslides |
| **$0.7687** | $5.00 | $0.50 | $30.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5) | 1.1M | $10.00 past 272k | #6 agenticslides |

Cheapest OpenAI row an agent can call normally is **GPT-5.1-Codex** at $0.2042 per million; the dearest is $0.7687, 4× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## OpenAI against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| xiaomi | 2 | 0.8–20% | 11.2× | $0.0237 |
| tencent | 1 | 5% | 10.3× | $0.0407 |
| DeepSeek | 3 | 3.3–8.4% | 7.9× | $0.0028 |
| Claude | 26 | 2.5–10% | 6.6× | $0.0151 |
| Gemini | 20 | 5–10% | 6.6× | $0.0769 |
| **OpenAI** | 11 | 5–10.4% | 6.5× | $0.2042 |
| Llama | 7 | 5–13.3% | 6.0× | $0.0569 |
| upstage | 2 | 10–20% | 5.4× | $0.0074 |
| nvidia | 2 | 13.3–20% | 4.9× | $0.0266 |
| thinkingmachines | 1 | 17% | 4.7× | $0.215 |
| Grok | 8 | 15–25% | 4.2× | $0.2494 |
| Qwen | 4 | 20% | 4.1× | $0.0779 |
| GLM | 12 | 16.7–98.6% | 4.1× | $0.0251 |
| MiniMax | 3 | 20% | 4.1× | $0.0731 |
| reflection | 1 | 20% | 4.1× | $0.0609 |
| stepfun | 1 | 20% | 4.0× | $0.0497 |
| Kimi | 7 | 10–94.8% | 2.9× | $0.1479 |

The spread in that fourth column is the whole point: Claude at 6.6× against Kimi at 2.9×, across 26 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about OpenAI while these were measured

7 figures in these field notes come from a sentence that names OpenAI. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **10 million tokens** — “LongCat gives 10 million tokens to new users who complete verification, with an API compatible with both OpenAI and Claude, so it drops into Claude Code, OpenClaw, and Qoder.” (2026-11-24) [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **10,000,000 tokens** — “LongCat gives new verified users 10,000,000 tokens, with an API compatible with OpenAI and Claude so it drops into Claude Code, OpenClaw, Qoder and similar agents.” (2026-11-23) [→](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- **14.753-second** — “An agent running tool calls through the OpenAI API in Lumina hit a 14.753-second rate limit after one call, or at most two.” (2026-11-20) [→](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- **20%** — “OpenAI is positioning ChatGPT Work as a productivity platform for business teams, and the share of its users who don't code is projected to grow from 20% to 60% within 12 months.” (2026-09-25) [→](../articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md)
- **10%** — “Anthropic, Google and OpenAI each charge 10% of input for a cache read — flat, every model, and stable across sellers too.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$0.19 per million tokens** — “Chinese AI models provide a cost-effective alternative to their American counterparts, with input costs as low as $0.19 per million tokens, compared to OpenAI's $5-12.” (2026-08-07) [→](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)
- **4 hours** — “He used OpenAI Codex's Record & Replay to automate monthly report generation, taking it from 4 hours to a few minutes.” (2026-08-05) [→](../articles/how-chinese-developers-are-using-codex-record-replay-to.md)

[All 950 figures, every kind](../figures.md)

- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)
- [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/10) · [telegra.ph](https://telegra.ph/How-Chinese-AI-Agent-Tools-Leverage-16-Billion-Free-Tokens-08-19)
- [How Chinese Developers Are Using Codex Record & Replay to Streamline Repetitive Workflows](../articles/how-chinese-developers-are-using-codex-record-replay-to.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/25) · [telegra.ph](https://telegra.ph/How-Chinese-Developers-Are-Using-Codex-Record--Replay-to-Streamline-Repetitive-Workflows-08-19)
- [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/97) · [telegra.ph](https://telegra.ph/I-Ran-DeepSeek-V4-Pro-and-GLM-4-Flash-in-the-Same-Coding-Agent-One-Took-24-Minutes-and-Deployed-Without-Asking-11-24)
- [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](../articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/76) · [telegra.ph](https://telegra.ph/Stop-Hitting-the-5-Hour-Limit-Routing-Your-IDEs-AI-Requests-to-Local-Models-09-25)
- [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/95) · [telegra.ph](https://telegra.ph/The-Cheap-Model-Is-50x-Cheaper-Until-It-Gets-Banned-Real-Per-Token-Costs-vs-What-Actually-Breaks-11-20)
- [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/96) · [telegra.ph](https://telegra.ph/The-Same-Model-Costs-2x-More-at-10am--Three-Pricing-Cliffs-That-Blow-Up-Your-Coding-Agents-Bill-11-23)

**A OpenAI price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=OpenAI&title=%5Bcorrection%5D+OpenAI) — the form already knows it is about OpenAI; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
