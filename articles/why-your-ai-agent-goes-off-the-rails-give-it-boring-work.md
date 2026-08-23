# Why Your AI Agent Goes Off the Rails: Give It Boring Work First

![Why Your AI Agent Goes Off the Rails: Give It Boring Work First](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology: 300 million tokens on day one, about 200 million on day two, about 100 million on day three. Nothing about the models changed in those 72 hours. What changed was that the requirements and the project rules stopped moving, and once the documents, the division of labor and the project constraints were stable, the wasted back-and-forth went away. I think most stories about agents "going off the rails" are really stories about that day one, repeated indefinitely, by someone who never wrote the rules down.

## Pick a Job That Can Be Checked

The advice that survives contact with real projects is unglamorous. The first task you hand an agent should be high-frequency, repetitive, decomposable into steps, verifiable in its result, and low-risk if it goes wrong.

I read that list as a filter rather than a recommendation, because each of the 5 clauses rules out a category of work people keep trying anyway. High-frequency means you see the failure mode more than once, which is the only way I have ever learned one. Decomposable means there is somewhere to insert a check. Verifiable means the check has an answer. Low-risk means the first wrong answer does not cost you a customer. Strategy work fails all four, which is why I think an agent handed a product roadmap gives you something that reads well and commits you to nothing.

A hiring case makes the boundary visible. By decomposing a role into observable, scoreable dimensions, one team went from screening 100 résumés a day to handling dozens of candidate chats a day; the gain came from handing the model a rubric instead of a job description. The interview stayed human, and the stated reason is worth repeating almost verbatim: tone, pauses and hesitation are signals the AI never receives. That same team caught itself letting the model amplify a candidate's story, and fixed it by re-auditing the claims against the record. So the split is not "AI does the easy part." My reading is narrower: the agent handles what can be scored, and a person handles what can only be sensed.

## Say What You Mean, In Writing

Prompt formulas are the most over-discussed part of this whole field.

The core of a prompt is not a template; it is stating the requirement clearly, and the technique for getting there is reverse questioning, or a short PRD that forces a vague ask to converge before the model starts guessing. One developer building a WeChat mini-program used exactly that, running a SPEC method where the AI asks questions continuously until positioning, boundaries and the MVP are pinned down, instead of discovering mid-build that they had been walking into walls. I'd argue the questioning does the work here, not the prompt. A well-phrased instruction sitting on top of an undefined requirement fails the same way a badly phrased one does, only later and at higher cost.

There is a stronger claim in the same write-up, and to be fair I find it the more useful one: documentation matters more than the prompt. A polished prompt cannot rescue a system with no documents. The failures traced back to unclear requirements, inconsistent interface standards, and project constraints that existed but were never recorded, so the fix was to maintain 5 document types — requirements, architecture, API, tests, progress — rather than to write better instructions. Every new session that starts without them re-learns the project from scratch and re-makes the same mistakes; that is what the 300-million-token day one looks like on an invoice.

The same idea shows up as structured files replacing long chat histories. `AGENTS.md` holds the global rules, `PROGRESS.md` holds this project's facts, and separating the two lets context travel across tools and across sessions instead of living in a Codex conversation you are afraid to close.

Write down the thinking you consider obvious.

In one short-drama production workflow the entire method was making implicit judgment explicit: decompose to atomic steps, define input, output and decision rules for each one, and reproducibility follows. Skipping a step because "anyone would know to do that" is exactly where an agent invents something, and honestly, I suspect this is the single most common source of drift in workflows that look well-specified on paper.

## One Agent Should Not Grade Its Own Homework

The most common architectural mistake I see is letting one agent define a requirement, implement it, and then declare it finished.

That was the honest description a developer gave of their own earlier setup: one agent implemented everything, and when problems appeared they kept patching inside the same conversation. Once the project spanned several stages, that agent was playing multiple roles with no independent check, and requirements, error output and history all piled into one session. Splitting agents by responsibility fixed it. That is org design wearing a technical costume, and I think it works for the same reason org design works.

Isolation helps in a more mundane way. A multi-window worktree setup lets 1 person run several parallel Codex windows against one product, each task advancing in its own git worktree so files do not collide and contexts do not bleed. A controlling agent decomposes the spec and the tasks, marks boundaries and dependencies, and the rhythm is staged deliberately: lay the shared contracts serially first, then parallelize in batches across the lower layers, the features and the UI, then integrate and accept at the end. Going wide before the contracts exist is how a group of agents drifts together.

Version your skills like software. `skill-mcp` treats AI skills as packages with rollback and permission control, which is the difference between a team that can undo a bad change and a team whose output quality quietly degrades because somebody edited a prompt in place 3 weeks ago.

## Build the Habit Before the Platform

Enterprise rollouts get this backwards, and the disagreement between my two sources is itself informative.

One says start with a pilot in a specific role, get the prompt working, then distill it into a reusable Skill, with management defining the goal and owning the review. The other says the minimum unit should not be a role at all but a real, high-frequency, low-risk, automatable scenario, because a role-shaped SOP generalizes into a hollow tool shell. I lean toward the second, though maybe they converge in practice, since a role narrow enough to pilot is usually one scenario wearing a job title.

Both agree on sequencing. Let staff run personal agents first and let real usage records accumulate; build the organizational layer out of that evidence afterward. Deploying an enterprise agent to people who have not yet formed a working habit with one is a documented way to fail. When the data layer does arrive it brings real engineering with it: trustworthiness, real-time access, permissions, risk control.

Your own role shifts too, from executor to configurator. You define how the system handles information rather than handling it yourself, and some people expect that to harden into a job title — an Agent Manager who selects, invokes, evaluates and retires other agents. I'm not sure that title survives contact with an actual org chart, but the function is already real.

## What This Actually Buys You

The concrete wins in my reading are small and repeatable rather than dramatic. Scheduled loops handle work nobody wants: one `/loop` setup runs at 10 p.m. across 40 AI podcasts and YouTube channels, so the summaries are sitting in Feishu by morning. Miora's Skills workflow turns a creative process into an asset, since switching brands means replacing specific rules rather than starting over. OpenWorker hands back an editable, shareable file instead of a wall of text you reassemble by hand. And for anyone who wants the mechanics underneath, the Hello-Agents tutorial argues for building your own framework rather than importing one.

None of that requires the agent to be clever. It requires the task to be bounded, the rules to be written, and someone other than the builder to check the result. Define the goal, the working boundary, the tools and the acceptance criteria, then give it something boring; the part people skip, every time, is the acceptance criteria.

*Also readable on [Telegraph](https://telegra.ph/Why-Your-AI-Agent-Goes-Off-the-Rails-Give-It-Boring-Work-First-08-23).*


---

**Read next**

- [The Hidden Costs of GPT-5.6 Model Selection: A Developer's Real-World Guide](the-hidden-costs-of-gpt-5-6-model-selection-a-developer-s.md)
- [AI Programming Tool Selection Strategy: From Rapid Prototyping to Long-term Collaboration](ai-programming-tool-selection-strategy-from-rapid.md)
- [Best Practices for AI Agent Skill Management](best-practices-for-ai-agent-skill-management.md)

[All 40 write-ups](../README.md)

The 3 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 377 more, as JSON and CSV.

Topics: [AI Implementation](../topics/ai-implementation.md) · [AI Programming](../topics/ai-programming.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fwhy-your-ai-agent-goes-off-the-rails-give-it-boring-work.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fwhy-your-ai-agent-goes-off-the-rails-give-it-boring-work.md&title=%5Bcorrection%5D+Why+Your+AI+Agent+Goes+Off+the+Rails%3A+Give+It+Boring+Work+First) — that form knows
which write-up you came from too; corrections and counter-data are the point.
