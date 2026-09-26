# 63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers

![63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/63-billion-tokens-in-one-month-spent-writing-google-ads-for.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/73) — that copy has a reply box under it, and this one does not.*

On September 6 a marketer in a Chinese paid community posted his token bill. July: 55.7 billion tokens, seventh on that month's 30-day leaderboard, almost all of it through CodeX. A month later he updated the post — August came in at 63 billion. He isn't training anything. He writes Google Ads copy for Amazon merchants, and when someone clicks his ad and buys, he collects 5 to 20 percent. Six months of that added up to 13,000-plus in commissions. The token number is what got passed around. The arithmetic underneath it is the part worth your time, and a second operator's funnel numbers explain why most people who try this version of the business lose money on it.

## What 63 Billion Tokens Actually Bought

The mechanic is old affiliate marketing with the copywriting cost driven toward zero. He picks Amazon products, generates the ad copy, runs the ads on Google, and a buyer who clicks through and purchases pays him a commission somewhere between 5 and 20 percent depending on the category. Nothing about that structure is new. What's new is that one person can now keep hundreds of ad variants alive across hundreds of products, because the writing stopped being the bottleneck and the token bill became the bottleneck instead.

Here's the number pair I keep coming back to. Two figures, one business, six months. If both are right, the spread between them is ad spend plus tokens — which means the gross number everybody repeats and the number that lands in his account are more than three times apart. If you're sizing this up as something to copy, that gap *is* the business model.

He also names his own most expensive mistake, and it isn't a bad keyword. He got the flow working from zero to one and immediately tried to make the whole thing fully automatic, before the manual version had actually been proven out. The early build was thrown away, and so were the tokens that went into it.
## The Funnel Numbers That Explain Who Survives

An AI image generation tool used Google Ads to boost its monthly paying subscribers from approximately 80 to over 500, maintaining a customer acquisition cost of around $10 per paying user. This strategy proved effective, as the early paying cohort generated a total revenue of $215 each over an eleven-month period.

A 21-to-1 ratio sounds like a machine that prints money, and it mostly is — but read the time axis before you copy it. The $10 leaves your account this week. The $215 arrives over eleven months, which means the thing you actually need isn't a good ratio, it's enough cash to carry ten months of gap while the ratio resolves. That constraint, not the creative, is what kills most attempts at this.

The same write-up is unusually specific about how the ad account gets configured, and the sequence matters more than any single setting. Registration completed is the primary conversion goal at first, running at 20 to 30 signups a day. Only after 30-plus weekly purchases have accumulated does the goal switch over to completed payment. Underneath both, micro-conversions get instrumented — first image generated is the one named — so the funnel has intermediate events to optimize against instead of one sparse purchase event.

I read that sequence as a volume argument rather than a preference: an optimizer with two purchases a week has nothing to learn from, and pointing it at signups buys you enough events to be worth optimizing. The risk is the obvious one, and it's why the micro-conversions exist — signups are free to give away, and optimizing toward them recruits people who will never pay. Buffer's version of this lesson is blunter: the signal that someone might actually buy was the click on the pricing page, not the email address.

## One Word in a Keyword Costs You Ten Times

The single most transferable number in the August material is a comparison between two searches for the same product. People searching "free AI image generator" convert to paid at a lower rate than people searching "AI product photo generator for ecommerce."" The recommendation that follows is mechanical: filter "free" out of your keyword set entirely, and eat the lower volume.

That ten-times spread shows up again when you compare two Amazon-adjacent sites that both look like "traffic" in a dashboard. DiskPrices.com is a single page that lists hard drive prices pulled from Amazon. It does about 80,000 visits a month and around ¥5,000 a month in affiliate revenue, an effective RPM of $62.50 — five to ten times what most content sites earn per thousand reads. It ranks for a query where the searcher has already decided to buy a drive and only needs a price.

Now the other end. A game strategy site called MistriaFans, measured through August 23, had 778 clicks against 42,400 impressions, a 1.8% clickthrough rate and an average position of 8.9. Its ad network recorded 1,082 impressions and $1.37 in revenue over roughly ten days, an average CPM of $1.266. That site is one of ten built inside a 20-day automated run whose first payout was $7.25.

Same continent of tactics, same class of tooling, roughly a huge difference in what a thousand pairs of eyes are worth. If you're deciding what to point your generation pipeline at, that ratio should decide it, because the cost of producing the page is approximately the same either way.

## What This Costs Before It Pays Anything

 Two levers show up in the material, and they pull in different directions.

The first is upstream of the model. If your agent keeps producing something almost right, the fix may be that the requirement was never pinned down, not that the prompt was too short.

The second is downstream and cruder: change what you're paying per token. A local proxy called OpenCodex redirects Codex requests to Chinese models such as DeepSeek and Zhipu GLM, which sidesteps the five-hour quota window and reportedly cuts cost by more than 80% — 10 yuan of DeepSeek credit lasting several days, with measured latency in the 100–200ms range and model switching that doesn't break conversation context. For a workload that's generating thousands of near-identical ad variants, the quality bar per variant is low and the volume is enormous, which is the exact shape where this trade pays.

The prerequisite nobody in this material quantifies is the one that can end the whole thing in an afternoon: what happens when the ad account gets flagged. Affiliate advertising into Amazon at volume, with machine-written copy, is exactly the profile ad platforms police.

## Where I'd Put My Money Next

There's a pattern in a September 10 post from the same community that I think generalizes past its own subject. Someone went looking for people making money with MCP servers. Every documented case was the same shape: taking someone else's MCP and using it to make an existing business run more efficiently — one member running that play inside a business they already had reported 50,000 RMB a month. Cases of *selling* an MCP: zero. The project case library returned nothing at all for the search.

The same post sketches the one direction with real data behind it — product-selection data, described as the only category among 50 catalogued opportunities with case support — and a starting shape for it: fix the keyword-scraping logic, tag everything to a consistent standard, use a free leaderboard as the top of funnel, sell the full list behind a subscription. Nine paid overseas data products were checked and collapsed into three pricing shapes: monthly subscription, per-call, or both; the MCP endpoint itself usually isn't billed separately. The cheapest way in is to copy DataForSEO's per-call model first and only move to subscriptions once someone has actually paid. For calibration on what that market bears: indie developers report paying $10 to $50 a month for SEO data, a tenth to a quarter of a Semrush seat.

So here's my bet, and I could be wrong about it. The token-burning ad operator's advantage isn't the model and isn't the copy — anyone reading this can generate ad copy tonight. What he has that you'd need six months to rebuild is a conversion record telling him which keyword shapes pay and which ones only look like demand. That asset is the same category of thing as the product-selection dataset above, and it's the part that doesn't get commoditized when the next model ships.

The open question is where the switch happens. He automated right after getting to one working flow and paid for it in wasted tokens. The image-tool operator waited for 30 weekly purchases before he'd even let the ad platform change what it optimized for. Those are two very different tolerances for acting on thin data, and I don't think there's a general answer. If you've run paid acquisition against an AI product, what did you use as the threshold to stop doing it by hand?

*Also readable on [Telegraph](https://telegra.ph/63-Billion-Tokens-in-One-Month-Spent-Writing-Google-Ads-for-Amazon-Sellers-09-16).*


---

**Read next**

- [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](how-respond-io-built-a-35m-arr-business-by-billing-ai.md)
- [Charge Per Conversation, Not Per Seat: The Billing Model Behind AI Support](charge-per-conversation-not-per-seat-the-billing-model.md)
- [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md)

[All 67 write-ups](../README.md)

The 18 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 604 more, as JSON and CSV.

Topics: [SaaS Business](../topics/saas-business.md) · [AI Features](../topics/ai-features.md) · [Revenue Growth](../topics/revenue-growth.md) · [Customer Service AI](../topics/customer-service-ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** You've read about the revenue differences between different sites. If you were to choose to point your generation pipeline at one of the two sites (DiskPrices.com or MistriaFans) for better returns, which one would you pick? Reply with the site's name. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/73).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2F63-billion-tokens-in-one-month-spent-writing-google-ads-for.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2F63-billion-tokens-in-one-month-spent-writing-google-ads-for.md&title=%5Bcorrection%5D+63+Billion+Tokens+in+One+Month%2C+Spent+Writing+Google+Ads+for+Amazon+Sellers) — that form knows
which write-up you came from too; corrections and counter-data are the point.
