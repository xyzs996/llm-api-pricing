# The DeepSeek Quota Math Nobody Publishes: $10/Month, Peak-Hour Doubling, or a 3-Million-Yuan Server

![The DeepSeek Quota Math Nobody Publishes: $10/Month, Peak-Hour Doubling, or a 3-Million-Yuan Server](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-deepseek-quota-math-nobody-publishes-10-month-peak-hour.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

On September 25, 2026, OpenCode announced that the $60 of DeepSeek V4.1 Flash credit bundled with its $10 monthly plan was no longer a limited-time promotion. It was permanent. The same week, DeepSeek's own API changelog listed a 1M token context window and pointed at DeepSWE and NL2Repo results for coding-agent work.

While you have seen the benchmark charts if you read English-language coverage of DeepSeek, you have not seen anyone put the three ways to actually pay for this model — the $10 subscription, the peak/off-peak API, and self-hosting — into one cost table. The peak-hour doubling in particular is almost invisible outside Chinese-language sources, and it is the single detail that decides whether your daytime agent bill is what you budgeted or twice that.

So this is the table. Three paths, their real thresholds, and the limits that do not show up on the pricing page.

## What $10 Actually Buys, and Where the Wall Is

Start with the arithmetic that gets quoted everywhere. Ten dollars a month, sixty dollars of DeepSeek V4.1 Flash credit, credit that never expires. That is a 6x return on paper, and the announcement is specific about how it got there: the plan originally carried $30 a month, and Phase 2 doubled it to $60 while dropping the time limit.

Two caveats sit inside that sentence, and both matter more than the leverage.

The first is scope. The $60 applies to DeepSeek V4.1 Flash as a model, not as a general-purpose wallet you can spend across whatever OpenCode hosts, and because this credit does not follow you there if your agent workflow leans on a second model for a specific step, it stays tied to that one model rather than extending to any other model your workflow might call on.

The second is the one people miss. OpenCode manages limits across three separate windows — 5 hours, weekly, and monthly. Your monthly credit being permanent does not mean any given window is unlimited. Hit the 5-hour ceiling and requests stop, even with most of the $60 still sitting there.

OpenCode's weekly caps don't reach me.

For a coding agent, that 5-hour window is the wall you meet first. A single agent task is not one request; it is dozens of tool calls, each carrying context, each billed. The monthly number is the one you can plan against. The 5-hour number is the one that interrupts you at 2pm on a Tuesday.

The 5-hour wall doesn't convince me.

How many days a $10 plan survives under heavy agent use varies enormously with how many tokens your tasks burn per round, and I do not have a measured figure for that.

Here is my read, and it is a read rather than a measurement — namely that $60 of credit is enough for an independent developer running a few hours a day at medium task granularity, whereas if you leave an agent running batches all day, the 5-hour window will reach you before the credit does. The premise behind that judgment is that credit is counted per model and throttling is counted per time window — the two meters are not synchronized, and that mismatch is where the surprise lives.

## The Listed Price Is the Off-Peak Price

Now the part that changes your bill by a factor of two, and that you will not find in an English pricing table.

DeepSeek prices by time of day. Off-peak costs half of peak. Weekends are off-peak all day. On weekdays, 12:00–14:00 and everything after 18:00 are off-peak. The peak windows are 9:00–12:00 and 14:00–18:00, and during those hours the price doubles. The same wording shows up in sources dated October 6 and October 13, 2026, so you can cross-check it rather than take one article's word.

Which means the price table circulating in Chinese tech media — the one that makes DeepSeek look remarkably cheap — is filled in with off-peak numbers, while if you run your agent during a weekday afternoon you pay double what that table implies, because those off-peak figures only hold outside the hours when most people actually use the service.

Concretely, for V4.1-Flash: off-peak input is 3 yuan per million tokens, output 9 yuan. Weekday daytime doubles both. The model shipped on September 10, 2026, positioned for code and batch workloads. DeepSeek said beta pricing matched deepseek-v4-flash, with peak rates of 0.1, 3, and 9 yuan — so the developer's actual outlay did not drop, despite the "lower cost" framing around the release.

The obvious move is to shift batch work into off-peak windows, where the unit price halves. What can move: bulk refactors, long-context retrieval passes, offline evals. What cannot: an interactive agent session where you are waiting on the answer. If you are running an agent in a chat loop, you are paying peak rates, and no amount of scheduling discipline changes that.

For context on where 3/9 yuan sits, the same price band includes Xiaomi's mimo-v2.6-pro at 3 yuan input and 6 yuan output per million tokens, and Ant's Ling-3.0-flash at 0.12 yuan input and 0.38 yuan output. Ling-3.0-flash is among the cheapest lightweight tiers available in China right now, and it fits RAG and bulk copy generation well.

Be careful with those two numbers. They are price comparisons, not same-task benchmarks. Nothing here tells you which model is better at your job.

The judgment I will stand behind: peak/off-peak pricing is the only one of the three paths where you can cut your bill without changing your architecture. The cost is that you accept your tasks queueing until off-peak.

## Eight H200s, Three Million Yuan, and a Quantization Door That Is Shut

Self-hosting is the path people romanticize, so let us put the number on the table. Running DeepSeek-V4.1-Flash locally at full context, one estimate puts the requirement at a server with 8 H200 cards or 16 PPU cards, at a budget north of 3 million yuan. I'd pick Flash over PPU.

That figure is a quoted estimate from the article's author, not a measured quote sheet. Treat it as an order of magnitude, not a purchase order.

The detail that closes the door for most people is precision. At FP8, there is very little quantization headroom left — the usual trick of compressing the model onto fewer cards is unavailable here.

Capability is not the problem. On DeepSWE v1.1, V4.1 Flash would sit close to the top-left corner of the chart, approaching GPT-6 Astra. Note the tense: that chart has not been updated on the official site, so this is an inferred position, not an official data point. In DeepSeek's own DSH Minimal mode, the model beat both Standard and PTC modes on two controlled-variable tests.

DeepSWE's chart doesn't reach me.

Now amortize the 3 million against API pricing. At 9 yuan per million output tokens off-peak, 3 million yuan buys an astronomical token count — years of an individual developer's usage. The direction of that comparison is that self-hosting does not pencil out for an independent developer on pure cost.

It is not an argument that self-hosting is never worth it.

The real returns on self-hosting are data residency, no rate limits, and the ability to modify weights. None of those are unit price. If you are weighing the purchase, you need the machine broken into one-time cost plus monthly power and depreciation.

For the reader this piece is written for — an independent developer trying to control spend — the barrier on this path is not money. It is whether you have a reason that requires self-hosting.

## Three Paths, Three Different Walls

Line them up and the hidden costs are not the same kind of cost at all. The subscription is throttled by a 5-hour window — and by weekly and monthly tiers behind it, so a monthly allowance is not the same thing as unlimited calls in any given window. The API is throttled by the clock on the wall. Self-hosting is throttled by a 3-million-yuan floor and a quantization ceiling that will not move.

- Subscription: $10/month, $60 of credit that never expires, three-tier throttling at 5 hours, weekly, and monthly.
- API: 3 yuan input / 9 yuan output per million tokens off-peak, doubled on weekday daytime, no window limits.
- Self-host: 8 H200 or 16 PPU cards, a budget north of 3 million yuan, sized to run the full 1M context.

One reference point that gets lost in these comparisons: DeepSeek's API cost runs about one tenth of ChatGPT's, and a small team burning a few hundred thousand tokens a month pays less than the price of a milk tea. At that volume the gap between subscription and API is noise; what actually decides it is whether you need burst capacity outside a 5-hour window, and whether your usage is interactive or batch.

The same source reports a single anecdote worth flagging as exactly that: on a complex multithreaded crawler, ChatGPT needed two rounds of fixes and still had bugs, while DeepSeek's first output ran. One case. Not a statistic. Do not build a selection decision on it.

My bet: most independent developers land on a hybrid — off-peak API for batch work, plus the $10 subscription to cover interactive sessions — and pure self-hosting does not enter the individual developer's option set in 2026. The basis for that bet is that the three paths' thresholds differ by two orders of magnitude.

It is not a claim about which model is smarter.

The counter-conditions are worth naming, because this is a policy-shaped calculation. If OpenCode widens the 5-hour window, or DeepSeek drops the peak/off-peak doubling, the hybrid combination gets recalculated.

Until then, the rule is simple enough to hold in your head. If your work is interactive, you are paying peak rates and the subscription's window is your real constraint. If your work is batch, move it to the weekend and pay half.

If you are considering a server, price the reason first, not the hardware.

*Also readable on [Telegraph](https://telegra.ph/The-DeepSeek-Quota-Math-Nobody-Publishes-10Month-Peak-Hour-Doubling-or-a-3-Million-Yuan-Server-11-26).*


---

**Read next**

- [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md)
- [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)

[All 79 write-ups](../README.md)

The 24 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 950 more, as JSON and CSV.

Topics: [AI Programming](../topics/ai-programming.md) · [Token Optimization](../topics/token-optimization.md) · [AI Costs](../topics/ai-costs.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md&title=%5Bcorrection%5D+The+DeepSeek+Quota+Math+Nobody+Publishes%3A+%2410%2FMonth%2C+Peak-Hour+Doubling%2C+or+a+3-Million-Yuan+Server) — that form knows
which write-up you came from too; corrections and counter-data are the point.
