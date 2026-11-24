# Token Optimization

9 of the 78 write-ups here are tagged Token Optimization. Every figure quoted below is in the [figures table](../figures.md) with the sentence it came from.

## The figures

- **$0.87** — If you think in dollars, another data point puts DeepSeek V4 at $0.87 per million output tokens, against GLM-5.2 at $4.4 and Kimi K3 at $15, while a third puts V4-Flash at $0.028 per million tokens, which is an order of magnitude off the previous figures. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$0.87** — In dollar terms the same source group puts DeepSeek V4 output at $0.87 per million tokens against GLM-5.2 at $4.4 and Kimi K3 at $15, which is the other half of why the cheap tier is where I start. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$3** — Those numbers aren't marketing, because they show up in real monthly bills, where one developer running three agents for email, calendar, and research put DeepSeek V4 Flash at roughly $3–5 per month against Opus 4.7 at $200–260 — with what they described as a small quality gap. [→](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- **$0.26** — DeepSeek V3.2 under the OpenClaw framework comes in at $0.26 per million input tokens and $0.38 output, the lowest-cost model in that particular comparison, while MiniMax M2.7 sits at $0.30 input and $1.20 output with a 204.8K context window, built for coding and agent workflows. [→](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- **$3** — One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day. [→](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- **$0.30** — Compare MiniMax M2.7 at $0.30 in and $1.20 out with 204.8K context, where the output spread is compressed and the pricing is easier to reason about for multi-turn agent work. [→](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- **$3** — Another framing: Kimi K3 at $3/$15 per million tokens against Fable 5 at $10/$50, with intelligence index scores of 59.7 and 62.1. [→](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- **$15** — Kimi K3's $15 output price is expensive by Chinese standards — it only looks cheap next to Fable 5, where it lands under a third. [→](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)

[All figures, 950 rows](../figures.md)

## The write-ups

### [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](../articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)

Chinese AI agent tools offer a game-changing strategy for independent developers to access a massive pool of 1.6 billion free tokens monthly.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/10) · [telegra.ph](https://telegra.ph/How-Chinese-AI-Agent-Tools-Leverage-16-Billion-Free-Tokens-08-19)

### [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)

DeepSeek V4-Pro took 24 minutes to build a recruiting site inside Claude Code, then skipped the skill constraint that said it must confirm the deployment domain with the user, because it picked `ca…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/97) · [telegra.ph](https://telegra.ph/I-Ran-DeepSeek-V4-Pro-and-GLM-4-Flash-in-the-Same-Coding-Agent-One-Took-24-Minutes-and-Deployed-Without-Asking-11-24)

### [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)

Just pick the model with the lowest per-million-token price — that's how you keep your agent bill down — but that advice breaks the moment your agent touches any of three structural traps: time-of-…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/96) · [telegra.ph](https://telegra.ph/The-Same-Model-Costs-2x-More-at-10am--Three-Pricing-Cliffs-That-Blow-Up-Your-Coding-Agents-Bill-11-23)

### [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)

DeepSeek V3.2 costs $0.26 per million input tokens and $0.38 per million output tokens.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/95) · [telegra.ph](https://telegra.ph/The-Cheap-Model-Is-50x-Cheaper-Until-It-Gets-Banned-Real-Per-Token-Costs-vs-What-Actually-Breaks-11-20)

### [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](../articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)

This checklist is for developers who are about to point Claude Code, or any other coding agent, at a cheap Chinese model like DeepSeek V4-Pro or V4-Flash and want to know what breaks before they fi…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/93) · [telegra.ph](https://telegra.ph/Running-DeepSeek-V4-Pro-Inside-Claude-Code-A-Cost-and-Failure-Checklist-for-Cheap-Chinese-Coding-Models-11-19)

### [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](../articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md)

In September and October 2026, a run of Chinese-language model price sheets started circulating with a line at the top that English cost write-ups still don't have: these are off-peak prices.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/92) · [telegra.ph](https://telegra.ph/Your-LLM-Bill-Is-2x-the-Sticker-Price-Peak-Hour-Pricing-and-the-272K-Token-Cliff-11-17)

### [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](../articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)

Qwen3.8-Flash lists 0.2 yuan per million input tokens and 2 yuan per million output tokens.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/91) · [telegra.ph](https://telegra.ph/The-Sticker-Price-Said-9x-Cheaper-My-Bill-at-Peak-Hour-Didnt-Move-11-16)

### [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](../articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md)

OmniRoute aggregates 237 providers and advertises roughly 1.6 billion free tokens a month, and that figure is arithmetic rather than a promotion, because the RTK+Caveman layer compresses 10,000 tok…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/12) · [telegra.ph](https://telegra.ph/16-Billion-Free-Tokens-Is-a-Compression-Ratio-Not-a-Strategy-08-19)

### [Token Optimization for Indie Developers' AI API Bills](../articles/token-optimization-for-indie-developers-ai-api-bills.md)

In July 2026, while indie developers building AI coding products full-time watched their API burn rate climb toward their revenue, a quieter shift in the Chinese developer stack showed a different…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/37) · [telegra.ph](https://telegra.ph/Token-Optimization-for-Indie-Developers-AI-API-Bills-08-19)

---

[All 78 write-ups](../README.md)

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=topics%2Ftoken-optimization.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=topics%2Ftoken-optimization.md) — corrections and counter-data are the point.
