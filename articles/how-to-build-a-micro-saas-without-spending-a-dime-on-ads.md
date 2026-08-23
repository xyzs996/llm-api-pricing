# How to Build a Micro-SaaS Without Spending a Dime on Ads

![How to Build a Micro-SaaS Without Spending a Dime on Ads](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/how-to-build-a-micro-saas-without-spending-a-dime-on-ads.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/27) — that copy has a reply box under it, and this one does not.*

Jordan posted an introduction thread across 3 Reddit sub-boards and had 200 people asking for access within days, at zero cost, and those users stuck around better than the paid traffic he never bought. He wrote 15 blog articles after that. Five of them, all aimed at the phrase Poshmark Automation, carry most of the organic search traffic to this day. The other ten are still up.

The tool itself started as a 30-line script that clicked the share button on his wife's Poshmark listings so she did not have to. Here is the order those two things happened in, why the Reddit thread worked when most launch posts do not, and what the five-out-of-fifteen ratio says about writing for search.

## The Origin: Solving a Wife's Daily Reselling Chore with 30 Lines of Code

The script came before the business. Jordan watched his wife spend a chunk of every evening clicking the share button on her own Poshmark listings, because the platform rewards sellers who re-surface their inventory and quietly buries the ones who forget, and he wrote 30 lines of JavaScript to do the clicking for her.

Nothing about that origin is strategic.

It is worth dwelling on for exactly that reason. The standard advice tells a founder to find an underserved niche, size the market, and validate the opportunity, which describes a research process Jordan never ran. He had one user, in his house, whose problem he could watch happen every evening, and the distance between noticing the problem and shipping 30 lines that fixed it was one sitting rather than six weeks of discovery calls.

That collapses the riskiest part of a micro-SaaS. The usual failure is not building the wrong feature, it is spending two months building the right feature for a customer who turns out not to exist. A household chore cannot be imaginary. You either watch someone do the work every day or you do not, and if you do, you already know its frequency, its tedium, and the exact click that hurts. The trap on the other side is that a personal itch generalizes badly, and most of them do. What made this one generalize was arithmetic rather than insight. Poshmark's mechanics make sharing mandatory for every seller on the platform, so 30 lines that fix it for one seller fix it for all of them, and the only open question left was whether those sellers could be reached without an ad budget.

## The Validation and Cold Start: Getting the First 200 Users on Reddit Without Ads

They could. Jordan wrote a plain introduction thread describing what the tool did, that he had built it for his wife, and that it was available, then posted it to 3 related Reddit sub-boards. Within days, 200 people had raised their hands. The posts collected roughly 200 upvotes, and the users who arrived that way stuck around better than paid traffic does.

Most launch posts in these communities fail, and the reason is usually visible in the first line. A post that opens with a value proposition reads as an ad, gets treated as one, and dies at 3 upvotes. A post that opens with the specific chore everyone in that sub-board performs every single day reads as a person talking, and the tool at the end of it lands as a favor. The difference is not tone, it is whether the writer knows the chore, and 200 upvotes across 3 sub-boards is what knowing it looks like from the outside.

The retention claim is the part worth taking seriously, and also the part hardest to check. Users who arrive from a sub-board dedicated to their own daily work have self-selected for the exact pain the tool removes, while paid traffic selects for whoever the ad platform decided to show the ad to. That gap is real across small products.

Jordan's own number is still a founder's number about his own product, and those run optimistic.

Two other zero-budget launches point the same way. Sam Shore handed roughly two-thirds of Typeshare's equity to two people with established audiences, Dickie and Cole, and monthly revenue moved from $10,000 to $15,000 inside 30 days. Zigpoll drew about a third of its new registrations straight from the Shopify App Store, where merchants already go looking for that kind of tool.

Neither founder bought attention. Both went where the attention already pointed at their problem, one by renting an audience at a price most founders would refuse, the other by sitting in the catalog its customers already browse.

## The Growth Engine: Driving Organic Traffic with Just 15 Targeted SEO Articles

After Reddit came search, and the numbers there are unusually clean. Jordan's entire blog is 15 articles. Five of them, all built around the phrase Poshmark Automation, carry most of the organic traffic. The other ten still exist and still do close to nothing.

That 5-out-of-15 ratio is the useful part of the whole story, because it inverts what content advice tells solo founders to do. Volume is the standard prescription, and volume is also the one thing a single person cannot sustain alongside building and supporting a product. What the blog suggests is that the winners were not the 5 written best. They were the 5 written against a phrase people type once they have already decided they want the thing, and no amount of quality rescues an article aimed at a phrase nobody searches.

"Poshmark Automation" is that kind of phrase. Someone typing it is not researching whether reselling is a good business. They are looking for a tool that automates the task they are sick of, so the article that meets them there does not have to persuade anybody of anything, which is why 5 of them outrun 10.

The honest caveat is that this is one blog's outcome, reported after the fact. Nobody knew which 5 would win before they were written, and the 10 that failed were presumably written with the same intent and the same care. The takeaway is not "write 15 articles and pick 5." It is that a minority of them will matter, so keep the total small enough that the failures stay cheap.

## Execution Guardrails: Navigating Platform Risks and Hidden Operational Costs

The unglamorous risk here is the platform itself. Automating clicks on a marketplace that never asked to be automated carries a permanent possibility of anti-bot detection and account suspension, and the person who eats that risk is the seller, not the tool.

Browser automation that drives a real local browser and imitates human navigation survives longer than headless automation, which is easier to fingerprint. Surviving longer is not the same as being safe. Any product built on this footing sits one platform policy change away from a bad week.

That risk is also the moat. A boring operational niche is unattractive to exactly the people who could otherwise clone the product in a weekend, and the last mile of dirty work, the part made of platform quirks and retry logic and knowing which click pattern gets flagged, does not fall out of a general-purpose AI wrapper. Tools that solve glamorous problems get competitors, and tools that solve tedious ones get customers, which is the whole reason a 30-line share bot outlived a thousand better-designed products launched the same month.

The last guardrail is time.

Validating an MVP inside a two-week window is not a rule about speed for its own sake, it is a cap on how much can be lost to an assumption nobody checked. Jordan's first version was 30 lines. Had nobody on those 3 sub-boards cared, the total cost of finding that out would have been one evening and one Reddit post.

## Can You Copy This? Replicating the Unsexy Micro-SaaS Model

Start with your own routines. The candidates are chores you or someone in your house performs on a schedule, on a platform other people also use, where the tedium comes from repetition rather than from difficulty.

The prerequisites are narrow. Commit to a tight niche, refuse to generalize the software before anyone has paid for the specific version, and take the first users from communities where the chore is already being complained about. 200 users from a forum you understand beat a launch on a channel you bought.

Skip this approach if you cannot script, or if you are unwilling to answer support messages by hand through the cold start. Both are load-bearing. Neither is optional in the version of this story that actually worked.

*Also readable on [Telegraph](https://telegra.ph/How-to-Build-a-Micro-SaaS-Without-Spending-a-Dime-on-Ads-08-19).*


---

**Read next**

- [The Cost-Effective Guide to Using Open Code Review for AI Programming Tools](the-cost-effective-guide-to-using-open-code-review-for-ai.md)
- [58 Million Plays Started With One Account, Not Four](58-million-plays-started-with-one-account-not-four.md)
- [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md)

[All 43 write-ups](../README.md)

The 3 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 393 more, as JSON and CSV.

Topics: [Automation Systems](../topics/automation-systems.md) · [SaaS Business](../topics/saas-business.md) · [Micro SaaS](../topics/micro-saas.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** five of fifteen articles carrying the traffic is one writer's hit rate on one keyword. Which channel brought you the users who were still there a month later? Reply with the channel name. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/27).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fhow-to-build-a-micro-saas-without-spending-a-dime-on-ads.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fhow-to-build-a-micro-saas-without-spending-a-dime-on-ads.md&title=%5Bcorrection%5D+How+to+Build+a+Micro-SaaS+Without+Spending+a+Dime+on+Ads) — that form knows
which write-up you came from too; corrections and counter-data are the point.
