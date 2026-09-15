# How to Turn the Workflows You Won't Document Into Agent Skills

![How to Turn the Workflows You Won't Document Into Agent Skills](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/how-to-turn-the-workflows-you-won-t-document-into-agent.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/71) — that copy has a reply box under it, and this one does not.*

This is for the solo developer who repeats the same chores every week and knows exactly how to do them, but has never written instructions for any of them. It is not for you if most of your work is one-off creative calls, because there is nothing stable enough to hand over. Record & Replay approaches exist for exactly this gap: the flows a person or a small team can do but won't write up as a manual.

When this works, the payoff is big. A one-person WeChat publication went from 115–215 minutes of manual work per article to about 11 minutes of machine time plus 10–20 minutes of human input and final review. A better prompt doesn't get you there. Small loops that repeat and can be checked automatically are what turn an agent demo into something you rely on.

## Find the Chores That Eat Your Week

In that WeChat publication, 70% of the solo workflow was repetitive: organizing source material, checking drafts for AI-sounding prose, making covers, converting to HTML layout and publishing. None of those is hard. Together they take up most of the day.

Start by making that list for your own week. Skip categories like "marketing." List the specific chores that keep coming back in roughly the same shape.

Next, break each chore into steps small enough to verify. The clearest example I know comes from a rider recruitment operation that built a helper tool with Codex. They first split recruiters' daily work into concrete operations. Then they built one verifiable closed loop at a time. The tool has been through **28 iterations**, and repetitive work on public recruiting platforms got 60% more efficient.

Twenty-eight is the number I'd pay attention to. That wasn't one big automation project. It was one small loop after another, each shipped, checked and extended. Loop Engineering advice follows the same pattern: start with small, recurring tasks whose output can be accepted automatically.

The failure mode here is drawing the boundary in the wrong place. If you miss a step, or hide a judgment call inside what looks like a mechanical chore, the automation ends up incomplete. You won't notice until it produces something wrong.

I think this is the quietest failure in the whole process, because nothing crashes.

Skip this step for tasks that are mostly creative, or whose steps change every time. A useful test: if you can't state the completion condition, an agent can't work toward one either.

## Record the Workflow Instead of Writing the Manual

Most people stall here, because writing documentation is the chore they wanted to avoid in the first place. Recording lets you skip the write-up.

Be honest about how narrow the fit is. The best candidates are **repetitive, stable, shaped by your personal preferences, and awkward to explain in words**. A button you click once is not the use case. What you capture matters more than which tool you use. Record the inputs, the outputs and every point where you made a decision. Those decisions are the "personal preference" part, and they're the reason the flow is worth recording at all.

The failure mode is a recording that looks complete but isn't, because the agent only sees part of what you saw. A workflow built on `wechat-cli` for post-publication reviews ran into this. The AI couldn't read images or any data not yet synced from WeChat's servers; it only had the local cache. About 40% of review tasks still needed manual filling in, which added about 15 minutes of extra work.

If your flow depends on screenshots, or on data that lives in someone else's system, you must first check what the agent can actually read before you trust a replay, because a recording of your screen is not the same as the agent's access.

Be careful about recording flows that touch credentials, customer data or anything confidential. Think about where that recording will end up and which agent will replay it later.

## Write a Skill Description the Model Won't Cut Short

If I had to bet on which step breaks first, it's this one.

Once you have a recording, look for the parts that repeat: steps that take the same kind of input and produce the same kind of output. Each one is a candidate skill.

A skill succeeds or fails on its description. OpenAI has said explicitly that when there are too many Skills, Codex shortens their descriptions to fit them into context. So a long description, or one whose trigger range covers half your work, does more than waste tokens. It gets trimmed, and the model then picks a skill based on whatever is left.

The same guidance recommends two related habits.

A recording pushes you toward the opposite, which is pasting in every click. Don't. The recording is raw material. The skill is the goal plus the conditions for done.

Also keep what the skill knows separate from how it works; one builder of content Skills puts it this way: the knowledge base is the ammunition and the Skill is the method for using it; Without the material, even a good Skill writes generic content that only looks fine.

The failure mode is getting the size wrong. A skill that swallows three chores gets a sprawling description, and one split too finely never triggers.

If the recordings don't agree with each other and no pattern holds across runs, don't force a skill out of them. Go back to the first step, because the boundary is probably still wrong.

## Pick an Agent Base Small Enough to Inspect

Where the skill runs matters as much as how it's written. Pi, an open-source agent base, sits at the minimal end. By default it gives the model four tools: `read`, `write`, `edit` and `bash`. Its original system prompt and tool descriptions add up to fewer than 1,000 tokens.

I like that for this job. With a base that small, your skill descriptions are most of what the model sees. When a replay goes wrong, there are only four tools to suspect.

At the other end, Agency Agents activates multi-role collaboration with a one-line install. The traditional route is writing and debugging four separate prompts yourself. Prebuilt packs are a third route. Claude Skills offers 355 skill packs across 18 domains for 13 AI coding tools, and they assume you have basic domain knowledge, quality varies, so the recommendation is to scan a pack with skill-security-auditor before installing it.

The failure mode I'd worry about most is permissions, not compatibility. Pi has no built-in sandbox. It inherits your user's files, processes, network access and credentials. The official advice is to run it in a container, VM, microVM or policy sandbox, and to mount only the directories the task needs. That matters most for unfamiliar code or unattended runs.

Put that next to the previous step: a recorded workflow, replayed unattended, by an agent holding your credentials, and if you're doing that, a cheap guard is a hook which scans for API keys before every Git commit.

If a platform can't run the skill you need, don't bend the skill to fit the platform. Switch platforms.

## Keep Correcting It After the First Good Run

A skill that worked once isn't finished. One write-up on building a stable AI Agent "employee" describes the cycle. The agent does real work, a human corrects it, the correction becomes a written rule, and then everything is verified again, with the goal being that the agent can start a fresh conversation and still do the job, which is an important aspect in building a stable AI Agent "employee" as described in the cycle. A multi-account automation SOP follows a similar order: let AI scout the path, check state, log failures, test in batches, and only then script the execution.

/loop` runs scheduled tasks, `/hook` runs on events and `/goal` works toward a stated objective, and in one setup, which is indicated by the annotation, a job runs every night at 10pm across 40 AI podcasts and YouTube channels, after which the day's podcast articles are waiting in Feishu the next morning. Another hook scans drafts for blacklisted words and automatically rewrites the paragraphs that contain them. Hooks like that also work as monitoring, because the check runs every time instead of whenever you remember.

When the agent gets something wrong, the fix often belongs in documentation, not the prompt. Common causes are unclear requirements, inconsistent interface standards, or a project constraint nobody wrote down. One developer's answer was to maintain requirements, architecture, API, testing and progress docs, so the next agent doesn't repeat the same mistake.

Updating a skill description is the same move on a smaller scale.

The failure mode of not watching is often cost, not just wrong output. In one case, GPT-6 Astra running a small tool directly in Codex used up a 5-hour quota in **2 minutes 41 seconds**. If you aren't looking, the first sign of trouble is an empty quota.

Don't make big configuration changes to a working skill without re-running the checks that proved it worked. Otherwise you've traded a known workflow for an unknown one.

---

**5 alternative titles**

1. **The 70% You Keep Redoing: Turning Undocumented Chores Into Agent Skills**
 Subtitle: Record it, extract it, and watch the step that fails without crashing
2. **Don't Write the Manual. Record It.**
 Subtitle: Why the workflows you won't document make the best agent skills, and where that goes wrong
3. **Why Does Your Agent Keep Picking the Wrong Skill?**
 Subtitle: Long descriptions get trimmed, and the model chooses based on what's left
4. **From 215 Minutes to About 30: What Reusable Agent Skills Actually Take**
 Subtitle: Five steps, each with its own failure mode, for developers working alone
5. **28 Iterations, One Small Loop at a Time**
 Subtitle: How repetitive work becomes an agent skill, and why a single big project doesn't

AI Agents · Indie Hackers · Automation · Developer Productivity · Workflow · Codex · Solopreneur

*Also readable on [Telegraph](https://telegra.ph/How-to-Turn-the-Workflows-You-Wont-Document-Into-Agent-Skills-09-14).*


---

**Read next**

- [The Cost-Effective Guide to Using Open Code Review for AI Programming Tools](the-cost-effective-guide-to-using-open-code-review-for-ai.md)
- [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md)
- [Best Practices for AI Agent Skill Management](best-practices-for-ai-agent-skill-management.md)

[All 59 write-ups](../README.md)

The 12 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 524 more, as JSON and CSV.

Topics: [Automation Systems](../topics/automation-systems.md) · [AI Features](../topics/ai-features.md) · [Cost Savings](../topics/cost-savings.md) · [Code Review](../topics/code-review.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** How many iterations do you think it would take for you to automate one of your repetitive work - related chores? Reply with a single number in the discussion thread. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/71).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fhow-to-turn-the-workflows-you-won-t-document-into-agent.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fhow-to-turn-the-workflows-you-won-t-document-into-agent.md&title=%5Bcorrection%5D+How+to+Turn+the+Workflows+You+Won%27t+Document+Into+Agent+Skills) — that form knows
which write-up you came from too; corrections and counter-data are the point.
