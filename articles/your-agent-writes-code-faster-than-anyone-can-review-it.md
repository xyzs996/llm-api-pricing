# Your Agent Writes Code Faster Than Anyone Can Review It

![Your Agent Writes Code Faster Than Anyone Can Review It](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-agent-writes-code-faster-than-anyone-can-review-it.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

The bottleneck in AI-assisted development moved, and most teams have not moved their tooling to follow it. Coding agents made producing a change dramatically faster; the cost of reviewing that change, running the tests, fixing the lint, writing a pull request description a maintainer will accept, and getting CI green did not fall by anything like the same amount. So the queue backs up one step later than it used to, which feels like progress right up until you notice the pile. I think this is the single most common way an agent rollout ends up net-negative, and nobody announces it, because nobody is measuring the step where it happens.

## The Gate Is the Product Now

There is a tool called no-mistakes built on exactly this observation, and its design is worth reading even if you never install it.

What it does is run a 9-step quality pipeline automatically before a commit goes out, so that "the agent produced a lot" and "what got committed is good" stop being two separate questions. That framing is the useful part. Output volume and merge quality drifted apart the moment generation got cheap, and every workflow that still treats them as one number is quietly accumulating debt that surfaces during the next incident.

Nine steps. Automatic. Before the commit, not after the argument.

The second design decision is that it does not bind to a specific agent. It supports multiple coding tools, which matters more than it sounds like it should, because the gate outlives the agent. You will change models this year. You will probably change harnesses. A verification pipeline coupled to whichever assistant was fashionable in March becomes a migration project in September, and honestly I'd treat tool-agnosticism as a hard requirement for anything you put on the merge path.

## "Human Decides, Agent Works"

The interaction model no-mistakes uses is stated in four words: the human decides, the agent does the work.

That sounds like a slogan and it is actually a specification. It means the agent is never the party that determines whether the change is acceptable; it is the party that produces the change and the evidence, and a person reads the evidence and makes the call. The failure it prevents is the one everybody has hit at least once, where an agent implements something, evaluates its own implementation, declares success, and is wrong in a way that no automated check was positioned to catch.

Splitting agents by responsibility is the same idea one level up. When requirements, implementation, error output and conversation history all pile into a single session, there is no independent check anywhere in the loop, and the context gets so crowded that the model starts losing the constraint you set forty messages ago. Give the implementation to one agent and the acceptance to another, and you get the separation for free.

The person who writes the invoice should not approve it. Same rule.

## The Unglamorous Features Are the Ones That Pay

Two things in no-mistakes look like plumbing and save the most time in practice.

The first is fork routing. If you contribute across repositories you do not own, the push has to go to your fork and the pull request has to open against upstream, and getting that wrong produces a confusing failure at the worst moment. Automating the routing removes a category of mistake that costs nothing intellectually and twenty minutes emotionally. It also ships with protection against losing work, which is the kind of feature you evaluate as unnecessary until the one time it is not.

The second is generated pull request descriptions. A PR that gets bounced for a red CI run or a description that does not meet the project's standard is a full round trip, and on a busy repository a round trip is measured in days rather than minutes. Having the tool produce the description from the actual diff, then verifying CI before the request goes out, changes the expected number of round trips from something above 1 to something near zero.

Neither of those is a model capability. Both are workflow surface, and both are where the hours actually go.

## Verification Needs Evidence, Not Assertions

The weak point in every automated gate I have looked at is the same: the checks confirm that the code compiles and the tests pass, and say nothing about whether the thing works.

Closing that gap needs the pipeline to reach the running system. The agent-device project is a concrete example of what this looks like on mobile, exposing a CLI that Codex, Claude Code and similar agents can call to drive a real device, then collecting the evidence from that run for smoke checks and exploratory testing. The output is not a claim that the change works; it is a record a person can look at.

That distinction is the whole game. An agent reporting "I verified the fix" is worth nothing, because the model has every incentive to believe itself and no mechanism for doubt. An agent attaching a snapshot taken from the device after the change is worth a lot, and the difference in engineering effort between those 2 options is a wiring problem rather than a research problem.

Ask what the gate reads. If the answer is "the agent's own summary," it is not a gate.

## Where This Fits in a Bigger Setup

For anyone running more than one agent, the coordination layer matters as much as the gate.

Session persistence and multi-agent orchestration across Claude Code, Codex and OpenCode through a shared ACP protocol, the way agentOS does it, solves the problem where every tool keeps its own incompatible notion of a conversation and switching costs you the context. Multi-window worktree setups solve the adjacent one, letting several agent windows build parts of the same product in parallel without file conflicts, with a controlling agent breaking the spec into tasks and stating the boundaries and dependencies before anything starts.

Put those together and the shape is clear enough. A controlling agent decomposes, worker agents implement in isolated trees, a verification pipeline gates every merge, and a person reads evidence at the boundary where being wrong gets expensive. Distilling repeated tasks into reusable skill templates is what keeps the whole arrangement from being re-explained every Monday.

I suspect most solo developers can skip about half of that. The gate is the half I would not skip.

## The Honest Limits

A quality pipeline catches what it was told to look for and nothing else, which means the failures that survive are the ones nobody anticipated, and those are exactly the failures that matter.

There is also a broader fragility worth naming once. Everything described here sits on platforms you do not control, and the developer stories where a whole business stopped overnight are almost never about code quality; they are about a policy change, a suspended account, a payment processor's threshold crossed. A gate that guarantees clean merges does not guarantee you keep the distribution channel, and those 2 risks want completely different mitigations.

But within the part you do control, the recommendation is simple enough to act on this week. Put a verification pipeline in front of the merge, make it produce evidence rather than assertions, keep it independent of whichever agent you are currently using, and never let the thing that wrote the code be the thing that signs off on it. Fast generation without that gate is not speed. It is just a larger backlog arriving sooner.

*Also readable on [Telegraph](https://telegra.ph/Your-Agent-Writes-Code-Faster-Than-Anyone-Can-Review-It-08-23).*


---

**Read next**

- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- [Your AI Coding Bill Scales With Your Repo, Not Your Output](your-ai-coding-bill-scales-with-your-repo-not-your-output.md)
- [Debunking the Myth of Overnight Success in Micro-SaaS](debunking-the-myth-of-overnight-success-in-micro-saas.md)

[All 49 write-ups](../README.md)

Topics: [Artificial Intelligence](../topics/artificial-intelligence.md) · [AI](../topics/ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-agent-writes-code-faster-than-anyone-can-review-it.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-agent-writes-code-faster-than-anyone-can-review-it.md&title=%5Bcorrection%5D+Your+Agent+Writes+Code+Faster+Than+Anyone+Can+Review+It) — that form knows
which write-up you came from too; corrections and counter-data are the point.
