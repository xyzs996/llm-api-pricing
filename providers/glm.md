# GLM API pricing: what 11 models cost a coding agent

Every GLM model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-11-19**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep GLM discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What GLM charges per million tokens

11 GLM models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-11-19**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**GLM does not have one cache-read rate — it has 7.** Across 11 rows the discount runs from 20.0% to 98.6% of that row's own input price. So a cheaper list price here can still be the dearer call once an agent starts caching, and no single discount figure describes this vendor. Repriced at a coding agent's mix, GLM's list input price overstates what an agent pays by a median **3.8×** (range 1.0×–4.1×).

3 rows are marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.0107** | $0.024 | $0.01 | $0.069 | [GLM 5.3 Flash](https://openrouter.ai/z-ai/glm-5.3-flash:batch) `batch` | 1M | — | #32 pdf |
| **$0.0362** | $0.15 | $0.03 | $0.50 | [GLM 5.3 Flash](https://openrouter.ai/z-ai/glm-5.3-flash) | 1M | — | #32 pdf |
| **$0.0728** | $0.0699 | $0.0689 | $1.40 | [GLM 5.3](https://openrouter.ai/z-ai/glm-5.3) | 1M | — | #2 htmlslides |
| **$0.0744** | $0.281 | $0.062 | $1.25 | [GLM 5.3](https://openrouter.ai/z-ai/glm-5.3:batch) `batch` | 1M | — | #2 htmlslides |
| **$0.0979** | $0.40 | $0.08 | $1.75 | [GLM 4.7](https://openrouter.ai/z-ai/glm-4.7) | 204K | — | #33 godotgamedev |
| **$0.1202** | $0.322 | $0.109 | $0.989 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2:batch) `batch` | 1M | — | #9 agenticgamedev |
| **$0.1218** | $0.50 | $0.10 | $2.00 | [GLM 4.6](https://openrouter.ai/z-ai/glm-4.6) | 204K | — | #15 godotgamedev |
| **$0.1661** | $0.62 | $0.14 | $2.42 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2) | 1M | — | #9 agenticgamedev |
| **$0.2413** | $1.00 | $0.20 | $3.20 | [GLM 5](https://openrouter.ai/z-ai/glm-5) | 204K | — | #19 godotgamedev |
| **$0.29** | $1.20 | $0.24 | $4.00 | [GLM 5V Turbo](https://openrouter.ai/z-ai/glm-5v-turbo) | 202K | — | #5 agenticslides |
| **$0.6331** | $1.19 | $0.60 | $3.74 | [GLM 5.1](https://openrouter.ai/z-ai/glm-5.1) | 204K | — | #2 agenticslides |

Cheapest GLM row an agent can call normally is **GLM 5.3 Flash** at $0.0362 per million; the dearest is $0.6331, 17× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## GLM against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| xiaomi | 1 | 0.8% | 18.4× | $0.0237 |
| tencent | 1 | 5% | 10.3× | $0.0407 |
| DeepSeek | 3 | 2–27.8% | 7.5× | $0.0107 |
| Claude | 26 | 2.5–10% | 6.6× | $0.0151 |
| Gemini | 18 | 5–10% | 6.6× | $0.0769 |
| OpenAI | 11 | 5–10.4% | 6.5× | $0.2042 |
| Llama | 7 | 5–13.3% | 6.0× | $0.0569 |
| upstage | 2 | 10–20% | 5.4× | $0.0074 |
| nvidia | 2 | 13.3–20% | 4.9× | $0.0267 |
| thinkingmachines | 1 | 17% | 4.7× | $0.215 |
| Grok | 8 | 15–25% | 4.2× | $0.2494 |
| Qwen | 4 | 20% | 4.1× | $0.0779 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |
| reflection | 1 | 20% | 4.1× | $0.0609 |
| stepfun | 1 | 20% | 4.0× | $0.0497 |
| **GLM** | 11 | 20–98.6% | 3.8× | $0.0362 |
| Kimi | 7 | 10–94.8% | 2.9× | $0.1711 |

The spread in that fourth column is the whole point: Claude at 6.6× against Kimi at 2.9×, across 26 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about GLM while these were measured

19 figures in these field notes come from a sentence that names GLM. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **21 minutes** — “Narrow tasks with a clear scoring rule can also go to the cheap side, which is illustrated by the fact that MiniMax M2.5 scored 28 out of 30 on a bug-hunt task, 3.5 points above GLM-5, and finished in 21 minutes — half of GLM-5's time.” (2026-11-19) [→](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- **20 million tokens** — “Zhipu's signup offer is 20 million tokens, and GLM-4-Flash is 20 million tokens permanently free with a 128K context and 30 concurrent connections.” (2026-11-19) [→](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- **$4.4** — “Zhipu's GLM-5.2 is $4.4.” (2026-11-19) [→](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- **100K tokens** — “GLM 5.3 Flash uses a flat token price for inputs above 100K tokens, which avoids the long-context cost jump that Haiku carries.” (2026-11-17) [→](../articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md)
- **644 seconds** — “First-token latency in that same comparison: Step 5 Preview 0.9s, DeepSeek V4.1 Flash 1.1s, GLM-5.3 1.9s, and Opus 5.5 at max reasoning strength a staggering 644 seconds.” (2026-11-16) [→](../articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)
- **100K tokens** — “If your prompts routinely exceed 100K tokens, take GLM 5.3 Flash for the flat pricing and skip the long-context cliff entirely.” (2026-11-16) [→](../articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)
- **100K tokens** — “GLM 5.3 Flash uses flat per-token pricing above 100K tokens, avoiding the long-context premium that Haiku applies.” (2026-11-13) [→](../articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md)
- **$3 per month** — “The Reddit forecast was $3-5 a month for three light agents, and GLM-4-Flash's 20M free tokens don't expire, while DeepSeek's sign-up grant of 10M tokens (2026-05-02 article) was valid for only 30 days.” (2026-11-10) [→](../articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md)
- **1.1 seconds** — “DeepSeek V4.1 Flash starts answering in 1.1 seconds and GLM-5.3 in 1.9 seconds, while Claude Opus 5.5 at its max reasoning setting took as long as 644 seconds during peak hours.” (2026-11-07) [→](../articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md)
- **$0.87** — “That's expensive next to its Chinese peers, since DeepSeek V4 charges $0.87 and GLM-5.2 charges $4.40.” (2026-11-07) [→](../articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md)
- **$0.68** — “GLM-5.3 completes an intelligent task at an average cost of $0.68, well below the $2.75 Claude Fable 5 needs for a comparable workload.” (2026-11-07) [→](../articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md)
- **$15 per million output tokens** — “Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50.” (2026-11-02) [→](../articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md)
- **90%** — “The real power shows up in daily use: you can send complex logic to GLM, which performs at about 90% of GPT-level quality, while offloading routine tasks to cheaper models like DeepSeek V4 Flash.” (2026-09-30) [→](../articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md)
- **70%** — “Subtitle: How switching to DeepSeek and GLM saved me 70% and gave me back control” (2026-09-30) [→](../articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md)
- **$1 per million tokens** — “Even at the high end, models like GLM 5.2 and DeepSeek V4 Pro hover around $1 per million tokens.” (2026-09-30) [→](../articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md)
- **90%** — “GLM provides an experience benchmarked at 90% of GPT capabilities for daily tasks, while DeepSeek offers a highly competitive pay-as-you-go pricing structure.” (2026-09-25) [→](../articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md)
- **80%** — “A local proxy called OpenCodex redirects Codex requests to Chinese models such as DeepSeek and Zhipu GLM, which sidesteps the five-hour quota window and reportedly cuts cost by more than 80% — 10 yuan of DeepSeek credit lasting several days, with measured latency in the 100–200ms range and model switching that doesn't break conversation context.” (2026-09-16) [→](../articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md)
- **45.2%** — “GLM-5.1 does the same: sort by input and you take GMICloud, and pay 45.2% over Chutes.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10.00%** — “Now the other side. z-ai's GLM-5.1 is served by seventeen hosts, cache read ratios running 10.00% to 50.42%.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)

[All 875 figures, every kind](../figures.md)

- [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](../articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/73) · [telegra.ph](https://telegra.ph/63-Billion-Tokens-in-One-Month-Spent-Writing-Google-Ads-for-Amazon-Sellers-09-16)
- [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](../articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/81) · [telegra.ph](https://telegra.ph/Bypass-Codex-Rate-Limits-The-Local-Proxy-Path-to-70-Cost-Savings-09-30)
- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)
- [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md) · [telegra.ph](https://telegra.ph/Running-DeepSeek-V4-Pro-Inside-Claude-Code-A-Cost-and-Failure-Checklist-for-Cheap-Chinese-Coding-Models-11-19)
- [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](../articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/76) · [telegra.ph](https://telegra.ph/Stop-Hitting-the-5-Hour-Limit-Routing-Your-IDEs-AI-Requests-to-Local-Models-09-25)
- [The "10x Cheaper" Trap: How to Read AI Coding Costs](../articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/85) · [telegra.ph](https://telegra.ph/The-10x-Cheaper-Trap-How-to-Read-AI-Coding-Costs-11-07)
- [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](../articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/89) · [telegra.ph](https://telegra.ph/The-Listed-Price-Is-a-Lie-What-DeepSeeks-PeakOff-Peak-Pricing-Rate-Limit-Windows-and-Permanent-Credits-Actually-Cost-Per-Task-11-13)
- [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](../articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/91) · [telegra.ph](https://telegra.ph/The-Sticker-Price-Said-9x-Cheaper-My-Bill-at-Peak-Hour-Didnt-Move-11-16)
- [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](../articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/86) · [telegra.ph](https://telegra.ph/This-Open-Source-Code-Review-Tool-Beats-Claude--With-19-the-Tokens-11-07)
- [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](../articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/87) · [telegra.ph](https://telegra.ph/What-DeepSeek-V41-Flash-Really-Costs-Per-Month-A-Five-Step-Checklist-11-10)
- [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](../articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/92) · [telegra.ph](https://telegra.ph/Your-LLM-Bill-Is-2x-the-Sticker-Price-Peak-Hour-Pricing-and-the-272K-Token-Cliff-11-17)

**A GLM price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=GLM&title=%5Bcorrection%5D+GLM) — the form already knows it is about GLM; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
