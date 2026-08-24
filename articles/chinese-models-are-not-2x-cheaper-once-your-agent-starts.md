# Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching

![Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/chinese-models-are-not-2x-cheaper-once-your-agent-starts.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/66) — that copy has a reply box under it, and this one does not.*

Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. Reprice the same 40 at the token mix a coding agent actually produces and the gap falls to 1.51x. Nothing was discounted and nothing expired. The comparison was just reading the wrong column.

## The Price You Compare Is Not the Price You Pay

Every model card quotes three numbers: input, output, and cached input. Comparison articles use the first. Agents spend almost all of their money on the third.

The table behind this piece was pulled on 2026-08-23, 60 rows off OpenRouter. Two lack a cached-input price and drop out; batch-mode rows are held aside for now, because mixing them into a median compares a latency tradeoff against a model. That leaves 40 like-for-like rows, 14 Chinese and 26 American.

Now weight those three prices by what an agent really sends. The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output.

Read that last figure again. Output — the scariest sticker, $25 or $50 per million — is under a third of one percent of the volume. It barely participates in the bill.

Reprice at that mix and the medians land at $0.2015 against $0.3046. A gap of 1.51x. Nearly a full point of the advantage was never there.

## Where the Lead Went

Cache read price is not a fixed fraction of input price, and the pattern does split along the map. It just does not split for the reason it looks like it splits.

Anthropic, Google and OpenAI each charge 10% of input for a cache read — flat, every model, and stable across *sellers* too. Claude Sonnet 5 is resold through nine storefronts including AWS Bedrock, Azure and Google, and all nine bill a cache read at exactly 10.00% of their own input price. Across all 26 American rows, none spreads wider than three points between cheapest and dearest host. The ratio is vendor policy, and resellers pass it through.

Now the other side. z-ai's GLM-5.1 is served by seventeen hosts, cache read ratios running 10.00% to 50.42%. Kimi K2.6 has nineteen, 10.00% to 50.00%. DeepSeek V4 Pro has seventeen, 3.33% to 20.00%. Of the fourteen Chinese rows, seven spread wider than three points; of the twenty-six American rows, zero do.

So "z-ai charges 20%" is a sentence that cannot be true, because z-ai is not the one charging. These are open-weight models: the vendor publishes weights and at most runs one storefront among many, and the price you pay is set by whichever GPU reseller your router picked. DigitalOcean, CoreWeave and Together are American companies charging you an American markup on a Chinese model.

Check it against the vendor's own rate card and the gap is plain. DeepSeek publishes 0.022 per million for a cache hit against 0.66 cache miss — a ratio of 3.33%. The row in my table said 8.33%, because the host my table recorded was StreamLake, not DeepSeek.

That is the correction. The border runs between *first-party and resold pricing*, not between two countries. It only looks national because the American models here are closed-weight and can only be sold at their maker's ratio, while the Chinese ones are open-weight and can be sold at anyone's.

## The Host Costs More Than the Model

Which turns the question inside out. If one model has a nine-fold spread depending on who serves it, picking the model is the small decision.

DeepSeek V4 Pro, one day, seventeen hosts, priced at the agent mix. Cheapest: GMICloud at $0.0429. Dearest: Venice at $0.3923. That is 9.1x, for byte-identical weights.

Worse is how the cheap one gets missed. Routers rank by list input price, and so did the table in this piece. On input StreamLake wins by a third of one percent — $0.5262 against GMICloud's $0.5280. On the bill you actually get, StreamLake costs **54.7% more**, because its cache read is 8.33% where GMICloud's is 3.33%. Sorting by the visible column picks the wrong host by half again, on a two-hundredths-of-a-cent difference in the column you were reading.

GLM-5.1 does the same: sort by input and you take GMICloud, and pay 45.2% over Chutes. Kimi K2.6 happens to come out right, which is the point — it is a coin flip, not a strategy.

None of this is exotic. It is one field, `input_cache_read`, published per host, that nobody sorts on.

## One Billion Tokens, Two Invoices

Here is the argument as a single month's bill. Take a billion tokens at that mix, a middling month for one developer running an agent seriously, and price it both ways.

Qwen3.7 Max lists at $1.475 per million input. Claude Sonnet 5 lists at $2.00. On the pricing page Qwen is 26% cheaper and the decision looks made.

Run the billion tokens through: Qwen3.7 Max bills $355.00, Claude Sonnet 5 bills $301.68. The cheaper-looking model costs 18% more.

Neither price is wrong. Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice. The list price answered a question nobody asked.

This particular pair is worth trusting more than most, because both sides are sold by the people who made them. Qwen3.7 Max has exactly one host on the router and it is Alibaba. Claude Sonnet 5 has nine, and all nine bill 10.00%. So this is Alibaba's own policy against Anthropic's own policy, 20% against 10%, with no reseller standing in between adding a markup I would have mistaken for a vendor decision.

That pair is not a cherry. Among the 40 rows there are 28 Chinese-American pairings where the Chinese model lists cheaper and bills the same or more.

While we are here: budgeting a billion tokens at Kimi K3's list input predicts $3,000. The real figure is $452.52, an overestimate of 6.6x. Anyone forecasting spend off a pricing page is not slightly wrong.

## Four Models Move Nine Places

Ranking by list price and ranking by effective price are not the same ranking. Sort all 40 both ways and watch who travels.

GLM 5V Turbo goes from 14th cheapest to 23rd. Qwen3.7 Max drops seven places to 27th, Grok 4.6 six to 33rd. Travelling the other way, GPT-5.1-Codex climbs seven, 19th up to 12th.

That is a long way to move on a number nobody checks. Anyone who picked a model off a list-price comparison last quarter has a live chance of holding one of those four.

## The Output Price Is a Decoy

Vendors compete on the output number because it reads as expensive and because buyers screenshot it. A model at $50 per million output looks four times worse than one at $12.50. At 0.29% of volume that gap contributes almost nothing, while a cache read at 10% against 20% moves the same bill by a third.

The pricing page is ordered by drama. The invoice is ordered by volume.

## Where the Cheap Advantage Is Real

None of this makes the Chinese side expensive, and the corrected numbers are kinder to them than the headline ratio was.

Gemini 3.7 Flash is the cheapest of the 40 at $0.0566 effective, and DeepSeek V4 Pro sits right next to it — a fact that turned out to be the loose thread in this whole piece. Overnight the DeepSeek row moved a third, on input, output and cache read alike. I expected the clock: DeepSeek is the one vendor here whose rate card splits peak from off-peak at a factor of two. So I read the row every six minutes across the boundary. Seven reads: it did not move by a hundredth of a cent.

Not the clock. The host. Nothing was repriced overnight — the cheapest of seventeen sellers changed, and the catalogue always reports whichever that is. The $0.0664 figure is StreamLake's to four decimals, and the day before it belonged to someone else.

So the question was malformed. DeepSeek V4 Pro is not next to Gemini 3.7 Flash. At GMICloud it is $0.0429, comfortably the cheapest of the forty; at Venice it is $0.3923, mid-table. Same model, same day. Asking which model is cheapest, without saying whose GPUs, has seventeen answers.

Eleven of the fourteen Chinese models beat the American median. That is a real advantage, and nothing here argues it away. Thirteen of the twenty-six American models also beat the American median.

So "Chinese models are cheaper" is doing less work than it appears to. "Some models are cheaper" is the same claim with a shorter list of exceptions, and it points at a table instead of at a flag.

At the top of the market the flag stops meaning anything at all. Kimi K3 prices at $0.4525 effective. So do Claude Sonnet 4.5 and Claude Sonnet 4.6, to four decimal places. Whatever separates those three, it is not cost.

## What the Table Does Not Cover

Batch mode went aside earlier for a reason, and what happens there is worth saying. Across the 18 batch rows the list gap is 1.58x and the effective gap is 0.98x, meaning the Chinese rows come out marginally more expensive. Three of those rows are Chinese, which is too thin to carry a conclusion, so treat it as a question rather than a finding.

Twelve models also carry a second, higher price band past a context threshold, mostly at 200,000 tokens and 272,000 for GPT-5.4. Every figure here uses the base band. An agent routinely running a 300,000-token context is paying a different table than this one.

That cuts against the conclusion in places, which is the reason to state it.

## Run It Against Your Own Mix

That mix came from one person's agent, on one codebase, five months ago. Yours will differ, and the direction it differs in changes the answer.

Cache-read share is the whole ballgame. Push it down toward 80%, which short sessions and cold starts and a pile of new files will do, and the vendors with cheap cache reads lose their edge; the comparison drifts back toward the card price, and back toward the Chinese side. Push it past 98%, which long runs on a stable repo will do, and the flat-ten vendors stretch further ahead.

The useful question was never which country prices lower. It is two numbers, and neither is on a comparison chart. What is your cache-read percentage — if you cannot say it to one decimal place, that is the number to go find this week, and it is already sitting in your API dashboard. And who is actually serving your tokens, which for a closed-weight model is a question with one answer and for an open-weight one is a question with seventeen.

Better to ship the arithmetic than the conclusion. Three prices per host, three weights, one multiplication. Nothing here asks you to trust anyone about anything except the prices, and those you can pull yourself in about a minute.

*Also readable on [Telegraph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24).*


---

**Read next**

- [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md)
- [Choosing the Right AI Model for Coding: Cost vs. Efficiency](choosing-the-right-ai-model-for-coding-cost-vs-efficiency.md)
- [Claude Code and Codex for Office Automation](claude-code-and-codex-for-office-automation.md)

[All 53 write-ups](../README.md)

The 64 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 429 more, as JSON and CSV.


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** what is your agent's cache-read share? Reply with the number if you know it, or one word for why you do not: dashboard, mixed, or never-looked. That one figure decides which half of this table you should be reading. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/66).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fchinese-models-are-not-2x-cheaper-once-your-agent-starts.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fchinese-models-are-not-2x-cheaper-once-your-agent-starts.md&title=%5Bcorrection%5D+Chinese+Models+Are+Not+2x+Cheaper+Once+Your+Agent+Starts+Caching) — that form knows
which write-up you came from too; corrections and counter-data are the point.
