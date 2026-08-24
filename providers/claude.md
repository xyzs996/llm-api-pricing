# Claude API pricing: what 18 models cost a coding agent

Every Claude model in the catalog that has been ranked in an agent category, priced three ways — list, cache read, and what the two come to at the token mix an agent actually sends. Recomputed from the source catalog on **2026-08-24**.

**List price is not the bill.** A coding agent re-reads its context every step, so about 95.6% of the tokens it sends are cache reads — and how deep Claude discounts a cache read decides the bill more than the number printed in the row. That discount is a vendor policy, not a per-model one, and no published rate card puts it next to the other vendors'.

## What Claude charges per million tokens

18 Claude models that have been ranked in an agent category of the Design Arena, read from [OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-08-24**. Three prices per row: what the row lists, what a cache read costs, and what the two come to at the token mix a coding agent actually sends.

**Claude charges one cache-read rate across every row that publishes one: 10% of that row's own input price.** All 18 of them use it, so within Claude the cheapest row on list price is also the cheapest row an agent actually pays — the ordering does not change. Repriced at a coding agent's mix, Claude's list input price overstates what an agent pays by a median **6.6×** — the same multiple on every row.

**2 of these 18 rows cost more than the price in their own row once the prompt is long enough.** The threshold reprices *every* token in the request, including the ones under it, so one token over the line roughly doubles the call. The thresholds are in the table.

9 rows are marked `batch` — the batch entries the catalog lists separately. They are kept apart on purpose: folding them in would read as if a normal call cost half of what it does.

| $ / 1M at agent mix | $ in / 1M | $ cache read / 1M | $ out / 1M | Model | Context | Long-context step | Best agents rank |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **$0.1508** | $1.00 | $0.10 | $5.00 | [Claude Sonnet 5](https://openrouter.ai/anthropic/claude-sonnet-5:batch) `batch` | 1M | — | #4 godotgamedev |
| **$0.2263** | $1.50 | $0.15 | $7.50 | [Claude Sonnet 4.5](https://openrouter.ai/anthropic/claude-sonnet-4.5:batch) `batch` | 1M | $3.00 past 200k | #25 mobileapps |
| **$0.2263** | $1.50 | $0.15 | $7.50 | [Claude Sonnet 4.6](https://openrouter.ai/anthropic/claude-sonnet-4.6:batch) `batch` | 1M | — | #5 mobileapps |
| **$0.3017** | $2.00 | $0.20 | $10.00 | [Claude Sonnet 5](https://openrouter.ai/anthropic/claude-sonnet-5) | 1M | — | #4 godotgamedev |
| **$0.3771** | $2.50 | $0.25 | $12.50 | [Claude Opus 4.5](https://openrouter.ai/anthropic/claude-opus-4.5:batch) `batch` | 200K | — | #11 mobileapps |
| **$0.3771** | $2.50 | $0.25 | $12.50 | [Claude Opus 4.6](https://openrouter.ai/anthropic/claude-opus-4.6:batch) `batch` | 1M | — | #6 mobileapps |
| **$0.3771** | $2.50 | $0.25 | $12.50 | [Claude Opus 4.7](https://openrouter.ai/anthropic/claude-opus-4.7:batch) `batch` | 1M | — | #1 agenticslides |
| **$0.3771** | $2.50 | $0.25 | $12.50 | [Claude Opus 4.8](https://openrouter.ai/anthropic/claude-opus-4.8:batch) `batch` | 1M | — | #2 agenticslides |
| **$0.3771** | $2.50 | $0.25 | $12.50 | [Claude Opus 5](https://openrouter.ai/anthropic/claude-opus-5:batch) `batch` | 1M | — | #3 fullstack |
| **$0.4525** | $3.00 | $0.30 | $15.00 | [Claude Sonnet 4.5](https://openrouter.ai/anthropic/claude-sonnet-4.5) | 1M | $6.00 past 200k | #25 mobileapps |
| **$0.4525** | $3.00 | $0.30 | $15.00 | [Claude Sonnet 4.6](https://openrouter.ai/anthropic/claude-sonnet-4.6) | 1M | — | #5 mobileapps |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Fable 5](https://openrouter.ai/anthropic/claude-fable-5:batch) `batch` | 1M | — | #1 agenticgamedev |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Opus 4.5](https://openrouter.ai/anthropic/claude-opus-4.5) | 200K | — | #11 mobileapps |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Opus 4.6](https://openrouter.ai/anthropic/claude-opus-4.6) | 1M | — | #6 mobileapps |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Opus 4.7](https://openrouter.ai/anthropic/claude-opus-4.7) | 1M | — | #1 agenticslides |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Opus 4.8](https://openrouter.ai/anthropic/claude-opus-4.8) | 1M | — | #2 agenticslides |
| **$0.7542** | $5.00 | $0.50 | $25.00 | [Claude Opus 5](https://openrouter.ai/anthropic/claude-opus-5) | 1M | — | #3 fullstack |
| **$1.5084** | $10.00 | $1.00 | $50.00 | [Claude Fable 5](https://openrouter.ai/anthropic/claude-fable-5) | 1M | — | #1 agenticgamedev |

Cheapest Claude row an agent can call normally is **Claude Sonnet 5** at $0.3017 per million; the dearest is $1.5084, 5× more. Both numbers exclude the `batch` rows above. Both are computed, not quoted — the arithmetic and the weights are in the JSON.


## Claude against the other vendors, on the same arithmetic

Same catalog, same day, same token mix. The column that decides an agent's bill is not the list price — it is how deep that vendor discounts a cache read, because about 95.6% of what an agent sends is a cache read.

| Vendor | Rows | Cache read, % of its own input | List price overstates the agent bill by | Cheapest non-`batch` row at agent mix |
| --- | --- | --- | --- | --- |
| DeepSeek | 1 | 8.3% | 7.9× | $0.0664 |
| **Claude** | 18 | 10% | 6.6× | $0.3017 |
| Gemini | 10 | 10% | 6.6× | $0.0566 |
| OpenAI | 9 | 10–10.4% | 6.3× | $0.2042 |
| Llama | 2 | 12% | 6.0× | $0.2067 |
| Qwen | 2 | 12.5–20% | 5.0× | $0.3379 |
| Grok | 4 | 15–25% | 5.0× | $0.2494 |
| Kimi | 5 | 10–25.4% | 4.7× | $0.0918 |
| GLM | 7 | 18.6–20% | 4.1× | $0.0979 |
| MiniMax | 2 | 20% | 4.1× | $0.0731 |

The spread in that fourth column is the whole point: Claude at 6.6× against GLM at 4.1×, across 18 and 7 rows. Two rows with the *same* list price, one from each, are not the same price to an agent — and no published rate card puts those two numbers next to each other.


[All models, every vendor, one table](../prices.md) · [Put your own token counts in](https://xyzs996.github.io/llm-cost-calculator/) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

## What was written about Claude while these were measured

18 figures in these field notes come from a sentence that names Claude. These are quoted from the write-up, dated the day it went out — unlike the table above, they are **not** recomputed, so read each one as of its own date.

- **20%** — “Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **20%** — “So this is Alibaba's own policy against Anthropic's own policy, 20% against 10%, with no reseller standing in between adding a markup I would have mistaken for a vendor decision.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10.00%** — “Claude Sonnet 5 is resold through nine storefronts including AWS Bedrock, Azure and Google, and all nine bill a cache read at exactly 10.00% of their own input price.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10.00%** — “Claude Sonnet 5 has nine, and all nine bill 10.00%.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **10%** — “Anthropic, Google and OpenAI each charge 10% of input for a cache read — flat, every model, and stable across sellers too.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$355.00** — “Run the billion tokens through: Qwen3.7 Max bills $355.00, Claude Sonnet 5 bills $301.68.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **$2.00** — “Claude Sonnet 5 lists at $2.00.” (2026-08-24) [→](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)
- **80%** — “For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency.” (2026-08-22) [→](../articles/claude-code-and-codex-for-office-automation.md)
- **80%** — “When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks.” (2026-08-20) [→](../articles/why-stripping-80-of-system-prompts-actually-improved-claude.md)
- **$1.25 per million** — “Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1.” (2026-08-19) [→](../articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md)
- **400 tokens** — “Anthropic's SKILL.md file is 400 tokens of aesthetic guidance and a two-pass working method, and it has been installed over 1.08 million times — a return on 400 tokens that argues taste-shaping is worth more than tool-building, at least in front-end generation.” (2026-08-10) [→](../articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- **$19 billion** — “Anthropic's $19 billion data center lease locks in five to eight years of compute, which reframes the competition as a contest over power and floor space rather than architecture.” (2026-08-10) [→](../articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- **$1.25 per million input tokens** — “Meta's Muse Spark 1.1 agent model API is priced at $1.25 per million input tokens and $4.25 per million output tokens — roughly 75% and 83% below Anthropic Opus on input and output respectively — and the target is explicit: become the cheap entry point for agent workflows and pull developers into the ecosystem.” (2026-08-10) [→](../articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- **80%** — “Claude Code's team discovered that removing 80% of system prompts actually improved programming performance, revealing how excessive model constraints can hinder rather than help AI effectiveness.” (2026-08-07) [→](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)
- **400-token** — “Anthropic's 400-token SKILL.md file, through its "two-pass workflow" and specific aesthetic guidance, has achieved over 1 million installations, proving that aesthetic direction is more useful than mere tool innovation.” (2026-08-07) [→](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)
- **400 tokens** — “Anthropic's SKILL.md file runs about 400 tokens, uses a two-pass approach with specific aesthetic guidance, and has passed 1.08 million installations.” (2026-08-05) [→](../articles/ai-model-costs-beyond-per-token-pricing.md)
- **$19 billion** — “Anthropic signed a data center lease reported at $19 billion, which is the kind of commitment that only makes sense if compute, not model architecture, is the constraint that decides who is still standing in five years.” (2026-08-05) [→](../articles/ai-model-costs-beyond-per-token-pricing.md)
- **$19 billion** — “Anthropic is not signing a $19 billion lease in order to cut prices in the next 12 months.” (2026-08-05) [→](../articles/ai-model-costs-beyond-per-token-pricing.md)

[All 493 figures, every kind](../figures.md)

- [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](../articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/12) · [telegra.ph](https://telegra.ph/16-Billion-Free-Tokens-Is-a-Compression-Ratio-Not-a-Strategy-08-19)
- [AI Model Costs: Beyond Per-Token Pricing](../articles/ai-model-costs-beyond-per-token-pricing.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/20) · [telegra.ph](https://telegra.ph/Beyond-Token-Pricing-How-Indie-Devs-Should-Really-Evaluate-AI-Model-Costs-08-19)
- [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](../articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)
- [Claude Code and Codex for Office Automation](../articles/claude-code-and-codex-for-office-automation.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/59) · [telegra.ph](https://telegra.ph/Office-Automation-with-Claude-Code-and-Codex-08-23)
- [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/10) · [telegra.ph](https://telegra.ph/How-Chinese-AI-Agent-Tools-Leverage-16-Billion-Free-Tokens-08-19)
- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](../articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/51) · [telegra.ph](https://telegra.ph/The-Token-Cost-War-Why-Price-per-Million-Tokens-Now-Decides-the-AI-Market-08-23)
- [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](../articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/40) · [telegra.ph](https://telegra.ph/Why-Stripping-80-of-System-Prompts-Actually-Improved-Claude-Codes-Performance-08-21)

**A Claude price that looks wrong?** [Say which row](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=Claude&title=%5Bcorrection%5D+Claude) — the form already knows it is about Claude; you only have to say what the number is now. Every figure here is computed from a published catalog, so a wrong one is a bug, not an opinion.

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — the data is CC BY and does not require starring.

---

[All write-ups](../README.md)
