# The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.

![The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/91) — that copy has a reply box under it, and this one does not.*

Qwen3.8-Flash lists 0.2 yuan per million input tokens and 2 yuan per million output tokens. DeepSeek V4.1-Flash lists 3 yuan in and 9 yuan out during off-peak hours. On paper that is roughly a 9x gap on input, and if you picked your coding agent off a price table you already know which column you circled.

Then you run the agent on a Tuesday afternoon and the invoice does not behave like a 9x gap. DeepSeek's own pricing page says the off-peak rate is half the peak rate, and peak is weekdays 9:00–12:00 and 14:00–18:00 — which is, inconveniently, when most of us are at a keyboard.

This piece does one thing: it takes the four ledgers that decide what you actually pay — sticker price, peak/off-peak, cache hits, and plan quotas — and shows how to pick a model from the bill instead of the table.

One caveat before the numbers. Every price below was pulled in September–October 2026 from vendor pages and third-party price tables, and vendor pages win when they disagree.

## The sticker price is the off-peak price, and you work during peak

Start with the trap that costs the most money and gets mentioned the least.

Most Chinese price tables list DeepSeek's rates as off-peak numbers. The convention is stated openly on the vendor side: off-peak is half of peak, peak is weekdays 9:00–12:00 and 14:00–18:00, and everything else — weekends all day, weekday lunch 12:00–14:00, evenings after 18:00 — bills at the lower rate.

So the 3/9 figure everyone quotes is a night rate. If your agent runs while you are awake and working, you are on the 2x column — DeepSeek's peak pricing doubles the listed rate for weekday mornings and afternoons — so the real comparison against Qwen3.8-Flash is far wider on input than the headline suggests, and that is before cache hits, which I will get to.

This is not a launch-week promotion, either. The same peak/off-peak rule shows up in a price table dated 2026-10-12, a month after V4.1-Flash shipped, worded the same way. If you were hoping the doubling would quietly go away, the calendar says otherwise.

The second half of the trap is that "cheaper" and "cheaper for you" are different claims. When DeepSeek launched V4.1-Flash, the official line was that current beta billing matched deepseek-v4-flash, with peak rates at 0.1, 3, and 9 yuan depending on the tier. Developers reading that as a discount found their actual spend unchanged, because the model got faster, not cheaper. The same beta run reported SVG code generation about 6x faster than V4 Flash Vision-Exp and long-context retrieval more than 5x faster. Faster is real. Faster is not a lower bill.

Can you just move your calls? Sometimes. Batch jobs — overnight re-indexing, test-suite runs, bulk summarization — can be scheduled into the 18:00-to-9:00 window and you genuinely capture the half rate. An interactive coding agent cannot. You type when you type.

There is a third variable that changes the shape of the bill rather than the rate: concurrency. The V4.1-Flash beta capped each account at 20 concurrent requests, and the model name implied the endpoint would expire on September 10 — leaving developers a two-day window to test. If you plan to benchmark a new model against your real workload, a 20-concurrency ceiling and a two-day window will not get you there. You will end up extrapolating from a handful of runs, which is exactly the estimation method this article is arguing against.

The 20-request cap doesn't convince me.

## Cache hits cut the bill to a tenth — if you hit

Here is the variable with the largest swing, and the one almost nobody puts in a spreadsheet.

The 2026 generation of Chinese models all pushed hard on KV cache compression, and the published figure is that a cache hit drops your real cost to about one tenth of the sticker price. Not one tenth off. One tenth of.

That single number matters more than your model choice for any RAG pipeline or agent that re-sends the same system prompt, the same tool definitions, and the same retrieved context on every turn. Your effective rate is not the table rate. It is the table rate times your miss rate, plus a tenth of the table rate times your hit rate.

The hardware side of caching got cheaper too, which matters if you are weighing local deployment rather than API calls. V4.1-Flash cut KV cache to a quarter of the previous generation's HBM footprint and an eighth of its SSD footprint. For an API user that is invisible. For anyone budgeting a local box, it is the difference between fitting and not fitting.

The flip side of cache discounts is threshold repricing, and this is where linear extrapolation breaks outright. On the GPT-6 series, once input crosses 272,000 tokens the whole request is repriced: input and cache rates double, output rises 50%. Going from 270,000 to 300,000 tokens of input can more than double the cost of that call. Notice what that does to your estimate. A per-token multiplication gives you a smooth line. The invoice gives you a cliff — and the width of that cliff is exactly the gap between the threshold and the input size you were quietly assuming. Budget for the token count you actually send, not the one your spreadsheet averaged.

If your workload lives above 100K tokens, flat pricing is worth more than a low headline rate. GLM 5.3 Flash charges a single token price regardless of length, which sidesteps the long-context premium jump that models like Haiku apply. Predictability is a feature. You cannot budget against a rate schedule you have to read three times.

## Cheap per token is not cheap per finished task

Now the metric that should replace the price table.

The right number is the total cost of completing one acceptable task, not the cost of a million tokens. A model that thinks longer and writes longer chains can eat most of a 60% sticker-price advantage through sheer volume.

There is hard data for this on the coding side. DeepSeek V4.1-Flash scores 96.0 on coding and costs $0.181 per successful task — close to Fable 5.1's 97.7 and ahead of Mistral Large 4's 95.4, at a fraction of the per-task cost. That $0.181 is the number to compare, not the 3/9 yuan. It already has the thinking tokens, the retries, and the failures baked in.

Latency belongs in the same table, because a slow model is an expensive model once you count your own time. First-token latency in that same comparison: Step 5 Preview 0.9s, DeepSeek V4.1 Flash 1.1s, GLM-5.3 1.9s, and Opus 5.5 at max reasoning strength a staggering 644 seconds. Six hundred and forty-four seconds to first token is not a coding agent. It is a batch job wearing a chat interface.

644 seconds doesn't reach me.

At the bottom of the market, the absolute differences get small enough that optimizing them is a hobby rather than a strategy. Ling-3.0-flash lists 0.12 yuan in and 0.38 yuan out, one of the cheapest lightweight tiers available. Compare that to Xiaomi's mimo-v2.6-pro at 3 yuan in and 6 yuan out, which tops the value ranking at 7.7 with an intelligence index of 46.3. The gap between those two on a month of light use is a few dollars.

Do not spend a week of engineering time to capture it.

For scale on what a real month looks like: three agents doing email, calendar, and research ran about $3–5 per month on DeepSeek V4 Flash against $200–260 on Opus 4.7, with what the user described as a small quality gap. At that order of magnitude, peak/off-peak and cache hit rate move your bill more than the per-token rate does. You are optimizing the wrong decimal.

## Pick DeepSeek V4.1-Flash, and pay these three costs

Time to commit. For a coding agent that runs as your daily driver, the pick is DeepSeek V4.1-Flash — and the reason is the $0.181 per successful task and the 96.0 coding score, not the 3/9 yuan on the price table.

The first cost you accept is peak pricing. Weekdays 9:00–12:00 and 14:00–18:00 bill at double, and an interactive agent cannot dodge those windows. Budget at the peak rate for anything you do while sitting at the desk, and treat the off-peak rate as a bonus you get for scheduling batch work overnight.

The second cost is a capability ceiling on the ultra-cheap tier. Ling-3.0-flash at 0.12/0.38 yuan is positioned as lightweight, and that is what it is — fine for classification, extraction, short summaries, not a coding mainstay. If you try to run your agent on it to save three dollars, you will spend the savings on retries.

The third cost is beta risk. New versions arrive with 20-concurrency caps and two-day expiries, which will break your load test at the worst possible moment. Pin your production model to a stable endpoint and test new releases on a side key.

Two cases where you should not pick it. If your prompts routinely exceed 100K tokens, take GLM 5.3 Flash for the flat pricing and skip the long-context cliff entirely. If you need the highest intelligence ceiling available domestically, Xiaomi's mimo-v2.6-pro sits at 46.3 on the intelligence index — 10th globally — at 3 yuan in and 6 yuan out. That is a real step up in capability for a real step up in price, and it is the right trade for hard reasoning work.

Before you switch anything, do the arithmetic once. Take the off-peak rate, multiply by the share of your calls that land in peak windows, then multiply by your cache miss rate plus a tenth of your hit rate. That last term carries the most weight of anything in the formula, which means the change that matters most this week is not a model swap.

It is making your prompts cacheable.

*Also readable on [Telegraph](https://telegra.ph/The-Sticker-Price-Said-9x-Cheaper-My-Bill-at-Peak-Hour-Didnt-Move-11-16).*


---

**Read next**

- [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](the-hidden-cost-of-ai-automation-turning-human-instincts.md)
- [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md)

[All 75 write-ups](../README.md)

The 18 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 857 more, as JSON and CSV.

Topics: [Artificial Intelligence](../topics/artificial-intelligence.md) · [AI Programming](../topics/ai-programming.md) · [Token Optimization](../topics/token-optimization.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** What share of your agent's input tokens actually hit the cache — reply with your rough hit rate, in one word or a percentage, from memory. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/91).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md&title=%5Bcorrection%5D+The+Sticker+Price+Said+9x+Cheaper.+My+Bill+at+Peak+Hour+Didn%27t+Move.) — that form knows
which write-up you came from too; corrections and counter-data are the point.
