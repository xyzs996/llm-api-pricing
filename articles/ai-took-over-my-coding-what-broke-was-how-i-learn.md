# AI Took Over My Coding. What Broke Was How I Learn.

![AI Took Over My Coding. What Broke Was How I Learn.](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/ai-took-over-my-coding-what-broke-was-how-i-learn.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/45) — that copy has a reply box under it, and this one does not.*

One indie developer writing in Chinese in July 2026 put it about as plainly as anyone has: AI has already replaced all of his coding work, and the systematic knowledge he accumulates keeps shrinking. Those two sentences sat next to each other in the same post, and I think most of the English-language coverage of agent adoption has picked up the first one and dropped the second. The replacement is the announcement. The shrinking is the part that shows up eighteen months later, and by then nobody connects it back to the tooling decision that caused it.

## What Gets Expensive When Code Gets Cheap

Start with the mechanical claim, because it holds up.

Writing code got fast. Reviewing code got fast too, which people mention less often and which matters more, since review was the bottleneck that made writing speed irrelevant on any team above 3 people. What follows from cheap code is not that projects got cheap; it is that the cost moved, and the report I keep coming back to names exactly where it moved to: finding the real problem, defining the business facts, handling the uncertainty in external systems, and being accountable for what happens in production.

Four things. None of them are typing.

That list is worth reading slowly, because every item on it is a judgment call that fails silently. A model given a badly defined problem produces a clean, well-tested, well-documented solution to the wrong thing, and every automated check you have will pass. The same report frames the valuable work as turning frontier capability into systems that are observable, recoverable and verifiable, rather than as writing the code that implements them, and honestly I'd argue that phrasing is the most useful three-word test available for whether an AI project is real. Can you see what it did. Can you undo it. Can you prove it worked.

Most agent demos fail all three and are still impressive to watch.

## The Learning Problem Nobody Priced In

Here is the second sentence again, the one that gets dropped: the systematic knowledge is shrinking, and learning has become fragmented.

I suspect this is the genuine cost of the transition and it is almost invisible on any dashboard. When you write a subsystem yourself, you pay in hours and you receive, as a side effect nobody itemizes, a model of how that subsystem behaves under stress. You know which part is fragile. You know what the error message at 3 a.m. is actually telling you. When an agent writes it, the hours come back to you and the model does not, and you find out you are missing it at exactly the moment you needed it, which is during an incident, in front of people.

The pattern generalizes past code. The same developer describes his social world reorganizing from product discussion toward people in the same overseas-business trade, and describes indie development stopping being purely work and becoming part of ordinary life, with more weight on family and on the quality of his relationships. Read charitably, that is somebody being honest about a trade that mostly went well. Read carefully, it also describes a person whose depth in one craft is being exchanged for breadth across several, and I have no idea whether that trade is good over ten years.

What I would do about it is unglamorous and cheap. Pick a small number of things a year, maybe 2 or 3, that you build by hand on purpose, chosen because you expect to be woken up by them later. Everything else can go to the agent. The point is not craft nostalgia; it is that you cannot supervise a system you have never held.

## An Agent Is Three Layers, and Two of Them Are Yours

The definition I find most workable treats an agent as a working unit with a goal, tools, context and a loop, operating under constraints a human set. Three layers underneath that: the model, the tools, the boundary.

You do not build the model. You do build the other two, and the failure mode in almost every stalled deployment I have looked at is that somebody built the tools and skipped the boundary, then blamed the model. A boundary is not a safety feature bolted on afterward. It is the specification of what "finished" means, and an agent without one does not pause when it is unsure; it produces something confident and ships it into your repository.

There is a structural version of this worth adopting early. Splitting agents by responsibility, so requirements, implementation, error output and conversation history stop piling into one session, matters because a single agent that implements a change and then evaluates its own change has no independent check anywhere in the loop. That is the same reason organizations separate the person who writes the invoice from the person who approves it, and the same reason it keeps getting rediscovered.

Separate the writer from the checker. Everything else is detail.

## The Missing Feedback Loop Is Physical

The gap that gets least attention is that AI coding tools can generate a change and cannot tell whether the change worked on a real device.

Mobile development is where this is most obvious, and the tooling response is instructive. agent-device reads the system accessibility tree and turns it into a structured page snapshot, giving the agent a short-context, explicit-action interface it can use to click, type and verify on the actual device. That is not a model improvement. It is a wiring improvement, closing the loop between the code an agent writes and the observable behavior of the thing it wrote, which is precisely the "observable and verifiable" requirement showing up in physical form.

Notice what falls out of that design. If your UI controls carry no label, no role and no test identifier, the accessibility tree has nothing useful in it, and the agent's snapshot is a blur. The prerequisite for automating your UI testing turns out to be accessibility hygiene you should have had anyway, which is a rare case of two priorities pointing the same direction.

The general lesson transfers to backends and data pipelines without much modification. Before adding an agent, ask what it will read to find out whether it succeeded, and if the honest answer is "the human who reviews the pull request," you have not automated the work; you have moved it and added a translation step.

## The Klarna Line, Briefly

The case everyone cites belongs here for one reason only. Klarna replaced roughly 700 support agents with an AI assistant in early 2024, claimed about $40 million a year, and a bit over a year later the same CEO said they had overshot and started hiring back.

I would not read that as evidence about model capability. I would read it as evidence about measurement, since the efficiency numbers were fine the entire time the service quality was degrading, and nothing in the reporting layer was capable of showing the difference. It is the same failure as an agent with no boundary, run at company scale and with a payroll attached.

## What I Would Actually Change

Three things, ordered by how quickly they pay.

Write the acceptance criterion before the agent, in a form a machine can evaluate, because criteria that only a person can judge quietly reintroduce the person you were trying to free up. Wire the verification loop to something real, whether that is a device snapshot, a staging query or a production metric, and treat any agent whose only feedback is human review as a draft generator rather than an automation. And keep 2 or 3 things a year that you build by hand, chosen deliberately, because the judgment the model cannot supply is judgment you have to keep manufacturing somewhere.

Cheap code did not make engineering cheap. It moved the whole cost into the parts that were always hard to see, and the developers doing well right now are mostly the ones who noticed the move early and started charging for the other four things.

*Also readable on [Telegraph](https://telegra.ph/AI-Took-Over-My-Coding-What-Broke-Was-How-I-Learn-08-23).*


---

**Read next**

- [Sell It Before You Build It: How Indie Devs Validate AI Products](sell-it-before-you-build-it-how-indie-devs-validate-ai.md)
- [Choosing the Right AI Model for Coding: Cost vs. Efficiency](choosing-the-right-ai-model-for-coding-cost-vs-efficiency.md)
- [The Hidden Costs of GPT-5.6 Model Selection: A Developer's Real-World Guide](the-hidden-costs-of-gpt-5-6-model-selection-a-developer-s.md)

[All 54 write-ups](../README.md)

The 1 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 499 more, as JSON and CSV.

Topics: [Indie Development](../topics/indie-development.md) · [AI Implementation](../topics/ai-implementation.md) · [AI Costs](../topics/ai-costs.md) · [Chinese AI](../topics/chinese-ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** reply with, what percentage of your coding work is now done by AI, and what percentage remains human-manual? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/45).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fai-took-over-my-coding-what-broke-was-how-i-learn.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fai-took-over-my-coding-what-broke-was-how-i-learn.md&title=%5Bcorrection%5D+AI+Took+Over+My+Coding.+What+Broke+Was+How+I+Learn.) — that form knows
which write-up you came from too; corrections and counter-data are the point.
