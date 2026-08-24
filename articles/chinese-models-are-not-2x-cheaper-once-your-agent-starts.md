# Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching

![Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/chinese-models-are-not-2x-cheaper-once-your-agent-starts.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/66) — that copy has a reply box under it, and this one does not.*

Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. Reprice the same 40 at the token mix a coding agent actually produces and the gap falls to 1.51x. Nothing was discounted and nothing expired. The comparison was just reading the wrong column.

## The Price You Compare Is Not the Price You Pay

Every model card quotes three numbers: input, output, and cached input. Comparison articles use the first. Agents spend almost all of their money on the third.

The table behind this piece was pulled on 2026-08-23, 60 rows off OpenRouter. Two lack a cached-input price and drop out; batch-mode rows are held aside for now, because mixing them into a median compares a latency tradeoff against a model. That leaves 40 like-for-like rows, 14 Chinese and 26 American.

Now weight those three prices by what an agent really sends. The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output.

Read that last figure again. Output, the price with the scariest sticker, the one at $25 or $50 per million, is under a third of one percent of the volume. It barely participates in the bill.

Reprice at that mix and the medians land at $0.2015 against $0.3046. A gap of 1.51x. Nearly a full point of the advantage was never there.

## Where the Lead Went

Cache read price is not a fixed fraction of input price, and the pattern splits almost exactly along the map.

Anthropic, Google and OpenAI each charge 10% of input for a cache read. Flat, every model, across 20 rows without one exception. Meta charges 12%.

The Chinese vendors mostly do not. z-ai charges 20% across six rows. MiniMax charges 20%. Qwen and Moonshot both sit near 16%, Moonshot spreading from 10% as far as 25%.

So a model that undercuts by half on the pricing page hands a third to a half of that back on the line carrying 96% of the traffic. DeepSeek is the exception that proves the rule: 8.3%, better than anyone's flat ten.

The split was not what I went looking for. A ratio moved, the question was which column moved it, and the answer turned out to be one column with a national border running down the middle.

## One Billion Tokens, Two Invoices

Here is the argument as a single month's bill. Take a billion tokens at that mix, a middling month for one developer running an agent seriously, and price it both ways.

Qwen3.7 Max lists at $1.475 per million input. Claude Sonnet 5 lists at $2.00. On the pricing page Qwen is 26% cheaper and the decision looks made.

Run the billion tokens through: Qwen3.7 Max bills $355.00, Claude Sonnet 5 bills $301.68. The cheaper-looking model costs 18% more.

Neither price is wrong. Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice. The list price answered a question nobody asked.

That pair is not a cherry. Among the 40 rows there are 28 Chinese-American pairings where the Chinese model lists cheaper and bills the same or more.

While we are here: budgeting a billion tokens at Kimi K3's list input predicts $3,000. The real figure is $452.52, an overestimate of 6.6x. Anyone forecasting spend off a pricing page is not slightly wrong.

## Four Models Move Nine Places

Ranking by list price and ranking by effective price are not the same ranking. Sort all 40 both ways and watch who travels.

GLM 5V Turbo goes from 14th cheapest to 23rd. Qwen3.7 Max drops seven places to 27th, Grok 4.6 six to 33rd. Travelling the other way, GPT-5.1-Codex climbs seven, 19th up to 12th.

That is a long way to move on a number nobody checks. Anyone who picked a model off a list-price comparison last quarter has a live chance of holding one of those four.

## The Output Price Is a Decoy

A minute on why the sticker misleads, because it explains the rest.

Vendors compete on the output number because it reads as expensive, and because buyers screenshot it. A model at $50 per million output looks four times worse than one at $12.50. At 0.29% of volume that difference contributes almost nothing, while a cache read at 10% versus 20% of input moves the same bill by a third.

The pricing page is ordered by drama. The invoice is ordered by volume. Nobody publishes a table sorted the second way; the one behind this piece is sorted that way, and the puller that produces it is about a hundred lines.

## Where the Cheap Advantage Is Real

None of this makes the Chinese side expensive, and the corrected numbers are kinder to them than the headline ratio was.

Gemini 3.7 Flash is the cheapest of the 40 at $0.0566 effective, and DeepSeek V4 Pro sits right next to it. Exactly which side of it, though, is the one number in this table that will not hold still. The 2026-08-23 read put DeepSeek at $0.0501, ahead of Gemini; OpenRouter lists the same model a third higher a day later, which puts it at $0.0664, behind. DeepSeek is the one vendor here that prices by the clock — its own rate card is split into peak and off-peak hours, and off-peak is half — so any single figure for that row is a snapshot of an hour rather than of a price. The point of this section survives either way, and survives harder: at the bottom of the market the two sides have converged to inside a rounding error, and which one is nominally cheapest depends on when you look.

Eleven of the fourteen Chinese models beat the American median. That is a real advantage, and nothing here argues it away.

Thirteen of the twenty-six American models also beat the American median.

So "Chinese models are cheaper" is doing less work than it appears to. "Some models are cheaper" is the same claim with a shorter list of exceptions, and it points at a table instead of at a flag.

At the top of the market the flag stops meaning anything at all. Kimi K3 prices at $0.4525 effective. So do Claude Sonnet 4.5 and Claude Sonnet 4.6, to four decimal places. Whatever separates those three, it is not cost.

## What the Table Does Not Cover

Batch mode went aside earlier for a reason, and what happens there is worth saying. Across the 18 batch rows the list gap is 1.58x and the effective gap is 0.98x, meaning the Chinese rows come out marginally more expensive. Three of those rows are Chinese, which is too thin to carry a conclusion, so treat it as a question rather than a finding.

Twelve models also carry a second, higher price band past a context threshold, mostly at 200,000 tokens and 272,000 for GPT-5.4. Every figure here uses the base band. An agent routinely running a 300,000-token context is paying a different table than this one.

That cuts against the conclusion in places, which is the reason to state it.

## Run It Against Your Own Mix

That mix came from one person's agent, on one codebase, five months ago. Yours will differ, and the direction it differs in changes the answer.

Cache-read share is the whole ballgame. Push it down toward 80%, which short sessions and cold starts and a pile of new files will do, and the vendors with cheap cache reads lose their edge; the comparison drifts back toward the card price, and back toward the Chinese side. Push it past 98%, which long runs on a stable repo will do, and the flat-ten vendors stretch further ahead.

The useful question was never which country prices lower. It is what your cache-read percentage is. If you cannot say it to one decimal place, that is the number to go find this week, and it is already sitting in your API dashboard.

Better to ship the arithmetic than the conclusion. Three prices per model, three weights, one multiplication. Nothing here asks you to trust anyone about anything except the prices, and those you can pull yourself in about a minute.

*Also readable on [Telegraph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24).*


---

**Read next**

- [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md)
- [Choosing the Right AI Model for Coding: Cost vs. Efficiency](choosing-the-right-ai-model-for-coding-cost-vs-efficiency.md)
- [Claude Code and Codex for Office Automation](claude-code-and-codex-for-office-automation.md)

[All 53 write-ups](../README.md)

The 49 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 429 more, as JSON and CSV.


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
