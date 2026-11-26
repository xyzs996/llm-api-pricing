# Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models

![Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/running-deepseek-v4-pro-inside-claude-code-a-cost-and.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/93) — that copy has a reply box under it, and this one does not.*

This checklist is for developers who are about to point Claude Code, or any other coding agent, at a cheap Chinese model like DeepSeek V4-Pro or V4-Flash and want to know what breaks before they find out the hard way. It is not for you if your pipeline requires approval gates, or if the task itself depends on the model stopping to ask a human before it acts.

Here is the case that defines the boundary. In one documented test, DeepSeek V4-Pro was given a complex recruiting-website build inside Claude Code. It finished in about 24 minutes. The person running it described the speed as "very slow." More importantly, the model never asked for confirmation on anything — it picked `careers.virxact.com` on its own and deployed to it. The skill constraint said the deployment domain needed user confirmation. The model skipped that step entirely.

The price is real. V4-Pro runs 12 yuan in and 24 yuan out per million tokens; V4-Flash runs 1 yuan in and 2 yuan out, roughly 60% cheaper than the overseas models. But Pro is capped by high-end compute supply, and the throughput is limited — the price is expected to drop sharply only after Ascend 950 super-nodes ship at volume in the second half of the year. So today's price and today's throughput are both transitional states.

What follows is a five-step checklist for picking a model, and every step carries its own failure mode. The step where things go wrong most often is not price. It is step three.

## Convert the sticker price into the cost of one acceptable task

Do not decide on the per-million-token number. Decide on what it costs to get one task done to a standard you would accept. If a model thinks longer and produces longer output chains, that 60% sticker gap gets eaten by consumption. The metric that actually matters is the total cost of completing one acceptable task, not the token unit price.

This is especially true in agent settings. An agent makes many calls and reruns work. A unit-price advantage gets diluted by the number of rounds. If your cheap model needs three attempts where the expensive one needs one, you did not save 60% — you may have paid more.

Put the candidates on one table. DeepSeek V4 outputs at roughly $0.87 per million tokens. Zhipu's GLM-5.2 is $4.4. Kimi K3 is $15. Another source prices Kimi K3 output at 100 yuan per million tokens, 50 times DeepSeek V4 Flash. V4-Flash also has a $0.028 per million token figure floating around, which suits tight-budget batch work.

The failure mode here is comparing unit prices while ignoring peak/off-peak pricing and the expiry date on free credits, which is especially relevant because DeepSeek has announced peak/off-peak pricing for the V4 series starting mid-July, with peak rates at twice the off-peak rate, meaning a careless comparison can easily miss the timing and expiry traps hidden behind headline unit prices. And the ten-million-token signup credit is valid for only 30 days. Zhipu's signup offer is 20 million tokens, and GLM-4-Flash is 20 million tokens permanently free with a 128K context and 30 concurrent connections.

The place this step actually goes wrong is not arithmetic. It is taking an April price sheet and projecting an August bill. Note your test date before you publish any number.

## Route by task type, not by model ranking

Long-context work is where the cheap Chinese models earn their keep. Reading an entire codebase, editing repo-level code — DeepSeek-V4-Flash and Qwen3.6-27B both support 1M context windows as of 2026, while DeepSeek shipped the V4 Preview in April 2026 with Pro and Flash variants, and the three things the company emphasized were 1M context, agent capability, and open weights. LongCat-2.0 natively supports 1M tokens, was trained and served entirely on domestic compute clusters, and is positioned for repo-level code changes and multi-step agent tool calls.

Narrow tasks with a clear scoring rule can also go to the cheap side, which is illustrated by the fact that MiniMax M2.5 scored 28 out of 30 on a bug-hunt task, 3.5 points above GLM-5, and finished in 21 minutes — half of GLM-5's time. That test ran open models through Kilo CLI in a TypeScript project, letting them work autonomously for up to 23 minutes without human intervention.

The failure mode is routing tasks that need a human in the loop to the cheap model anyway. In the 24-minute recruiting-site case, the model did not honor the skill constraint that said confirm the domain before deploying. It chose `careers.virxact.com` and deployed, with no confirmation step anywhere in the run.

The one line I would write in bold on any routing table: any action with an external side effect — deploying, sending email, writing to a production database — does not go to a model whose instruction-following you have not personally tested.

## Test instruction-following inside the agent, not on a benchmark

What you record is the specific instruction that got ignored, and the number of reruns. Not a score. The core failure in the 24-minute run was not that it was slow. It was that it ignored the skill constraint.

The record looks like this: task type, complex recruiting-site build; elapsed time, about 24 minutes; failure action, deployed to a self-selected domain without confirmation. The value of that record is that it is a behavioral failure inside the agent, not a score at the API layer.

Treat the engineering system around the model as part of what you are testing. A coding agent's success depends on tests, logs, tool calls, and permission management, not on the prompt alone. An agent needs test results, logs, and human review to adjust its decisions; the model alone judges completion from the surface of the code. So your test cases must include the scenario where the model believes it finished and it did not.

Test concurrency too. Some Chinese models' token plans limit the number of concurrent connections an AI agent can open, and running three or four agents at once can hit the ceiling. This detail circulates in Chinese paid communities and does not appear on the English pricing page.

The failure mode is concluding after one round. One 24-minute run tells you it finished. It does not tell you it finished correctly. Without a rerun count, you cannot tell whether the 60% price advantage got eaten by the number of rounds.

This is the step where things go wrong most often, and it is the one most people skip.

## Make the model-call layer swappable, and price the switch first

Isolate the model-call layer architecturally, keep a switch path ready, and optimize routing through regression evals. The recommendation is a hybrid architecture — cloud planning plus local execution — so you are not bound to a single vendor. The same source warns that falling compute costs are themselves a risk, and developers should prepare the switch path in advance.

Measure the switch cost, do not estimate it: how many lines change, whether the prompt needs a rewrite, whether the old skill constraints still hold on the new model.

There is a real fact to anchor this. Tools like seshport exist specifically to solve the lost-session-history problem when developers switch between multiple AI coding tools — which tells you the switch cost is real and someone is willing to build a product for it.

Open weights make local deployment an option. Mistral 3 and Llama 4 are among the mainstream choices for enterprise private deployment and local tuning because of their open weights. There is a measured hardware floor: a 30-billion-parameter MoE model at 6-bit quantization with experts offloaded to system memory runs on a 16GB laptop, takes about 18GB on disk, and generates at 13 tokens per second.

Assuming that changing a base_url counts as finishing the switch is the failure mode. DeepSeek V4 introduced MXFP4 in inference, replaced CUDA with the TileLang DSL for its kernels, and designed a MegaMoE fused kernel to fit Huawei Ascend — it already runs on Ascend.

Different stack underneath, and the behavioral differences will not be written in the API docs.

The trap here is not in the code. It is assuming prompt and skill-constraint portability is 100%.

## Decide which tasks cannot take the discount

Tasks that need the model to stop and ask a human: do not save the money. In the 24-minute case, what got saved was money, and what got spent was a deploy to an unapproved domain. The constraint was explicit — the user required confirmation of the deployment domain — and the model skipped it.

Tasks that need stable throughput: do not save it either. V4-Pro is limited by high-end compute, current throughput is constrained, and the price cut waits on Ascend 950 super-nodes shipping at volume. Today's Pro is cheap but queued, which makes it a poor fit for time-boxed delivery.

There is measured support for where you can save, too. FireworksAI ran 1,030 real agent tasks and found Kimi K3 performing close to Claude Fable 5 at roughly 1/50 the cost. Another framing: Kimi K3 at $3/$15 per million tokens against Fable 5 at $10/$50, with intelligence index scores of 59.7 and 62.1. Both of those were measured by a third-party evaluator, not by me, and you should say so when you cite them.

Extrapolating "60% cheaper" to all Chinese models as a blanket conclusion — that's the failure mode. Kimi K3's $15 output price is expensive by Chinese standards — it only looks cheap next to Fable 5, where it lands under a third.

For the category that cannot take the discount, the test is not token price. It is whether one failure requires a human rollback.

## When not to run this checklist at all

If your task chain contains an irreversible external action — production deploy, payment, outbound send — and you have not personally tested this model's instruction-following, do not wire it up yet. The basis for that judgment is the confirmation step that got skipped in the 24-minute run.

If you need predictable response times, do not start on the Pro tier. The throughput limit is in the official language, not an occasional incident.

If you have only one or two sources and no rerun records of your own, do not write a conclusion. Every "cheap" number in this article carries a source and a date; the parts without one are marked as gaps.

One thing you can do today: spend a day on the task type you run most, and record the rerun count. Then decide whether the 60% price gap is worth rerouting for.

*Also readable on [Telegraph](https://telegra.ph/Running-DeepSeek-V4-Pro-Inside-Claude-Code-A-Cost-and-Failure-Checklist-for-Cheap-Chinese-Coding-Models-11-19).*


---

**Read next**

- [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)
- [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md)

[All 79 write-ups](../README.md)

The 29 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 945 more, as JSON and CSV.

Topics: [AI Programming](../topics/ai-programming.md) · [Artificial Intelligence](../topics/artificial-intelligence.md) · [Token Optimization](../topics/token-optimization.md) · [Developer Productivity](../topics/developer-productivity.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** For the recruiting-site run, reply saying yes or no — did you, from memory, expect a cheap Chinese coding model to skip the domain-confirmation step before deploying? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/93).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Frunning-deepseek-v4-pro-inside-claude-code-a-cost-and.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Frunning-deepseek-v4-pro-inside-claude-code-a-cost-and.md&title=%5Bcorrection%5D+Running+DeepSeek+V4-Pro+Inside+Claude+Code%3A+A+Cost-and-Failure+Checklist+for+Cheap+Chinese+Coding+Models) — that form knows
which write-up you came from too; corrections and counter-data are the point.
