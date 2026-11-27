# AI Programming

15 of the 80 write-ups here are tagged AI Programming. Every figure quoted below is in the [figures table](../figures.md) with the sentence it came from.

## The figures

- **$3** — A developer running three agents for daily work — email, calendar, research — reported a real cost of roughly $3–5 per month on DeepSeek V4 Flash, against $200–260 per month for the same workload on Opus 4.7. [→](../articles/deepseek-s-peak-hour-price-is-double-how-to-schedule-your.md)
- **$3** — At $3–5, the savings are a few dollars, and the engineering — scheduler changes, retry handling, a queue, monitoring for jobs that did not fire — costs more than it returns. [→](../articles/deepseek-s-peak-hour-price-is-double-how-to-schedule-your.md)
- **$60** — The $60 applies to DeepSeek V4.1 Flash as a model, not as a general-purpose wallet you can spend across whatever OpenCode hosts, and because this credit does not follow you there if your agent workflow leans on a second model for a specific step, it stays tied to that one model rather than extending to any other model your workflow might call on. [→](../articles/the-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md)
- **$60** — Here is my read, and it is a read rather than a measurement — namely that $60 of credit is enough for an independent developer running a few hours a day at medium task granularity, whereas if you leave an agent running batches all day, the 5-hour window will reach you before the credit does. [→](../articles/the-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md)
- **$0.87** — If you think in dollars, another data point puts DeepSeek V4 at $0.87 per million output tokens, against GLM-5.2 at $4.4 and Kimi K3 at $15, while a third puts V4-Flash at $0.028 per million tokens, which is an order of magnitude off the previous figures. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$0.87** — In dollar terms the same source group puts DeepSeek V4 output at $0.87 per million tokens against GLM-5.2 at $4.4 and Kimi K3 at $15, which is the other half of why the cheap tier is where I start. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$3** — Those numbers aren't marketing, because they show up in real monthly bills, where one developer running three agents for email, calendar, and research put DeepSeek V4 Flash at roughly $3–5 per month against Opus 4.7 at $200–260 — with what they described as a small quality gap. [→](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- **$0.26** — DeepSeek V3.2 under the OpenClaw framework comes in at $0.26 per million input tokens and $0.38 output, the lowest-cost model in that particular comparison, while MiniMax M2.7 sits at $0.30 input and $1.20 output with a 204.8K context window, built for coding and agent workflows. [→](../articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)

[All figures, 978 rows](../figures.md)

## The write-ups

### [DeepSeek's Peak-Hour Price Is Double — How to Schedule Your Batch Agent Jobs Around It](../articles/deepseek-s-peak-hour-price-is-double-how-to-schedule-your.md)

This one is for independent developers running batch coding agent jobs and paying per token.

[telegra.ph](https://telegra.ph/DeepSeeks-Peak-Hour-Price-Is-Double--How-to-Schedule-Your-Batch-Agent-Jobs-Around-It-11-27)

### [The DeepSeek Quota Math Nobody Publishes: $10/Month, Peak-Hour Doubling, or a 3-Million-Yuan Server](../articles/the-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md)

On September 25, 2026, OpenCode announced that the $60 of DeepSeek V4.1 Flash credit bundled with its $10 monthly plan was no longer a limited-time promotion.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/98) · [telegra.ph](https://telegra.ph/The-DeepSeek-Quota-Math-Nobody-Publishes-10Month-Peak-Hour-Doubling-or-a-3-Million-Yuan-Server-11-26)

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

### [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](../articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)

Qwen3.8-Flash lists 0.2 yuan per million input tokens and 2 yuan per million output tokens.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/91) · [telegra.ph](https://telegra.ph/The-Sticker-Price-Said-9x-Cheaper-My-Bill-at-Peak-Hour-Didnt-Move-11-16)

### [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](../articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md)

"DeepSeek V4.1 Flash is 3 yuan per million input tokens off-peak and 9 yuan output — cheap enough to run anything." That sentence is true on the price sheet.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/89) · [telegra.ph](https://telegra.ph/The-Listed-Price-Is-a-Lie-What-DeepSeeks-PeakOff-Peak-Pricing-Rate-Limit-Windows-and-Permanent-Credits-Actually-Cost-Per-Task-11-13)

### [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](../articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md)

In January 2026, an indie developer shipped an iOS app using Claude Code as the primary development assistant, letting the agent handle everything from backend API design to the SwiftUI frontend.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/88) · [telegra.ph](https://telegra.ph/Shipping-a-SwiftUI-App-with-AI-Where-It-Shines-and-Where-It-Crashes-11-11)

### [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](../articles/how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md)

In July 2026, Alibaba open-sourced Open Code Review.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/82) · [telegra.ph](https://telegra.ph/How-Alibabas-Open-Code-Review-Slashed-AI-Code-Review-Costs-by-90--And-What-It-Means-for-Independent-Developers-10-01)

### [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](../articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md)

If you're hitting the 5-hour Codex limit like clockwork every day, stop counting minutes.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/81) · [telegra.ph](https://telegra.ph/Bypass-Codex-Rate-Limits-The-Local-Proxy-Path-to-70-Cost-Savings-09-30)

### [Best Practices for AI Agent Skill Management](../articles/best-practices-for-ai-agent-skill-management.md)

Managing AI Agent skills is not merely about tools; it's about designing workflows to boost your productivity.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/18) · [telegra.ph](https://telegra.ph/Best-Practices-for-AI-Agent-Skill-Management-08-21)

### [Why Pi's 1000-Token Agent Engine Needs a Sandbox Before You Touch It](../articles/why-pi-s-1000-token-agent-engine-needs-a-sandbox-before-you.md)

Pi's system prompt and its 4 tool descriptions come to under 1,000 tokens, which is the whole reason to like it.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/39) · [telegra.ph](https://telegra.ph/Why-Pis-1000-Token-Agent-Engine-Needs-a-Sandbox-Before-You-Touch-It-08-19)

### [The First Line of Defense in AI Programming: Environment Variable Management](../articles/the-first-line-of-defense-in-ai-programming-environment.md)

MonkeyCode ships with 900 million free tokens and supports private deployment, which tells you exactly what its users are doing: pointing an AI coding tool at their own keys, on their own infrastru…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/33) · [telegra.ph](https://telegra.ph/The-First-Line-of-Defense-in-AI-Programming-Environment-Variable-Management-08-19)

### [Why Your AI Agent Goes Off the Rails: Give It Boring Work First](../articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.md)

One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology:…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/54) · [telegra.ph](https://telegra.ph/Why-Your-AI-Agent-Goes-Off-the-Rails-Give-It-Boring-Work-First-08-23)

---

[All 80 write-ups](../README.md)

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=topics%2Fai-programming.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=topics%2Fai-programming.md) — corrections and counter-data are the point.
