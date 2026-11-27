# AI Agents

5 of the 80 write-ups here are tagged AI Agents. Every figure quoted below is in the [figures table](../figures.md) with the sentence it came from.

## The figures

- **$0.87** — If you think in dollars, another data point puts DeepSeek V4 at $0.87 per million output tokens, against GLM-5.2 at $4.4 and Kimi K3 at $15, while a third puts V4-Flash at $0.028 per million tokens, which is an order of magnitude off the previous figures. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$0.87** — In dollar terms the same source group puts DeepSeek V4 output at $0.87 per million tokens against GLM-5.2 at $4.4 and Kimi K3 at $15, which is the other half of why the cheap tier is where I start. [→](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- **$3** — One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day. [→](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- **$0.30** — Compare MiniMax M2.7 at $0.30 in and $1.20 out with 204.8K context, where the output spread is compressed and the pricing is easier to reason about for multi-turn agent work. [→](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- **40%** — 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. [→](../articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md)
- **1,000 tokens** — Its original system prompt and tool descriptions came to under 1,000 tokens. [→](../articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md)
- **300 million tokens** — One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology: 300 million tokens on day one, about 200 million on day two, about 100 million on day three. [→](../articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.md)
- **3 weeks** — Version your skills like software. treats AI skills as packages with rollback and permission control, which is the difference between a team that can undo a bad change and a team whose output quality quietly degrades because somebody edited a prompt in place 3 weeks ago. [→](../articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.md)

[All figures, 978 rows](../figures.md)

## The write-ups

### [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](../articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)

DeepSeek V4-Pro took 24 minutes to build a recruiting site inside Claude Code, then skipped the skill constraint that said it must confirm the deployment domain with the user, because it picked `ca…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/97) · [telegra.ph](https://telegra.ph/I-Ran-DeepSeek-V4-Pro-and-GLM-4-Flash-in-the-Same-Coding-Agent-One-Took-24-Minutes-and-Deployed-Without-Asking-11-24)

### [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](../articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)

DeepSeek V3.2 costs $0.26 per million input tokens and $0.38 per million output tokens.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/95) · [telegra.ph](https://telegra.ph/The-Cheap-Model-Is-50x-Cheaper-Until-It-Gets-Banned-Real-Per-Token-Costs-vs-What-Actually-Breaks-11-20)

### [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](../articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md)

"If your AI keeps writing bad code, you need a better model." In each of the rebuilds below, a new model wouldn't have fixed anything, because the model was reading the wrong thing.

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/77) · [telegra.ph](https://telegra.ph/Your-AI-Didnt-Misread-Your-Code-by-Accident-You-Handed-It-the-Wrong-Context-09-25)

### [One Person, 8 AI Agents, 3,000 Baseball Caps in Two Months](../articles/one-person-8-ai-agents-3-000-baseball-caps-in-two-months.md)

Zhang Qianchao runs a custom baseball cap export business on Alibaba.com with 8 AI agents and no employees, and in 2 months he shipped 3,000 caps to buyers across Europe, the Americas and South Ame…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/60) · [telegra.ph](https://telegra.ph/One-Person-8-AI-Agents-3000-Baseball-Caps-in-Two-Months-08-23)

### [Why Your AI Agent Goes Off the Rails: Give It Boring Work First](../articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.md)

One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology:…

[reply box](https://github.com/xyzs996/llm-api-pricing/discussions/54) · [telegra.ph](https://telegra.ph/Why-Your-AI-Agent-Goes-Off-the-Rails-Give-It-Boring-Work-First-08-23)

---

[All 80 write-ups](../README.md)

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=topics%2Fai-agents.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=topics%2Fai-agents.md) — corrections and counter-data are the point.
