# AI Model Costs: Beyond Per-Token Pricing

![AI Model Costs: Beyond Per-Token Pricing](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/ai-model-costs-beyond-per-token-pricing.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/20) — that copy has a reply box under it, and this one does not.*

Microsoft's evaluation of Kimi K3 landed on a number that should change how you read a pricing page: about 60 percent of the cost difference between models comes from the thinking depth a task requires, not from the price per token. That is the whole argument in one line. The number on the landing page is the smallest of the two variables you are actually paying for.

Here is what thinking depth costs in practice, why project context rather than generated code drives most of the bill, and what the $1-per-million tier tells you about where this market is heading.

## The 60 Percent Nobody Prices In

Two models can advertise the same rate and bill you differently for the same task, because one of them takes more turns to get to an acceptable answer. Microsoft's testing puts that effect at roughly 60 percent of the observed cost spread, which makes it the dominant term and the unit price the correction.

I find this easy to believe and hard to act on, which is the awkward part. The gap between the two is probably where most cost-control plans quietly die.

Thinking depth is not published. No vendor lists average turns to completion, partly because it depends entirely on your task and partly because it is not a flattering number. So the only way to know is to run the same task on two models and compare the total spend to a working result, which most indie developers never do because it feels like a detour from shipping. It is a detour that pays for itself in the first month or two, and to be fair the reason it gets skipped is obvious enough, since a benchmark run produces no feature at the end of the afternoon.

OpenAI Codex's Record and Replay feature shows the same effect from a different angle. Token efficiency there varies noticeably depending on how the task is structured, which means the shape of your prompt and workflow moves the bill independently of which model you picked. The task design is a cost lever, and it is the one you fully control.

Anthropic's research points at a structural reason some of this happens. Models like Claude develop internal conceptual patterns while working, and that process consumes tokens that never appear as output you can read. You are paying for reasoning that leaves no trace in the file it produced.

## Where the Tokens Actually Go

Most developers assume the bill tracks the code the model writes for them. It does not.

The bulk of consumption in an AI coding assistant comes from re-reading project context every round. Test results, error logs, previous edits, and the files the model needs to see before it can safely change anything all become input on the next turn. Generated code is short. The context in front of it is not, and it grows with the project rather than with the task.

This has an unpleasant implication for anyone who compares models on a toy benchmark. A 60 percent price advantage measured on an isolated function can disappear entirely in a real repository, because the cheap model reads the same context the expensive one does and then needs another round to get it right. The advantage was never in the unit price; it was in how many times each model had to look.

The practical response is to make your model-calling layer swappable, so that routing a lighter task to a cheaper model is a configuration change rather than a rewrite. That routing rule should come from measurement rather than instinct: run the same task on both, compare output quality against total spend, then write the rule down. I suspect the split ends up less flattering to the cheap model than most people expect, and that the tasks which genuinely tolerate a weaker model are narrower than they look, arguably closer to formatting and boilerplate than to anything touching program state.

Prompt design matters here more than the token count suggests. Anthropic's SKILL.md file runs about 400 tokens, uses a two-pass approach with specific aesthetic guidance, and has passed 1.08 million installations. A 400-token file at that install count is worth staring at for a moment, because it says the effective intervention was guidance rather than tooling, and it cost almost nothing per call to apply.

## What the $1 Tier Says About the Market

The high end of the open-weight market has settled around a recognizable price. DeepSeek V4 Pro and GLM5.2 charge roughly $1 per million tokens and reportedly run at a 10 to 20 percent margin.

That margin is the interesting figure, not the dollar.

Ten to twenty percent is a commodity margin. It tells you these vendors are competing on price against each other rather than extracting rent from a capability nobody else has, and it means there is not much room left to fall. If you have been waiting for inference prices to drop another order of magnitude before committing to an architecture, this is the number that argues against waiting, at least at this tier.

The free end tells a similar story from the other side. MonkeyCode's free tier includes 900 million tokens, which is more than most competing coding tools offer and more than a solo developer working normally will exhaust. When a serious allocation is being given away, the token itself is not the scarce resource.

What is scarce sits one layer down. Anthropic signed a data center lease reported at $19 billion, which is the kind of commitment that only makes sense if compute, not model architecture, is the constraint that decides who is still standing in five years. My reading, and I could be wrong about the timing, is that the $1 tier holds while that build-out is being financed and that the pressure surfaces later as capacity limits rather than as price rises. Anthropic is not signing a $19 billion lease in order to cut prices in the next 12 months.

For a solo developer the defensive move is the same either way. Do not build anything whose economics only work at today's rate from today's vendor.

## What to Measure Instead

If you take one operational change from all of this, make it this one: stop comparing price per million tokens and start comparing total cost to complete one acceptable task.

Acceptable is doing real work in that sentence. It means the output passed your tests, not that it looked plausible in the chat window. A model that produces almost-right code cheaply is not cheap, because you are the one paying the difference in review time, and your time does not appear on any invoice.

Two things are worth tracking per model. The first is tokens per useful output, which catches the model that is verbose without being wrong. The second is output chain length, the number of turns from request to something you would merge, which catches the model that is cheap per turn and needs five of them.

GPT-5.6 Sol illustrates why the second one matters. On 3D web page generation it can hit rendering issues and performance bottlenecks, particularly when GPU resources were not assessed before the run started, and every one of those stumbles is another full context read at full price. The failure was environmental rather than a limit of the model, which is precisely the kind of cost that a benchmark comparison will never show you and your monthly bill will.

Measure the loop. The unit price is the part of the bill you can see, and on Microsoft's numbers it is the smaller part.

*Also readable on [Telegraph](https://telegra.ph/Beyond-Token-Pricing-How-Indie-Devs-Should-Really-Evaluate-AI-Model-Costs-08-19).*


---

**Read next**

- [AI Took Over My Coding. What Broke Was How I Learn.](ai-took-over-my-coding-what-broke-was-how-i-learn.md)
- [From AI Demo to Product: Loop Engineering for Indie Devs](from-ai-demo-to-product-loop-engineering-for-indie-devs.md)
- [AI Programming Tool Selection Strategy: From Rapid Prototyping to Long-term Collaboration](ai-programming-tool-selection-strategy-from-rapid.md)

[All 53 write-ups](../README.md)

The 13 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 466 more, as JSON and CSV.

Topics: [Indie Development](../topics/indie-development.md) · [AI Implementation](../topics/ai-implementation.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** the claim is that thinking depth drives most of the cost gap, and almost nobody checks their own split. Off the top of your head: is your bill mostly context you resend, or output you generate? Reply with a guess and say it's a guess. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/20).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fai-model-costs-beyond-per-token-pricing.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fai-model-costs-beyond-per-token-pricing.md&title=%5Bcorrection%5D+AI+Model+Costs%3A+Beyond+Per-Token+Pricing) — that form knows
which write-up you came from too; corrections and counter-data are the point.
