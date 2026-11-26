# Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else

![Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-channel-report-is-lying-1-215-of-1-463-branded-search.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/94) — that copy has a reply box under it, and this one does not.*

ReelDrop launched two months ago and collected 1,118 signups, 28 paying customers, and about CA$2,150 after refunds and before Stripe fees. Sorted by signups, the channels look healthy. Sorted by revenue, one of the biggest ones is a zero. Search brought 472 signups and 8 paid customers, a 1.7% conversion. ChatGPT brought 83 signups and 6 paid, 1.2%. X brought 42 signups and 3 paid, roughly 7%. Two channels, UGC creators and the referral program, brought 124 signups between them and not one dollar.

So the signup leaderboard and the revenue leaderboard give you two different answers about the same two months. This is a breakdown of why, and how to reconcile three data sources until the numbers agree.

## What Two Months and 1,118 Signups Actually Earned

Start with the revenue definition, because it decides every denominator below. The 28 paying customers and the roughly CA$2,150 are measured after refunds and before Stripe fees. If you read CA$2,150 as net deposits, you are already ahead of the bank. Stripe still takes its cut on top of that figure, and any refund issued after the report was pulled is not in it either.

 Hold that number. It is the baseline every channel gets compared against, and most of them lose to it.

Now split by first-touch attribution. Search: 472 signups, 8 paid. ChatGPT: 83 signups, 6 paid. X: 42 signups, 3 paid. Add those three up and you get 17 paid customers out of 28. Less than two-thirds. The rest of the paying customers do not have a clean channel attribution in the report, which is itself worth knowing before you start making budget decisions off it.

The ChatGPT number deserves a second look, because it runs against the mood of the last year. Eighty-three signups and 6 paid is 1.2%, below search's 1.7%. Everyone assumes traffic arriving from an AI assistant must be further down the funnel. In this account it is not. That may be a property of this product, or it may be 83 signups being too few to say anything at all.

Either way, the intuition did not survive contact with the report.

If you are running this playbook on your own product, the honest framing is that two months and 28 paid customers is not enough evidence to rank any channel's long-term value. A single good or bad month flips the order. The gap between 1.7% and 7% rests on 3 paid customers out of 42 signups. Write the sample size next to every conversion rate in your own report, or you will make a confident decision on a coin flip.

## The 1,215 Clicks That Were Never Google's

Here is the piece of evidence that reframes everything above. Search Console showed 1,463 clicks with a query attached. Of those, 1,215 were people searching "reeldrop.

Think about what a branded search means. Nobody discovers a product by typing its exact name into Google. They type the name because they already heard it somewhere else — a post on X, a friend's recommendation, a video from one of those UGC creators who supposedly converted nobody. Then they go to Google, type the name, click the first result, and sign up.

The report credits Google.

Two mechanisms stack here. First-touch attribution assigns the whole user to whichever tracked link they hit first, and a branded search click is a tracked link. Search attribution then treats the query as discovery when it was really a return visit. The user gets counted twice: once as a social or word-of-mouth win that the report never sees, and once as an organic search win that the report overstates.

This is exactly why the search channel can carry 472 signups and still convert at only 1.7%. The pool is contaminated with people who were going to convert anyway. You are not measuring how well Google finds new buyers. You are measuring how many existing fans can spell your product name.

The same ambiguity shows up in smaller accounts. One developer launched a SaaS and waited 2.5 months for the first paying customer, a $7 sale, and reported that the customer found the product through Google organic search. Maybe that was genuine discovery. Maybe they had seen the product somewhere and searched the name. A single case like that cannot separate branded from non-branded, which is why the Search Console query export matters more than the channel column.

One caveat before you apply these numbers to your own product. "Reeldrop" is a made-up word. Nearly every search for it is a search for this product. If your product is named after a common phrase, your branded share will be lower and your search channel will look worse — not because your marketing is weaker, but because your name is doing different work.

## Four Other Ledgers, and What They Do and Don't Prove

Before treating ReelDrop as a template, look at how other small products got their first paying customers. The channel mix differs every time, which is the point.

Purple Palm AI, a SaaS for e-commerce owners, spent €0 on ads and went from its first paying customers in September 2025 to 12 paying customers and 116 total registered users by February 2026. The acquisition was almost entirely manual: Instagram DMs and forum conversations. The cost does not appear in any ad report, because the cost was the founder's hours. That is a real line item, and it is invisible in every channel dashboard. The same founder also optimized onboarding so free users start generating content immediately after signup, and pushed Google page performance from 35 to 72 — the kind of work that never shows up as a channel but shows up in whether those 116 registered users ever come back.

A second product got its first customer through a friend's Shopify store at about $6/month billed annually, $72 for the year. Customers two and three came from posting on a subreddit, with the product still primitive, at $9/month. Everyone after that arrived by word of mouth, including one heavy user who handles around 5,000 questions a month. Note what the ledger would say: Reddit, 2 signups, 2 paid.

A 100% conversion rate on a sample of two.

A third case tested the paywall timing instead of the channel. Thirty days of posting usage scenarios on Reddit and X produced 5,000 visitors and 367 users. The paywall went up and the first sale landed five hours later; three days brought 3 sales and $90. Collecting registrations first and charging later did not produce a better conversion rate. The same pattern shows up in the ReelDrop numbers: 1,118 signups against 28 paying customers, with the biggest registration channels — 107 signups from UGC creators and 17 from a referral program — converting to zero paid. If you are sitting on a few hundred free users wondering why the paywall underperforms, look at which channel they came from before you blame the price.

And the negative case, which is the most useful one if you are tempted to "just test some ads." One founder spent €25 on Meta Ads for 80 clicks and €30 on Reddit for 40 clicks. Zero signups from either. At this scale, paid acquisition did not even buy registrations, let alone customers. A channel that produces clicks and no signups does not belong in your comparison table as "needs optimization." It belongs outside the table.

None of these four can be compared to each other on conversion rate. Different products, different prices, different maturity. What transfers is the method: pull two columns per channel, signups and paid, not one.

## Three Columns, One Cut

The fix for the report is one extra column. Signups, paid customers, and branded search share. The third column is what exposes the attribution error, and it is the one nobody fills in.

Concretely: export Search Console by query, count the clicks containing your product name separately, and either subtract them from the search channel's signups or flag them. The rule of thumb — any channel where branded queries exceed half its attributed signups is having its conversion rate systematically overstated.

Then cut by conversion rate, not by signup volume. On this ledger, UGC creators (107 signups, 0 paid) and the referral program (17, 0) are the first two to go, and X (42, 3) is the one to keep. But 42 signups is a small sample, so the correct move is to keep X and put more into it while continuing to watch, not to declare it the answer. Purple Palm AI's 116 signups and 12 paid is a reminder that small products routinely post high conversion rates on tiny samples. Do not overfit.

The last column nobody puts in the report is replicability. One developer got all three of his first paying customers from direct DMs and conversations he started himself. That path does not automate, which is why it should not sit in the same ranking as paid channels. Manual channels get their own table, and their cost gets written down as founder hours. A channel you cannot repeat at ten times the volume is not a growth channel yet, however good its conversion rate looks.

There is a broader version of this argument. One developer deliberately shifted focus away from acquiring trial users and toward onboarding, retention, and expansion, explicitly dropping signup count as a vanity metric. The three-column ledger is the same idea applied to channels: the number that decides where your next hour goes is paid customers per channel, with the branded-search contamination stripped out first.

If you take one thing from this: pull the query-level export before you reallocate a single dollar. The channel column told ReelDrop that search was its biggest source of signups. The query column told a different story: of the 1,463 Search Console clicks that had a query attached, 1,215 were people typing the brand name "reeldrop" — users who had already heard about the product somewhere else and came back to search for it by name. Two reports, same two months, opposite conclusions.

One of them is right.

*Also readable on [Telegraph](https://telegra.ph/Your-Channel-Report-Is-Lying--1215-of-1463-Branded-Search-Clicks-Came-From-Somewhere-Else-11-19).*


---

**Read next**

- [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](the-hidden-cost-of-ai-automation-turning-human-instincts.md)
- [A 30-Line Script, 200 Users, and a Niche Nobody Wanted](a-30-line-script-200-users-and-a-niche-nobody-wanted.md)
- [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md)

[All 79 write-ups](../README.md)

The 18 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 956 more, as JSON and CSV.

Topics: [SaaS Business](../topics/saas-business.md) · [AI](../topics/ai.md) · [Micro SaaS](../topics/micro-saas.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** Of the paying customers you can trace, how many first heard about your product through a branded Google search rather than discovering it there? Reply with that number — reply in the thread. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/94).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-channel-report-is-lying-1-215-of-1-463-branded-search.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-channel-report-is-lying-1-215-of-1-463-branded-search.md&title=%5Bcorrection%5D+Your+Channel+Report+Is+Lying+%E2%80%94+1%2C215+of+1%2C463+Branded+Search+Clicks+Came+From+Somewhere+Else) — that form knows
which write-up you came from too; corrections and counter-data are the point.
