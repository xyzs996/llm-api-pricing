# DeepSeek's Peak-Hour Price Is Double — How to Schedule Your Batch Agent Jobs Around It

![DeepSeek's Peak-Hour Price Is Double — How to Schedule Your Batch Agent Jobs Around It](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/deepseek-s-peak-hour-price-is-double-how-to-schedule-your.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

This one is for independent developers running batch coding agent jobs and paying per token. It is not for you if your agent has to answer a human in real time, and it is not for you if you have already moved your whole workload onto a local open-weight model where the marginal cost of a call is electricity.

DeepSeek's own pricing page makes the mechanics plain: idle-hour prices are half the peak-hour price, and the peak windows are 9:00–12:00 and 14:00–18:00 on weekdays, billed at twice the table rate, while weekends are idle all day, and so is the 12:00–14:00 lunch gap and everything after 18:00.

What follows is how to work out whether moving your jobs is worth it. I am going to be honest about the part I cannot give you: I have not run a controlled before-and-after on my own bill, so every number here is arithmetic against published rates, not a receipt.

Where you need your own data, I say so.

## Work Out What Share of Your Bill Sits in the Peak Window

Before you touch a cron file, get one number: what percentage of your tokens land inside 9:00–12:00 and 14:00–18:00 on weekdays. Without it, everything else is guesswork dressed as optimization.

Here is the rate card you are working against. DeepSeek V4.1-Flash, released 2026.09.10, runs 3 yuan per million input tokens and 9 yuan per million output tokens at idle rates. Weekday daytime doubles that. Note what happened to the promise of cheaper: developers reported that actual charges did not fall, and peak-hour output still came to 9 yuan per million tokens.

The second thing to internalize is that agent workloads do not have the token mix of chat. Output dominates. A chat turn is a long prompt and a short answer, while an agent turn is a short instruction and a long trail of tool calls, diffs, and reasoning, and that matters because the peak multiplier lands hardest on the expensive side of the ledger, the output side, where you are already paying three times the input rate.

And the capability is not being traded away for that price. In one set of coding evaluations, DeepSeek V4.1 Flash scored 96.0 with a cost of $0.181 per successful task, against Mistral Large 4 at 95.4 and Fable 5.1 at 97.7. So this is not a cheap model you tolerate; it is a competitive one you can afford to run in bulk.

The failure mode here is specific and common: comparing models on the headline per-million-token rate and multiplying by your monthly token total. That number is fiction. This is the step where I think most people quietly get it wrong, because the arithmetic looks rigorous while resting on an assumption nobody checked.

## Put the Cron Entry in the Idle Window

The first move is not a code change. It is sorting your jobs into two piles: those that can be delayed and those that cannot. Only the first pile moves.

The idle windows are three: the weekday lunch gap from 12:00 to 14:00, everything after 18:00 on weekdays, and all of Saturday and Sunday. The peak windows are two, and they are not contiguous — 9:00–12:00 and 14:00–18:00, with a two-hour hole in the middle. That hole is the detail people miss when they think of "the workday" as one block.

The weekend is the most overlooked slot in the whole scheme. Batch work scheduled for Saturday or Sunday is straight half price, no cleverness required, and if your jobs are already nightly you are three-sevenths of the way there by accident. I checked this against three separately captured rate tables — 2026-10-03, 2026-10-06, and 2026-10-12 — and the window definitions agree across all of them. That consistency is reassuring, but it is not permanence. Vendors adjust windows and multipliers, so any article on this subject, including this one, has to state its capture date or it is just folklore.

Now the part that decides whether any of this is worth doing. Against what delay?

A developer running three agents for daily work — email, calendar, research — reported a real cost of roughly $3–5 per month on DeepSeek V4 Flash, against $200–260 per month for the same workload on Opus 4.7. Sit with that for a second. If your monthly bill is five dollars, halving the peak portion of it saves you a dollar or two. You will spend more than that in your own time once, and then keep paying it in the form of a queue, retry logic, and a class of bug where a job silently does not run because the scheduler and the rate window disagreed.

The failure mode in this step is not arithmetic, it is discipline. The temptation is to move everything into the idle window, including the jobs that a human is waiting on. Your bill arrives at the end of the month; a sluggish agent is felt in the same second it happens. Of the two ways to get this wrong, I think this is the more likely one, and the more expensive in trust.

## The Concurrency Ceiling Does Not Care That It Is Cheap

Here is the trap that turns a good plan into a stalled queue. A cheaper window does not come with a wider pipe.

DeepSeek's V4.1 Flash beta API was limited to 20 concurrent requests per account. That beta also auto-expired after 2026.09.10, which gave developers a two-day testing window. Read that carefully before you plan around it: 20 concurrency is a beta-era figure, and the beta itself is gone. Do not treat either number as a current guarantee.

Check the live documentation for whatever model you are actually calling.

Why it still matters is the shape of the risk. Compress a large batch into a two-hour lunch window and you have not just moved the work, you have concentrated it. If your fan-out exceeds the ceiling, the excess does not vanish — it waits, and now your two-hour window is not enough and the tail of the batch spills into 14:00, which is peak, which is double.

You have optimized your way into paying the premium you were avoiding.

There is a real speed story on this model that makes the concentration tempting. In end-to-end comparisons, V4.1 Flash generated SVG code about 6 times faster than V4 Flash Vision-Exp, and long-context retrieval more than 5 times faster. Fast models invite you to pile on more work per window.

That is exactly how you find the ceiling.

The failure mode: you assume idle means fast. It means cheap. The bill goes down and the batch does not finish, and you find out at the deadline rather than at the invoice.

## Cache Hits Move the Bill More Than the Clock Does

If you only take one thing from this, take the ordering: make your workload cache-friendly first, schedule it second. Done the other way around, you optimize the smaller lever and feel finished.

The 2026 generation of Chinese models put serious work into KV cache compression, and once you are hitting cache, real cost can fall to about one tenth of the list price. DeepSeek V4.1-Flash specifically cut KV cache footprint to a quarter of the previous generation's HBM occupancy and an eighth of its SSD occupancy.

For batch agent work, the cacheable material is not exotic. It is the system prompt you send on every single call, the tool definitions, the repository context, the style guide. If those are stable and ordered consistently, they hit cache. If your harness rebuilds the prompt with a timestamp at the top, or shuffles the file list, you are paying full price for identical bytes, thousands of times.

Compare the two multipliers and the priority sorts itself. Cache takes you to roughly 1/10. Peak-to-idle takes you to 1/2. That is a five-fold difference in effect, and the cache one does not cost you a single minute of latency.

The failure mode is treating peak-shifting as the whole answer. A reader follows the schedule advice, saves half of one line item, and concludes they have reached the floor. They have not; they have rearranged the furniture in one room.

## When Not to Do Any of This

Three cases where the right move is to close the tab.

The first is a workload that must be delivered immediately. If a person or a downstream system is blocked on the output, the delay is the cost, and it is larger than the discount. Keep those jobs where they are and move only the genuinely deferrable ones.

The second is a bill already measured in single-digit dollars per month. At $3–5, the savings are a few dollars, and the engineering — scheduler changes, retry handling, a queue, monitoring for jobs that did not fire — costs more than it returns. This is the case where the honest advice is to do nothing and spend the afternoon on something that ships.

The third, and the one most likely to mislead, is using a model that has no peak-valley mechanism at all. The cheap tier is full of flat-rate options: Qwen3.8-Flash, released 2026.08.14, prices input at 0.2 yuan and output at 2 yuan per million tokens. Ant Ling-3.0-flash goes lower still, at 0.12 yuan input and 0.38 yuan output per million tokens, with no peak multiplier listed in the rate table.

Do the comparison honestly and the scheduling question may dissolve. If a flat-rate model at a fraction of the price clears your quality bar, switching models beats rearranging your cron by a wide margin, and it costs you one afternoon instead of a standing piece of infrastructure.

The failure mode: copying a cron pattern from an article about peak pricing onto a model that does not have peak pricing. Nothing breaks, nothing saves, and you have added a moving part for free.

## The Short Version

Peak is 9:00–12:00 and 14:00–18:00 on weekdays at double the idle rate; idle is the 12:00–14:00 gap, everything after 18:00, and all weekend. Quantify your peak share before you claim a saving — no distribution log means no number. Cache-friendly prompts first, because 1/10 beats 1/2. Confirm the current concurrency limit for your model rather than trusting a beta figure that has already expired. And if the bill is a few dollars a month, leave it alone.

The judgment call I would put to you: if a batch finishes in the afternoon instead of the morning and saves you a dollar, is that a trade you would make twice? Some people will say yes without hesitating, and they are not wrong — they just have a different cost of waiting than you do.

*Also readable on [Telegraph](https://telegra.ph/DeepSeeks-Peak-Hour-Price-Is-Double--How-to-Schedule-Your-Batch-Agent-Jobs-Around-It-11-27).*


---

**Read next**

- [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md)
- [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)
- [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md)

[All 80 write-ups](../README.md)

The 4 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 974 more, as JSON and CSV.

Topics: [AI Programming](../topics/ai-programming.md) · [AI](../topics/ai.md) · [Cost Savings](../topics/cost-savings.md) · [LLM](../topics/llm.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fdeepseek-s-peak-hour-price-is-double-how-to-schedule-your.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fdeepseek-s-peak-hour-price-is-double-how-to-schedule-your.md&title=%5Bcorrection%5D+DeepSeek%27s+Peak-Hour+Price+Is+Double+%E2%80%94+How+to+Schedule+Your+Batch+Agent+Jobs+Around+It) — that form knows
which write-up you came from too; corrections and counter-data are the point.
