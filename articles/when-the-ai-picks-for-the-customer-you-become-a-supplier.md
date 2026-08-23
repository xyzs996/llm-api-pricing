# When the AI Picks for the Customer, You Become a Supplier

![When the AI Picks for the Customer, You Become a Supplier](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/when-the-ai-picks-for-the-customer-you-become-a-supplier.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/52) — that copy has a reply box under it, and this one does not.*

WeChat's Xiaowei agent went into closed testing this year, and Qwen's brand agents already have Luckin Coffee and KFC connected to them. Those are the same shift arriving in 2 different shapes, and which shape your business ends up with gets decided by a wiring choice nobody in the room thinks of as strategic. Here is what is at stake in it. When an AI assistant completes a purchase for somebody, that person's identity, their behavior and their intent to buy again settle on the platform side by default, and what reaches the merchant is an isolated order. Not a customer. An order, and the gap between those 2 words is the gap between a business with a future and a contract manufacturer with good margins this quarter.

## The Default Is Disintermediation

Nobody has to intend this for it to happen. It is what the architecture produces if you accept the defaults.

Think about what an ordinary transaction used to deposit with the seller. A profile, an email address, a browsing history, a record of what this person bought last time and what they returned, a loyalty tier, a reason to send them something in March. All of that accumulated as a side effect of the customer walking through your door, and none of it required a strategy. When the assistant becomes the door, the accumulation happens on the assistant's side instead, and you receive a fulfillment instruction.

An order is a transaction. A customer is an asset. Only one of them compounds.

I'd argue this is the most consequential and least discussed part of the current agent wave. The conversation is dominated by whether the models are good enough, which is a question that resolves itself over time, while the structural question of who ends up owning the relationship gets decided by integration decisions that individual engineers make in an afternoon.

## Two Architectures, and They Are Not Equivalent

There are broadly 2 shapes this takes, and the difference between them is not cosmetic.

In the platform-proxy shape, the assistant belongs to the platform, and it selects among merchants and executes on the user's behalf. WeChat's Xiaowei agent, currently in closed testing, is the version of this that a lot of merchants will encounter first. The merchant supplies goods or services; the platform supplies the interface, the identity and the memory.

In the brand-agent shape, the merchant runs an agent that keeps its own membership system, its own offers and its own conversation history. Qwen's brand agent model works this way, and brands including Luckin Coffee and KFC have connected to it while keeping their loyalty programs and personalized promotions intact. Same underlying capability. Completely different ownership of the thing that matters.

The distinction is not about model quality at all. It is about where the customer's identity lives after the transaction closes, and once you frame it that way the correct architectural priority becomes obvious in a way it usually is not while people are arguing about which assistant answers better.

## The Technical Requirement Is One Sentence

What actually defends the relationship is stitching the transaction back into your own membership system.

That is the whole requirement, and it is more specific than it sounds. It means that when an order arrives through an agent, your system resolves it to a member identity you control, records the repurchase data against that identity, and updates the profile you keep. Not a copy of the order. A binding between the transaction and the person, held on your side.

Membership identity. Repurchase data. User profile. Those 3 things are the root, and everything else is branches.

If you do that work, an agent-driven order is a normal order with an unusual origin, and you can still recognize the customer, still price for them, still reach them. If you do not, then the agent has effectively performed the marketing, the selection and the customer relationship, and left you the part that costs money to fulfill. Honestly, the second arrangement can be quite profitable for a while, which is exactly why it is dangerous; the revenue looks fine right up until the platform decides its own house brand should occupy that slot.

## There Is a Window and It Is Open Right Now

The reason to act on this in the next few months rather than later is a policy detail that most people are reading as a reprieve.

WeChat's current stance is read-only, meaning the agent can see but not act. That posture is described as temporary, with brand-agent interfaces plausibly opening later. Which means the present moment is a rehearsal with the consequences turned off, and the thing to do with a rehearsal is to build the part that will be expensive to retrofit.

Concretely, separate the relationship layer in your architecture now, as its own component with its own storage, rather than as a set of fields hanging off whatever order table your current channel happens to write to. When a new channel opens, integrating it becomes a connector rather than a migration. Doing this after three channels are live is the same work performed under deadline, in production, with data already scattered.

I suspect most teams will not do this, for the ordinary reason that nothing is broken yet.

## Discovery Is Changing Shape Too

There is a second-order effect worth planning for, which is what happens to how customers find you at all.

Traffic distribution is shifting from ranking toward AI readability. The user stops scrolling a list of ten options and the assistant picks one service and executes it, which turns a ranking problem into a matching problem. Being third instead of eighth used to cost you some percentage of clicks. Not being selected costs you all of them, and there is no partial credit in a world where the assistant returns one answer.

What that rewards is an explicit, unambiguous statement of what you do. Not marketing language, a capability description precise enough for a machine to match against a request, including the boundaries: what you handle, what you do not, in which areas, under what conditions. The practical sequence people suggest is to first confirm through the default automatic path that the assistant can discover your service at all, then invest in the more deliberate integration path only for the high-value flows where being chosen reliably is worth the engineering.

Compare two descriptions of the same coffee shop to see how large the gap is. "Premium handcrafted beverages and an elevated cafe experience" matches nothing, because it describes a mood. "Order hot or iced coffee for pickup within 15 minutes, 7 a.m. to 8 p.m., at 3 locations in this district, with member pricing applied at checkout" matches a request, and it also happens to tell the assistant that member pricing exists, which is how a brand agent like the one Luckin Coffee and KFC connected to keeps its loyalty economics visible instead of getting flattened into a generic listing. The second description is not better writing. It is machine-readable in a way the first one structurally is not.

Vague positioning used to cost you nothing. That is the change.

## What I Would Do This Quarter

Three things, and none of them require guessing which assistant wins.

Make the relationship layer a first-class component with its own identity resolution, so that any channel writing an order also writes a binding to a member you own. Write the capability statement, plainly enough that a machine can match it, and keep it current, because it is now doing the job that your search ranking used to do. And measure the thing that actually indicates whether you are still a business rather than a supplier, which is the share of repeat purchases you can attribute to a customer you recognize.

That last number is the one I would put on the wall. Revenue can look healthy while it drifts toward zero, and by the time anyone notices, the relationship layer belongs to somebody else and buying it back is not on the menu.

*Also readable on [Telegraph](https://telegra.ph/When-the-AI-Picks-for-the-Customer-You-Become-a-Supplier-08-23).*


---

**Read next**

- [AI Side Hustle: Stop Selling Hours, Start Selling Plans](ai-side-hustle-stop-selling-hours-start-selling-plans.md)
- [Why Pi's 1000-Token Agent Engine Needs a Sandbox Before You Touch It](why-pi-s-1000-token-agent-engine-needs-a-sandbox-before-you.md)
- [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](why-stripping-80-of-system-prompts-actually-improved-claude.md)

[All 50 write-ups](../README.md)

The 1 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 414 more, as JSON and CSV.

Topics: [Indie Development](../topics/indie-development.md) · [Automation](../topics/automation.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** Can you reply with a number between 1 and 10 to indicate how concerned you are about this shift in customer relationships? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/52).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fwhen-the-ai-picks-for-the-customer-you-become-a-supplier.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fwhen-the-ai-picks-for-the-customer-you-become-a-supplier.md&title=%5Bcorrection%5D+When+the+AI+Picks+for+the+Customer%2C+You+Become+a+Supplier) — that form knows
which write-up you came from too; corrections and counter-data are the point.
