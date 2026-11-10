# What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist

![What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/87) — that copy has a reply box under it, and this one does not.*

This checklist is for developers who run DeepSeek V4.1 Flash inside a coding agent, direct or through OpenCode Go, and want a monthly bill they can defend. If you only use a free allowance, or a flat plan where you never look at tokens, skip it. I'd bet on Flash winning.

It exists because "cheaper" never showed up on bills. A 2026-09-08 report said V4.1 Flash internal-test billing matched deepseek-v4-flash, with peak rates of 0.1, 3 and 9 yuan per million tokens. That test ran two days and auto-expired on 9/10, so any price quoted from it is already stale. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] --> A 2026-09-18 sheet lists V4.1-Flash at 3 yuan in and 9 yuan out at idle, with weekday peak doubled. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> The same 3 and 9 show up as peak in one source and idle in the other. So every number below carries a date, and every step ends in a formula you fill in yourself: sticker, hour, cache, quota, schedule.

0.1 looks inflated to me.

## Write Down the Sticker Price With Its Date and Tier

The same model carries different sticker numbers depending on who quotes it and when. Next to every price in your spreadsheet, record three things: source, date, tier. The table below shows the DeepSeek Flash line. These are not all the same model, so don't read the rows as one price moving over time.

| Source date | Model named | Number quoted |
|---|---|---|
| 2026-05-02 | V4 | input "as low as" 0.27 yuan per million tokens |
| 2026-08-07 | V4 Flash | $0.028 per million tokens (direction not stated) |
| 2026-08-13 | V4 | output $0.87 per million tokens |
| 2026-09-01 | V4 Flash | output 2 yuan per million, "about 1% of Claude Opus" |
| 2026-09-08 | V4.1 Flash test | peak 0.1 / 3 / 9 yuan |
| 2026-09-18 | V4.1-Flash | idle 3 in / 9 out, peak doubled | <!-- [doc_498fb0bdb45e57d43725ed947a23c384] --> <!-- [doc_7b7a9d39c7edd7e338e85692ea3084a2] --> <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] --> <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

I did not resolve the disagreement. The 09-01 article says V4 Flash output is 2 yuan, yet the 09-08 report says test billing equals V4 Flash and shows 9 yuan at peak output.

Comparison tables make this worse, because they quote the off-peak price, not the one you pay at 10 a.m. Three tables (10-03, 10-12, 10-06) carry the same footnote: the DeepSeek price shown is the idle price, covering weekends all day plus weekdays 12:00-14:00 and after 18:00, and peak is 2x the table value. If you copy a row into your spreadsheet, you silently underquote every weekday-morning call. <!-- [doc_5528073dd1f937283caedd2c3baea7bc] --> <!-- [doc_bb4977a25d3700b71ae2e8b5eeec2fdc] --> <!-- [doc_c6529bc86a0b8c6e764c417e8433f153] -->

Don't use an April estimate as your baseline either. A Reddit poster on 2026-04-28 guessed about $3-5 a month for three agents doing email, calendar and research on V4 Flash, against $200-260 for Opus 4.7. That is a forecast for non-coding agents, not a bill. <!-- [doc_a7947740a61f182190750b03d21aac3c] --> A July article says DeepSeek announced peak/off-peak pricing for the V4 series from mid-July, with peak at 2x off-peak, so the April number could not have included it. <!-- [doc_5528073dd1f937283caedd2c3baea7bc] -->

Opus pricing doesn't concern me.

The pricing rule looks simple, but the failure mode hides inside it. DeepSeek's peak windows run on weekdays from 9:00 to 12:00 and from 14:00 to 18:00. Everything else, weekends included, is billed at half price. Peak is a small slice of the week, but your own working hours cluster inside it. If you code on weekdays between 9 and 6, nearly all of your tokens land in the expensive window, at double the off-peak rate.

Use this blended-price formula, where p is the idle price and s is your peak share of tokens:

blended = p × (2s + (1 − s))

At s = 1 you pay double the idle price. The 2x multiplier comes from the official wording the tables quote, so don't guess a different one, and don't assume anything in between without checking the published schedule. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] -->

One run on the input line, treating 3 yuan as the idle tier, as the 09-18 sheet labels it: weekday daytime peak pricing doubles that figure. So the more of your traffic lands in working hours, the further your blended input cost drifts above the headline price. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

The failure mode is that s is unknown until you log timestamps. Estimating it from memory is how people end up with a figure far below the real one, because nobody remembers how much of the work happens at peak hours.

## Discount Only the Cache Hits You Can Prove

The headline is that after a cache hit, real cost drops to one tenth of sticker. The 09-18 sheet says it about the whole batch of models released in 2026, which it says all strengthened KV Cache compression, and it frames the claim for RAG and agent workloads. It names no hit rate and no one who measured it. Treat it as an upper bound on the discount, not a DeepSeek measurement. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

There is one cross-check available, and it's the only genuinely new number in this checklist. If the first figure in the 0.1 / 3 / 9 triple is cache-hit input, the ratio is 0.1 to 3, about 1/30, not 1/10. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] --> Two sources disagree on the size of the discount. I can't tell you which one is official until the first number's meaning is confirmed.

The formula, with h as your hit rate, c the cache price and p the normal input price:

input cost = tokens × (h × c + (1 − h) × p)

With c = 0.1 and p = 3 yuan per million, a hit rate of 0.5 already pulls the effective input price well below the sticker 3 yuan, and a hit rate of 0.9 pushes it close to the discounted floor. Those hit rates are illustrations, not measurements. The formula covers input only. On the 09-18 sheet, output is 9 yuan against 3 for input, and those are off-peak prices, since weekday daytime doubles them. So a loop that generates a lot of text won't see the cache discount on that part. <!-- [doc_548375f4087cc017be2bc703f8d16167] -->

This is the step I'd expect to go wrong most often. h is the one input nobody publishes, and the 1/10 headline invites you to plug in h = 1. If you have no measured hit rate, write "unmeasured" in that cell and carry a range through the sheet instead of a point.

## Convert the Subscription Quota Into Tokens and Name Its Three Windows

OpenCode Go costs $10 a month and buys a $60 usage quota for V4.1 Flash, and that quota is now permanent. It started as $30 a month, was raised to $60 in "Phase 2", and was kept long-term. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> But dollars of quota are not tokens. To turn $60 into tokens you need the per-token rate OpenCode charges, and the sources here don't give it.

OpenCode's quota doesn't reach me.

The monthly quota is also not an unlimited-call pass. The docs manage limits per 5 hours, per week and per month, separately. The monthly quota is kept, but each window still caps how many requests you can make. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> The failure mode is a batch job that burns through the 5-hour window halfway through a run, then sits idle until the window resets.

Your month looks affordable on paper while the job misses its deadline.

Context size is the last quota-adjacent cost. The API changelog lists a 1M-token context window, and the coding-agent tests it names are DeepSWE and NL2Repo. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> <!-- [doc_548375f4087cc017be2bc703f8d16167] --> Here's the derived arithmetic: one full 1M-token prompt with no cache hit, at 3 yuan per million, is 3 yuan of input. If 3 yuan is the idle tier and you're in peak, it's 6. An agent that resends a long context ten times is 30 to 60 yuan before it has written a line of output. Check what your agent actually puts in the window before you trust the monthly figure.

DeepSWE tells me nothing.

## Move Batch Work Off-Peak and Price It Per Finished Task

Batch jobs belong in the off-peak windows. The 09-18 sheet recommends night runs for batch work, and weekends are off-peak all day. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> Speed makes that practical: a developer measured SVG generation about 6x faster and long-context retrieval more than 5x faster than V4 Flash Vision-Exp, same task end to end. That comparison is against a vision-experimental model, not plain V4 Flash, so don't generalise it. The test billing also gave each account 20 concurrent requests. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] -->

Then price at the task level, not the token level. A 2026-10-31 article lists V4.1 Flash at 96.0 on coding, $0.181 per successful task, and 1.1 s first-token latency. I don't know who measured it or on which benchmark, so it's a lead, not evidence. <!-- [doc_3e5fc44d8368b305e0bdb046c6eeaa03] --> The failure mode: a cheap token price with a low success rate can cost more per finished task than a pricier model. The formula is cost per finished task = (tokens per attempt × price) ÷ success rate.

For a cross-check on list prices only (no ranking), Qwen3.8-Flash, released 2026-08-14, is 0.2 yuan in and 2 yuan out. Ling-3.0-flash is 0.12 in and 0.38 out. GLM-4-Flash gives 20M free tokens at registration, permanently, with 128K context and 30 concurrency. <!-- [doc_548375f4087cc017be2bc703f8d16167] --> <!-- [doc_a2038db8e4ae681c3866106c792fca3c] --> <!-- [doc_498fb0bdb45e57d43725ed947a23c384] --> Whether any of them can do the same coding task is untested here.

That's the five steps. Before you build the spreadsheet, check whether it's worth the time.

If your spend is a few dollars a month, the checklist costs more than it saves. The Reddit forecast was $3-5 a month for three light agents, and GLM-4-Flash's 20M free tokens don't expire, while DeepSeek's sign-up grant of 10M tokens (2026-05-02 article) was valid for only 30 days. <!-- [doc_a7947740a61f182190750b03d21aac3c] --> <!-- [doc_498fb0bdb45e57d43725ed947a23c384] -->

GLM's free tokens convince me.

If your work is interactive coding that can't leave 9:00-18:00, skip the scheduling step. Peak covers weekday 9-12 and 14-18, so only 12:00-14:00 is a daytime gap. Put the effort into cache hit rate and quota windows instead. <!-- [doc_a2038db8e4ae681c3866106c792fca3c] -->

Don't reuse any number here without re-checking the pricing page. The 09-08 test billing and its two-day window are already past, and every price above is only as fresh as the source date next to it. <!-- [doc_3f84ec4bbd12a94082dbba3339082afa] -->

*Also readable on [Telegraph](https://telegra.ph/What-DeepSeek-V41-Flash-Really-Costs-Per-Month-A-Five-Step-Checklist-11-10).*


---

**Read next**

- [The "10x Cheaper" Trap: How to Read AI Coding Costs](the-10x-cheaper-trap-how-to-read-ai-coding-costs.md)
- [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](the-hidden-costs-of-ai-coding-tools-what-english-developers.md)
- [How a Multi-Agent AI System Made $7,600 in 7 Days for Under $100 in API Costs](how-a-multi-agent-ai-system-made-7-600-in-7-days-for-under.md)

[All 68 write-ups](../README.md)

The 22 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 709 more, as JSON and CSV.

Topics: [Development Tools](../topics/development-tools.md) · [AI](../topics/ai.md) · [Chinese AI](../topics/chinese-ai.md) · [Indie Developer](../topics/indie-developer.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** What percentage of your DeepSeek V4.1 Flash coding agent tokens do you estimate fall in peak pricing windows, reply with one number here? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/87).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fwhat-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fwhat-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md&title=%5Bcorrection%5D+What+DeepSeek+V4.1+Flash+Really+Costs+Per+Month%3A+A+Five-Step+Checklist) — that form knows
which write-up you came from too; corrections and counter-data are the point.
