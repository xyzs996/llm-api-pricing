# The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill

![The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/96) — that copy has a reply box under it, and this one does not.*

Just pick the model with the lowest per-million-token price — that's how you keep your agent bill down — but that advice breaks the moment your agent touches any of three structural traps: time-of-day pricing, context-threshold repricing, and prepaid packages that expire or throttle, any one of which can double your bill and all three of which together can do worse.

Here's the shape of it before we go deep. While DeepSeek V4.1-Flash lists 3 yuan per million input tokens and 9 yuan output in off-peak hours — and doubles during the weekday daytime peak — GPT-6 series reprices the entire request once input crosses 272,000 tokens, so going from 270K to 300K can more than double the cost, which means the two models' headline rates diverge sharply depending on when and how much you send. LongCat sells 50 million tokens for 9.9 yuan, but the package has an expiry date and the service throttles at peak.

This article does one thing: takes those three layers apart so you can work out what your agent actually costs per month, instead of what the price table says it should.

## Where the per-token story actually holds

Let me be fair to the advice before I take it apart. In a narrow band of usage — static prompts, short context, off-peak calls — the price table genuinely predicts the bill. That band is real, and it's why the advice spread.

Look at the cheap end. DeepSeek V3.2 under the OpenClaw framework comes in at $0.26 per million input tokens and $0.38 output, the lowest-cost model in that particular comparison, while MiniMax M2.7 sits at $0.30 input and $1.20 output with a 204.8K context window, built for coding and agent workflows.

Those numbers aren't marketing. Those numbers aren't marketing, because they show up in real monthly bills, where one developer running three agents for email, calendar, and research put DeepSeek V4 Flash at roughly $3–5 per month against Opus 4.7 at $200–260 — with what they described as a small quality gap.

A full order of magnitude separates those two. That's why static price comparison became the default move.

But read the fine print on any of those tables. The DeepSeek figures are explicitly labeled off-peak prices, with weekday peak hours of 9:00–12:00 and 14:00–18:00 billed at twice the table rate, while every number above is a snapshot taken at a specific time of day and a specific context length, so that changing either one means the snapshot stops describing your bill.

Peak hours don't reach me.

If your agent only runs batch jobs at night on short prompts, you can stop reading. The rest of this is for the people whose agents get clicked.

## Cliff one — the clock doubles the same model

Time-of-day pricing is not a discount. It's the opposite framing, and the framing matters. The peak rate is the base rate; the off-peak rate is a temporary concession. Pick a model by its displayed price and you've implicitly assumed you'll always run off-peak.

DeepSeek's own documentation is blunt about this: the idle-period price is half the peak price, with weekday peaks at 9:00–12:00 and 14:00–18:00 billed at 2x the published table, while weekends all day, plus weekday 12:00–14:00 and after 18:00, are off-peak. The same structure repeats on V4.1-Flash: 3 yuan input and 9 yuan output off-peak, doubled during the weekday daytime window.

The 12:00–14:00 window still looks off-peak to me.

The counterintuitive part is what happens when a vendor ships a "cheaper" version. DeepSeek said V4.1 Flash's internal-test billing matches deepseek-v4-flash, with peak rates at 0.1, 3, and 9 yuan. So the developer's actual outlay didn't fall. Peak output is still 9 yuan per million tokens. Meanwhile the same test batch showed V4.1 Flash generating SVG code 6x faster than V4 Flash Vision-Exp and doing long-context retrieval more than 5x faster, yet faster is not the same as cheaper, and a new version number is not the same as a new price structure, because speed gains alone do not guarantee that the underlying cost of running the model has actually gone down for anyone paying the published rates.

Why does this bite coding agents specifically? Because the agent's call time is set by the user's click, not by you. Interactive daytime use lands in the peak window by default. You can't schedule your way out of a human typing at 10am.

And peak hours cost more than money, because first-token latency gets worse too — Claude Opus 5.5 hit 644 seconds at peak in deep-reasoning mode, against 1.1 seconds for DeepSeek V4.1 Flash and 0.9 seconds for Step 5 Preview. If you're paying double and waiting ten minutes, the peak window is charging you twice.

## Cliff two — one token over 272K reprices the whole request

This is the cliff most people don't see coming, because it isn't linear. It's a step function, and the step re-prices everything behind it.

On GPT-6 series, once input passes 272,000 tokens, the entire request is repriced: input and cache rates double, output rises 50%. That's not a marginal increase for a marginal input.

Coding agents walk straight into this. Repository-level tasks naturally push context toward the threshold. LongCat-2.0 natively supports a 1M token window and is positioned for repo-scale code edits and multi-step agent tool calls. DeepSeek V4.1 Flash's API changelog lists a 1M token context window and tests it on coding-agent tasks like DeepSWE and NL2Repo. The bigger the window, the easier it is to drift past a threshold you never noticed.

The fix exists, but know which layer it fixes. KV Cache compression cuts cache footprint and hit cost — DeepSeek V4.1-Flash squeezed its KV cache to a quarter of the previous generation's HBM footprint and an eighth of its SSD footprint. The 2026 batch of Chinese models all strengthened KV Cache compression, and once cache hits, real cost can fall to a tenth of list price. That's a real saving. It does not change the threshold repricing rule. You can have a perfectly warm cache and still trip the input-length step that doubles the rate.

## Cliff three — the package expires and throttles

Prepaid resource packs swap a unit price for a down payment, and the discount hides two costs: expiry and concurrency.

LongCat's 9.9 yuan gets you 50 million tokens, but both gifted and purchased packs carry expiry dates you're told to watch. The official note also advises off-peak use because heavy traffic causes peak-hour throttling. A pack you can't burn before it expires is a pack you paid for and didn't use. A pack you can't burn because you're throttled at the hour you need it is worse.

Free tiers have the same shape. They solve cold start, not the monthly bill, and their forms differ wildly. LongCat gives new verified users 10,000,000 tokens, with an API compatible with OpenAI and Claude so it drops into Claude Code, OpenClaw, Qoder and similar agents. Compare GLM-4-Flash: new users get 20 million tokens, permanently valid, 128K context, 30 concurrent. Same "free tokens" headline, completely different expiry and concurrency terms. One is a runway; the other is a coupon.

The 10,000,000 tokens don't reach me.

Concurrency is the hidden line item. DeepSeek V4.1 Flash's internal-test API capped each account at 20 concurrent requests and auto-retired after September 10 — a two-day evaluation window. If your workload needs more than 20 in flight, the cap decides whether you can spend the tokens inside the window at all.

The 20-request cap leaves me unpersuaded.

## What the table should look like instead

Put all three structures in one table with three columns — peak/off-peak windows, threshold trigger points, package expiry and concurrency limits — and stop ranking on unit price alone.

Concretely: DeepSeek must be labeled "off-peak price + 2x at peak," while Xiaomi's mimo-v2.6-pro at 3 yuan input and 6 yuan output is a flat rate. Those two cannot be compared as written. The low end has even lower anchors — Ant Group's Ling-3.0-flash at 0.12 yuan input and 0.38 yuan output, Qwen3.8-Flash at 0.2 yuan input and 2 yuan output. Nice numbers, but only meaningful once you know whether they're peak or flat.

The better unit is cost per successful task, not per million tokens. DeepSeek V4.1 Flash scores 96.0 on coding at $0.181 per successful task. GPT-6 Sol scores 33.2% on AutomationBench, beating Claude Opus 5's 26.9%, at 9% of Opus 5's per-task cost. Per-task cost already folds in retries, context length, and failure — the things a per-token price hides.

And similar list prices do not mean similar bills. On a writing task where Claude Fable 5.2 and Gemini 4 Carbon both scored 99/100, the monthly API bills came to $462.60 and $116.10 — roughly a 4x gap.

## How to read a pricing page from now on

Three questions, in order. First: which time window is this price for? DeepSeek's official terms only make sense read alongside the peak schedule — weekday 9:00–12:00 and 14:00–18:00 peak, everything else including weekends at half. Second: where's the threshold, and what happens past it? Read the clause that says the entire request is repriced, not just the overage rate. Third: what are the expiry and concurrency limits on the quota or pack?

The 12:00–14:00 gap looks overstated to me.

Then make a real trade. Off-peak batch jobs save money; real-time responses can't be shifted off-peak. That's a genuine exchange between bill and experience, not an optimization you can have both ways. The peak/off-peak structure repeats across multiple price tables, which tells you it's a stable mechanism and not a temporary promo — worth designing your call schedule around it.

Off-peak saves me real money.

All prices above are as of their capture dates; check each vendor's official page before you commit.

*Also readable on [Telegraph](https://telegra.ph/The-Same-Model-Costs-2x-More-at-10am--Three-Pricing-Cliffs-That-Blow-Up-Your-Coding-Agents-Bill-11-23).*


---

**Read next**

- [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](running-deepseek-v4-pro-inside-claude-code-a-cost-and.md)
- [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md)
- [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md)

[All 77 write-ups](../README.md)

The 30 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 901 more, as JSON and CSV.

Topics: [Artificial Intelligence](../topics/artificial-intelligence.md) · [AI Programming](../topics/ai-programming.md) · [Software Development](../topics/software-development.md) · [Token Optimization](../topics/token-optimization.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** When your coding agent last ran during DeepSeek's weekday peak window, did it land in the 9:00–12:00 block or the 14:00–18:00 block? Reply saying which one — from memory, no lookup. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/96).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md&title=%5Bcorrection%5D+The+Same+Model+Costs+2x+More+at+10am+%E2%80%94+Three+Pricing+Cliffs+That+Blow+Up+Your+Coding+Agent%27s+Bill) — that form knows
which write-up you came from too; corrections and counter-data are the point.
