# Sell It Before You Build It: How Indie Devs Validate AI Products

![Sell It Before You Build It: How Indie Devs Validate AI Products](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/sell-it-before-you-build-it-how-indie-devs-validate-ai.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/48) — that copy has a reply box under it, and this one does not.*

The most useful number I've come across in indie product write-ups this year is a hundred orders in twenty-four hours, and the thing worth noticing is what produced it: Pieter Levels put up a crude landing page for Photo AI, fulfilled the first requests by hand, and let the orders answer the question that a month of building would only have postponed. I think most of the advice aimed at solo builders gets the sequence backwards — it treats validation as something you do after shipping, when the cheapest version happens before a line of product code exists. What follows is the sequence that keeps showing up in the cases I read, with the numbers attached where numbers exist.

## Validate Willingness to Pay, Not Interest

Interest is free. Payment is information.

The practical test for willingness to pay is not a survey — it's three observable things: whether paid tools already exist in the space, how dense the complaints are in the communities around them, and whether the keywords people search carry commercial intent. All three are visible before you build anything, and all three are about money already moving. A market with paid competitors and loud complaints is a market with budget in it. A market with neither is usually a market where everyone likes the idea and nobody has ever paid for the problem.

The reverse-order version of this is blunter: sell first, then build. A landing page and a pre-order do the same job as six weeks of development, at roughly none of the cost, and the pre-order tells you something a signup never does.

Photo AI is the case people cite because the gap is so wide. A basic page, manual verification of each request, over a hundred orders inside a day — and none of the infrastructure that a normal launch treats as prerequisite. I'd argue the manual fulfillment is the part to copy rather than the landing page, because doing the work by hand for the first customers is what tells you which parts are worth automating and which ones you imagined.

Look for the gap, not the empty ocean.

Hunting for a niche nobody has entered sounds smart and usually finds a niche nobody wants. The better target is a specific, high-frequency pain that existing solutions handle badly — the seam in a market that already works. You inherit the demand and compete on the one thing that annoys people, which is a much shorter path than educating a market from zero, and it gives you an obvious answer to the question of who your first twenty users are.

## Build the Smallest Thing That Can Fail Honestly

Minimalism in an MVP is not an aesthetic preference. It is a way of making failure cheap and fast enough that you can afford several of them, which matters because the first attempt is usually wrong in a way that no amount of planning surfaces in advance.

A review-scraping plugin for Shopify makes the point concretely. Testing it against a real browser rather than a controlled fixture turned up DOM structure changes that would have silently broken collection in production, and the fix was continuous validation of the parser rather than a better initial design. That failure mode is invisible in a mock. It only appears when the thing runs against the live surface it depends on, which is an argument for shipping something narrow and real early instead of something broad and simulated later.

There's a second kind of fragility that testing doesn't catch. One developer's account was suspended and their payment account frozen by a platform policy change — the product worked perfectly and the business stopped anyway. The lesson people draw from it is unglamorous: spread the risk, build a channel to reach your users that the platform doesn't own, and watch the metrics that predict enforcement, like dispute rate, rather than only the ones that flatter you.

Platform dependence is a design decision, not an accident.

Once something works, the cost of building the next one drops, and this is where AI tooling earns its place. Pairing WorkBuddy with BrowserAct produces a competitive pricing table in about 5 minutes and a product opportunity report in about 7, which is the difference between researching a niche and researching twelve. Skill-mcp handles the other half by treating AI skills as versioned software packages with rollback, so a team stops depending on whichever prompt happened to be pasted in most recently. I suspect the versioning matters more than it sounds, because the failure it prevents is the one nobody notices until output quality has already drifted.

## Get the First Twenty Users by Hand

Growth channels get discussed as if the choice were between Product Hunt and paid ads. For a developer tool, the honest early answer is neither: find twenty highly relevant users, serve them specifically, and let concrete results build the trust that a launch-day spike never does. Twenty is a small enough number that you can do it manually and a large enough one that patterns show up.

Content works when it comes before the product, not after. One creator published an MVP and short videos ahead of a mini-program launch and arrived at release day with 200,000+ views and a 1,200-person group of people who already knew what was coming — the launch had an audience because the audience was assembled first, over weeks, in public.

Paid acquisition has a place once you know what converts. A small Meta budget of $30 a day, run against Instagram content, produced qualified leads at $3 to $4 each in one reported test. Honestly, I would treat single-campaign cost figures as a starting hypothesis rather than a benchmark, but the shape of the number tells you the channel is testable at a scale a solo builder can afford, which is the actual question.

There's also a supply of demand signal sitting in public that most people ignore. AI agents can mine comment sections for the emotions, needs and scenarios users describe in their own words, and turn that into marketing material that uses the phrasing customers already reach for. It's the same material a founder would read manually, at a volume no founder reads manually.

## Integration Beats Invention

Two cases in my reading push in the same direction, and it's the opposite of what most product advice implies.

Faceless.video pulled a workflow that was scattered across several tools into one end-to-end AI short-video platform and grew fast on the strength of that consolidation — nothing about the underlying capability was new, and the value was entirely in removing the seams between steps people were already performing. Motion's AI Employees line did the structural equivalent in project management, embedding execution into a mature market that already had budget allocated, and reached tens of millions in annual recurring revenue without needing to create a category. Both of them entered established demand instead of manufacturing it.

OpenWorker's delivery function is the small version of the same idea: the agent decomposes a task, uses the files and applications on your machine, and hands back an editable, shareable file instead of a wall of text you then have to reassemble. The improvement is the last mile, which is exactly the mile most tools skip.

That framing changes what you should measure, too. An AI project that reports "efficiency gains" is reporting a feeling; one that reports resolution rate, delivery cycle time, rework volume or service cost is reporting something a buyer can check. Whose time was saved, where it went, what got measurably better — if the answer isn't embedded in a real business process, the number probably isn't either.

Start as a side project, accept that the first version fails, and iterate. That advice is old and slightly boring, and the cases above suggest it's still the closest thing to a reliable method: get a paying signal before you build, build the smallest thing that can honestly break, and hand-serve the first twenty people who care.

*Also readable on [Telegraph](https://telegra.ph/Sell-It-Before-You-Build-It-How-Indie-Devs-Validate-AI-Products-08-23).*


---

**Read next**

- [From AI Demo to Product: Loop Engineering for Indie Devs](from-ai-demo-to-product-loop-engineering-for-indie-devs.md)
- [Why Your Indie App Needs Short-Form Video Marketing (And How to Get Started)](why-your-indie-app-needs-short-form-video-marketing-and-how.md)
- [AI Agent Loop Engineering: Karpathy's Method for 5x Productivity Gains](ai-agent-loop-engineering-karpathy-s-method-for-5x.md)

[All 53 write-ups](../README.md)

The 4 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 489 more, as JSON and CSV.

Topics: [Indie Development](../topics/indie-development.md) · [Automation Systems](../topics/automation-systems.md) · [AI Costs](../topics/ai-costs.md) · [Productivity](../topics/productivity.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** Can you reply with a number between 1 and 100 to show your agreement with the idea of manual fulfillment for the first customers? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/48).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fsell-it-before-you-build-it-how-indie-devs-validate-ai.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fsell-it-before-you-build-it-how-indie-devs-validate-ai.md&title=%5Bcorrection%5D+Sell+It+Before+You+Build+It%3A+How+Indie+Devs+Validate+AI+Products) — that form knows
which write-up you came from too; corrections and counter-data are the point.
