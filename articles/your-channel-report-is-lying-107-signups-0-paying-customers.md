# Your Channel Report Is Lying — 107 Signups, 0 Paying Customers

![Your Channel Report Is Lying — 107 Signups, 0 Paying Customers](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-channel-report-is-lying-107-signups-0-paying-customers.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

ReelDrop's first two months produced 1,118 signups and 28 paying customers, about CA$2,150 collected after refunds and before Stripe fees. That works out to roughly 2.5% signup-to-paid overall, which sounds like a mediocre but unremarkable early SaaS number.

Then you break it out by channel and the mediocrity disappears.

The UGC creator channel brought 107 signups and zero paying customers. The referral program brought 17 signups and zero paying customers. The channel with the second-most signups earned nothing; the channel with the fourth-most signups earned more per head than anything except X.

If you're sitting on a dashboard that ranks channels by signups, that table is telling you to double down on UGC creators and quietly ignore X. It is wrong, and the reason it's wrong is worth an hour of your afternoon.

## The Numbers, Laid Out Side by Side

ReelDrop's first-touch attribution puts search at 8 paid customers from 472 signups, a 1.7% conversion rate. ChatGPT accounts for 6 confirmed paid customers from 83 signups, 1.2%. X, as above, 3 from 42.

Sort by signups and you get search (472), UGC (107), ChatGPT (83), X (42), referral (17). Sort by paid customers and you get search (8), ChatGPT (6), X (3), UGC (0), referral (0). Those two orderings share almost nothing past the top slot. Search is both the biggest signup source and the biggest paid source, so it survives the re-sort — but its conversion rate is a quarter of X's.

Before anyone builds a strategy on this, the sample size deserves a hard look. Twenty-eight paid customers total. X's "7%" is 3 out of 42 — shift one or two customers either way and the rate moves by several points. The UGC channel's zero is 0 out of 107, which is a bigger and more stable zero, but the gap between "UGC is worthless" and "UGC is slow" is not something 107 signups can settle. Treat every percentage in that table as a hypothesis with a confidence interval wide enough to drive a truck through.

What the table can do is tell you where to look next.

## The Search Console Number That Reframes Everything

Here's the detail that made me put down my coffee. In ReelDrop's Search Console data, 1,463 clicks had a query attached. Of those, 1,215 were people searching the brand name "reeldrop."

That's about 83%. Non-brand clicks: roughly 248.

Sit with that for a second. The channel your report labels "Google search," the one with 472 signups and 8 paid customers, is overwhelmingly people typing your product's name into a search box. They didn't discover you in a search result. They heard about you somewhere else — a tweet, a video, a friend — and then opened a new tab and searched for you by name. First-touch attribution credits search with the discovery. Search did not discover them. Search collected them.

This is why "search has the most signups" and "search has a 1.7% conversion rate" can both be true at once without meaning what they appear to mean. Search is a closing channel wearing a discovery channel's name tag. The people arriving through it already decided; the page just had to not ruin it.

Purple Palm AI, an AI SaaS for e-commerce owners, shows the same distortion from the other direction. It went from its first paying customer in September 2025 to 12 paying customers and 116 total registered users by February 2026, with €0 spent on ads. Most early users came from Instagram DMs and forum outreach done by hand. Manual outreach like that usually leaves no UTM trail. Those signups land in your analytics as direct or organic, and the channel that actually did the work gets credited to "direct" — which is to say, to nobody.

The 116 users don't convince me.

One honest limit: ReelDrop's original post gives the brand-query click count but not how many signups or paid customers those clicks produced. The brand-name search share proves search attribution is inflated. It does not let you calculate by how much.

## Three Numbers to Pull Before You Trust Your Own Report

You can run this audit on your own product this week. It takes three queries and no new tooling.

The first is paid conversion rate per channel, not signup count. Line up your PostHog or GA signup table against your Stripe customer table and divide. ReelDrop's aligned numbers are search 1.7%, ChatGPT 1.2%, X about 7%, UGC and referral 0%. When 107 signups produce zero revenue and 42 signups produce three paying customers, the channel to cut is the one with the bigger number. A rough early-stage rule: a channel with a large signup count and zero paid customers does not deserve more of your hours until you understand why the zero is there. The referral program's 17 signups and zero paid is the same story at smaller scale.

The third is keeping the two ledgers separate. ReelDrop's 1,118 comes from PostHog; its 28 comes from Stripe. Two systems, two definitions, two numbers that only mean something printed next to each other. Read only PostHog and you have "over a thousand users in two months." Read only Stripe and you have "28 orders in two months." Both are true. Neither is the business.

For contrast, consider a developer who ran Google Ads at $5/day, initially picking up 7–8 users per day, and reached 20-plus paying customers in 65 days. He then tapered the ad spend as organic traffic from Reddit and similar communities took over, ending at 1.6k+ signups and 60k+ visitors. That path has both ledgers filled in — signups and paid customers — but it still doesn't split brand versus non-brand queries. If you're thinking of copying it, add that step yourself before you conclude the ads did the work.

All three metrics are after-the-fact attribution tools. None of them replaces asking a paying customer, in person, where they first heard about you. ReelDrop's post doesn't include that data, and with 28 paid customers, every channel conclusion in it should be filed under "unverified."

## What the Report Leaves Out: The Cost Side

Every channel in that table has a price, and the table shows none of them.

Purple Palm AI's 12 paying customers came from Instagram DMs and forums over eight months at €0 in ad spend. Zero ad spend is not zero cost. Somebody sat and sent those DMs. The post doesn't put a number on the hours, which means the channel's true cost is invisible in exactly the way its signups are visible. During the same stretch, the founder also reworked onboarding so free users generate content immediately after signup, raised Google page performance from 35 to 72, and made the landing page and dashboard fully mobile-friendly. None of that produces a signup on a dashboard. All of it affects whether a signup becomes a payment.

Content channels carry the same hidden invoice. One AI micro-SaaS pulled 90% of its organic traffic from TikTok and Instagram Reels — raw, native content, before-and-after clips of a messy voice note versus the cleaned-up text. The founder's own word for it was "exhausting," and noted that paid ads had failed before the pivot to organic social. The payoff was real: about 6,000 users, $4,500 MRR, eventually sold for a low-to-mid five-figure sum. But "90% of traffic" is a revenue-side statistic with no hours column attached.

SaaS isn't my game.

And the cheap end of paid acquisition is often just cheap. One developer spent about €25 on Meta Ads for 80 clicks and about €30 on Reddit for 40 clicks. Signups from both: zero. At that scale you're not buying customers, you're buying a data point that says small budgets don't buy customers.

The €25 result doesn't surprise me.

ReelDrop's own post doesn't disclose what the two months of acquisition cost — content production, any paid UGC partnerships, founder hours. The CA$2,150 is revenue, not profit, and the gap between those two words is where most channel reports quietly die.

## Running the Audit on Your Own Numbers

Start by joining the two tables. Take your analytics signup counts by channel and your payment processor's customer list, match them on user ID or email, and compute paid conversion per channel. ReelDrop's joined output is the template: search 1.7%, ChatGPT 1.2%, X about 7%, UGC and referral 0%. If you can't join them because your signup events don't carry a channel field, that's the first thing to fix, and it's a one-afternoon fix.

Then pull Search Console's query-attached clicks and compute your brand share. ReelDrop's benchmark is 1,215 out of 1,463. If the bulk of your query-attached clicks turn out to be people typing your product name, treat your "search" and "organic" rows as collection channels until proven otherwise, and go find the discovery channel your report is hiding.

Then take every channel with signups and zero paid customers and do a manual review. Pull ten of those signups, look at their session recordings or their onboarding drop-off, and figure out whether the channel sent you the wrong people or your attribution simply lost the thread — no UTM, a direct visit, a link shared in a DM. That distinction changes the decision completely.

UTM's the part I'd doubt.

Three steps gets you correlation. To get causality you have to talk to paying customers and ask where they first heard about you, and no analytics tool will do that part for you. ReelDrop's post doesn't include it, which is precisely why its channel table should be read as a map of where to investigate rather than a verdict on where to spend.

*Also readable on [Telegraph](https://telegra.ph/Your-Channel-Report-Is-Lying--107-Signups-0-Paying-Customers-11-28).*


---

**Read next**

- [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](63-billion-tokens-in-one-month-spent-writing-google-ads-for.md)
- [Charge Per Conversation, Not Per Seat: The Billing Model Behind AI Support](charge-per-conversation-not-per-seat-the-billing-model.md)
- [Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else](your-channel-report-is-lying-1-215-of-1-463-branded-search.md)

[All 81 write-ups](../README.md)

The 21 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 978 more, as JSON and CSV.

Topics: [SaaS Business](../topics/saas-business.md) · [Revenue Growth](../topics/revenue-growth.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-channel-report-is-lying-107-signups-0-paying-customers.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-channel-report-is-lying-107-signups-0-paying-customers.md&title=%5Bcorrection%5D+Your+Channel+Report+Is+Lying+%E2%80%94+107+Signups%2C+0+Paying+Customers) — that form knows
which write-up you came from too; corrections and counter-data are the point.
