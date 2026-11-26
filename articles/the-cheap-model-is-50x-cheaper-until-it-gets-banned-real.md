# The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks

![The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/95) — that copy has a reply box under it, and this one does not.*

DeepSeek V3.2 costs $0.26 per million input tokens and $0.38 per million output tokens. Opus 4.7 lists at $5.00 per million input — except that's not what you pay, because a 35% tokenizer increase pushes the effective input price to roughly $6.75 per million.

Same task, same agent loop, and one side of that comparison is about 50x cheaper than the other. One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day.

That sounds like the end of the article. It isn't, because the cheap side carries three bills the price sheet never shows you: a tokenizer that inflates what you actually send, a provider dropdown that can multiply your output cost by an order of magnitude, and a set of availability failures — bans, rate limits, tool calls that get promised and never executed — that cost you in retries and babysitting rather than dollars per token.

Here's each one, with the numbers attached.

## The Sticker Price Is Not the Bill

Start with the tokenizer, because it's the one that quietly invalidates every back-of-envelope estimate you've ever made from a pricing page.

Opus 4.7's input price is $5.00 per million tokens. But the same prompt gets cut into more tokens than it used to — a 35% increase — so the effective input cost lands around $6.75 per million. The per-token rate didn't move. The token count did. Which means any spreadsheet that multiplies your character count by the advertised rate is going to come in low, and it will come in low by a margin you can't see anywhere on the vendor's page. This figure comes from a user's own measurement posted on 2026-04-28, not from a vendor announcement, so treat it as a first-hand estimate rather than a published spec — but it's the kind of estimate you should be making yourself before you commit to a model.

The second hidden multiplier is provider selection, and this one is worse because it's a dropdown menu.

If you call Qwen 3 Coder through OpenRouter and leave Alibaba selected as the inference provider, output can run up to $60 per million tokens. Same model, same OpenRouter endpoint, one different selection in a provider list, and the output price differs by an order of magnitude. The original warning about this was written in all caps as an operational instruction: remove Alibaba from the Qwen 3 Coder provider list. If you're routing through an aggregator and you've never opened the provider settings, you don't actually know what you're paying.

The third is the output-side spread, which matters more the more your workload looks like an agent loop. Qwen3.5 Plus runs $0.12–0.57 per million input and $0.69–3.44 per million output, with context up to 1M tokens. The top of that output range is roughly five times the bottom. In a loop where the model is generating reasoning, tool arguments, and revisions turn after turn, output tokens dominate — so your bill drifts toward the expensive end of a range you thought was one number. Compare MiniMax M2.7 at $0.30 in and $1.20 out with 204.8K context, where the output spread is compressed and the pricing is easier to reason about for multi-turn agent work.

What I can't do is fold all three of these into a single monthly figure for a real workload, because that requires the input/output/cache split of an actual agent's token usage.

Without that split, the three multipliers above stay separate warnings instead of one number. If you're budgeting, pull your own split first — the ratio decides whether the tokenizer increase or the output spread is the thing that hurts you.

## Where the Cheap Side Actually Wins

The interesting part isn't that cheap models are cheap. It's that in at least some hands-on coding tests, the quality held up well enough that "you get what you pay for" stops being a useful rule.

Kimi 2.5, given a game-programming task, produced a first version of the HTML that ran. It had one bug — projectiles did not damage enemies — and one round of fixes resolved it. Note the specificity: not "some minor issues," but a named failure with a fix count of one. That's a single task and a single run, so it doesn't rank general coding ability. But it's the kind of concrete result you can actually check against your own workload, which is more than most benchmark tables give you.

Now the other direction. Claude Sonnet 4.5's token cost ran higher than Qwen 3.5, GLM 5, and Kimi 2.5 in the same tester's comparison, and the tester's judgment was that the money did not convert into better or more optimal token generation. That's the one place in this set of data where "expensive means reliable" gets directly contradicted rather than just left unproven.

I have to flag how incomplete that comparison is, because the same tester wanted to re-run Sonnet 4.5 for a fair head-to-head and couldn't: the Claude free tier was exhausted during the first coding session. So the expensive-side result rests on a partial trial. It's evidence that high cost didn't automatically buy better output, not proof that Sonnet 4.5 is worse. If you're making a decision on this, the honest reading is that the cheap side has a win and the expensive side has an unproven claim.

There's also an ordering within the cheap tier worth knowing. Kimi K2 came in at half the cost of Qwen 3 Coder while producing generally better code and features. Cheaper and better in the same comparison, which tells you price and quality aren't positively correlated down in this segment. It also connects back to the previous section: Qwen 3 Coder's expense in that test was a provider-selection artifact, not the model's own list price. The lesson isn't "Qwen is expensive." It's that routing decisions, not model choice alone, determine what you actually pay.

## What the Saved Money Buys You

Here's where the 50x gap gets spent. Three failure modes, all of them availability problems, none of them visible on a price sheet.

The first is account bans. Zhipu has been banning agent users on GLM-5.1 coding plans, according to a single user report. I'm writing that as one user's report and not as a general conclusion, because that's the strength of the evidence. But look at what's being banned: subscription coding plans, not per-token API access. The path you choose to save money determines which risk you're exposed to. If you buy a monthly coding plan to get a flat rate, you've taken on a risk that doesn't exist for someone paying per token — and you won't find it in the terms until it happens to you.

The second is rate limiting, and this one has a number precise enough to plan around. An agent running tool calls through the OpenAI API in Lumina hit a 14.753-second rate limit after one call, or at most two. The consequence isn't just waiting: agentic tasks ran 10x slower, required repeated "continue" prompts, and each continue burned context and usage while requiring a human to sit there and press it. If you're running an agent unattended overnight, this is the failure that turns a cheap run into a manual one. And notice the cost shape — it isn't billed as tokens, it's billed as your attention.

The third is the quietest and the most expensive to debug. Kimi K2 in VSCode will promise to make a tool call and then not make it — the same failure pattern as Gemini 2.5 Pro — while Qwen 3 Coder was close to flawless in that same setting. No error, no exception. The agent loop keeps running, burning tokens on a plan that will never execute. There's a related failure in the same family: MiMo-v2-omni kept hammering the tools until it died from context overflow, and generated private methods that just called public methods of the same name. That's the shape of a model that has learned what tool use looks like without learning what it does.

For contrast, there's a known-good ceiling. GLM 5.3 API completed a large coding task involving 54 reasoning steps and 74 cascading tool calls without incident. Use that as a floor for what "working" looks like: if your agent tasks are smaller than 54 steps and 74 calls, rate limits and tool failures may never surface in your testing, and you'll discover them in production instead. The same source reports a model bound to an OpenAI API key that insisted you could use reasoning or tool calls but not both — a warning sign worth checking before you build a loop that needs both.

One gap in this section: everything above is somebody else's report.

## The Verdict: Route by Task Type, Not by Price

Here's where I come down: route by task type, and stop treating the price column as a proxy for the decision.

For high-frequency, short-turn, structured-output agent calls, DeepSeek V3.2 at $0.26 in and $0.38 out with 163K context is the right default. Save Opus 4.7 for the steps where one wrong answer means re-running the whole chain. The reasoning is in the previous two sections: the cheap side's failures are mostly retry-shaped — a bad tool call, a rate limit you wait out — while the expensive side's failure mode in the data is your quota disappearing. And with a monthly gap of $3–5 against $200–260, you have an enormous retry budget before the cheap route stops being cheaper.

The cost of choosing cheap is three things you should write down before you commit. A subscription coding plan can get your account banned. A single call can hit a 14.753-second rate limit. A tool call can be promised and silently skipped. None of these are price problems. They're availability problems, and the only two hedges are routing by task type or going into OpenRouter and manually removing the expensive providers from your model's list.

The cost of choosing expensive needs saying too, because it's the argument people skip. The tokenizer adds 35% to your effective input price, and in the comparison we have, the higher spend didn't buy better output. That isn't proof that expensive models are unreliable — it's proof that expensive doesn't automatically mean reliable. Reliability has to be shown with something like the 54-step, 74-call run, not inferred from a price tag.

One last caveat on every number in this piece: model names and prices move fast, and these figures span source dates from 2025-07-23 to 2026-08-31. Treat them as a snapshot and re-check before you put them in a budget.

*Also readable on [Telegraph](https://telegra.ph/The-Cheap-Model-Is-50x-Cheaper-Until-It-Gets-Banned-Real-Per-Token-Costs-vs-What-Actually-Breaks-11-20).*


---

**Read next**

- [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)

[All 79 write-ups](../README.md)

The 26 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 948 more, as JSON and CSV.

Topics: [AI Programming](../topics/ai-programming.md) · [Token Optimization](../topics/token-optimization.md) · [AI Agents](../topics/ai-agents.md) · [LLM](../topics/llm.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** Before you read this, what was your own input/output token split for a real agent workload — reply with that ratio below, since you'd know it from memory without checking any dashboard. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/95).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md&title=%5Bcorrection%5D+The+Cheap+Model+Is+50x+Cheaper+Until+It+Gets+Banned%3A+Real+Per-Token+Costs+vs.+What+Actually+Breaks) — that form knows
which write-up you came from too; corrections and counter-data are the point.
