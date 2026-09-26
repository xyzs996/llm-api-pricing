# Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.

![Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/77) — that copy has a reply box under it, and this one does not.*

"If your AI keeps writing bad code, you need a better model." In each of the rebuilds below, a new model wouldn't have fixed anything, because the model was reading the wrong thing.

One solo developer ended up with files over 1,000 lines, where UI, state management, API calls, business logic and error handling all lived together. Another builder kept their knowledge base in one messy 321KB document, and the AI kept attaching one product's facts to copy about a different product. A third got pulled off course by same-name files and hidden old tables while reading and writing data through the Feishu CLI.

## Model Choice Matters, and Solo Devs Already Route Around It

The strong version of the claim deserves a fair hearing, because part of it is true. Different tools really are better at different jobs, and experienced solo developers send work to them on purpose.

One developer's split looks like this. Product planning, project structure and anything that needs long context goes to Claude Code, which also does most of the coding. Codex gets well-scoped tasks: wrapping an existing feature, changing one module, work that doesn't reopen product direction. Kimi's model came in later for clear execution tasks. The developer is open about what it costs: someone has to decide by hand which bucket each task goes into, and that someone is them.

The claim also holds for how an agent is built. The open-source agent base Pi ships with four default tools: read, write, edit and bash. Its original system prompt and tool descriptions came to **under 1,000 tokens**. A lean harness can beat a bloated one, and picking the right one is a real decision.

So if you're sending a long architecture discussion to a tool that's better at narrow edits, switching will help. I agree with all of that. Where I disagree is the next step: that when output goes wrong, the model is the first place to look.

Every routing setup above quietly assumes the model is looking at a clean project.

The tooling built around these agents shows where the real worry sits. agent-device gives Codex, Claude Code and Cursor a command-line interface to open an app, read the current screen, tap controls, type, swipe and assert state, then save screenshots, recordings, logs and performance data as evidence. It's meant for smoke checks and exploratory testing after AI has written the code. Routing can't cover that part. Knowing which model wrote the code tells you nothing about whether the app still opens.

## When the Code Itself Is the Wrong Context

That assumption is where the claim falls apart. The developer with the 1,000-line files never wrote a shared project description, so every new AI window started from zero and they had to re-explain the background, the goals and the feature positioning each time. The model was guessing. The model never saw the full picture, so the pages, features and code it produced drifted, slowly, away from the original product framework, and pulling them back cost **dozens of hours of rework**. A stronger model starting from zero is still starting from zero.

A 1,000-line file is a context problem before it's a code-quality problem. Put display, state, requests, business logic and error handling in one file, and a small feature change means reading a lot of unrelated code, with every edit risking a break in some other module. That cost lands on the model making the change and on you reviewing the diff. Git made it worse. The project never had real version history, so when the developer finally took a close look, they described a tangled tree: features wired into each other, and no way to say what any single change had done, let alone roll one back or compare two approaches. Running several AI windows in parallel on that codebase made overwrites and feature conflicts more likely. I'd argue the missing Git history hurt more than the file length did.

A split stack does the same damage, just across language boundaries. The Claude Code and Codex developer's May version spread pages, APIs and data models across JavaScript, Python and MySQL. With a handful of features, that held. Then login arrived. Payments, permissions and more reading scenarios followed, and every change needed back-and-forth confirmation across languages and projects, so the current version puts pages, server APIs and data access into one TypeScript project built on Next.js, PostgreSQL and Prisma, where each part still keeps its own job. None of that was a model upgrade. It shrank how much surface anyone, human or model, has to keep straight to make one change. I don't blame MySQL here. I'd argue the three-language split was the real cost, and I suspect a stronger model would have hit the same wall, though I could be wrong about how soon.

Parallel windows can work, but only when each one gets its own isolated space. One multi-window workflow gives every Codex task its own worktree, precisely so several windows can build a whole product at once without file conflicts or one task's context bleeding into another's. Shared directories break that. If three agents write into one working directory, the model isn't your bottleneck.

I'd argue isolation matters more than model choice, though I might be wrong.

## When the Data Is the Wrong Context

Code at least throws errors. Bad data doesn't. The output comes back fluent, confident and wrong, and no model upgrade catches it, because the model has no way of knowing the source was wrong.

The builder with the 321KB document didn't reach for a new model; the fix was structure, and **146 legacy entries** were migrated into the main base and reclassified into **5 libraries**: vehicle model profiles, content assets, customer reviews, policy and after-sales, and ops output. Each car model got its own document. The cross-product mix-ups during retrieval stopped.

Structure won.

The Feishu case is worse, because the tool call succeeds and the target is still wrong. Before trusting any read or write through the Feishu CLI, the builder had to verify two things, the authorization and the exact target, because otherwise a same-name file or a hidden stale table could quietly steer the result somewhere nobody meant it to go. The call returns fine. That only proves the call worked, not which table it touched. I don't think a green status line should count as verification for any agent that writes data.

Sometimes the model can't see the data at all, and it doesn't tell you. With `wechat-cli`, the AI could only read the local cache, which meant images and any messages that hadn't yet synced from WeChat's servers simply never reached it. **40% of review tasks** needed manual backfill, costing about **15 extra minutes** each time. The gaps stay silent. The model summarizes whatever is in front of it and never flags what's missing.

I'd argue that silence is the real cost here, more than the 15 minutes.

A mega-Skill hides which input went wrong. One builder wanted a single Skill to do everything for a Xiaohongshu post, and when the output broke, they couldn't tell whether the topic, the body or the keywords were wrong, or whether the AI had simply read the wrong material. That's the trap. The fix was five Skills, one per core problem: topic, writing, keywords, layout and review. Their own framing is worth keeping: the knowledge base is the ammunition and the Skill is how you use it. Without the material, even a good Skill produces generic content that only looks fine. I think the split matters more than the model, though I might be wrong if your task really is one step, because then there is nothing to isolate and five Skills just add handoffs.

If you can't tell which input caused a bad output, a better model just gives you a more convincing version of the same mistake.

## Check the Context Before You Blame the Model

Before you blame the model, check what it was given. One builder stopped polishing prompts and started maintaining requirements, architecture, API, testing and progress docs, so the next agent wouldn't repeat the last one's mistakes. Their token burn went from about **300M on day one** to 200M on day two and 100M on day three, as the requirements and project rules settled and rework dropped. Same models all three days. The prompts barely mattered. I might be wrong about how far this generalizes, but no prompt can rescue a system where nobody wrote down the interface standards or the project's odd constraints.

Here's the checklist, ordered by where things broke above. Run it against your own project before you open a model comparison.

- Give the AI a project doc it reads first. A CLAUDE.md or AGENTS.md defines how the AI should use the materials and outputs in the folder, and Skills cover the step-by-step procedures. This is what the drifting project was missing.
- Keep files small, stay on one stack, and use version control. That means no 1,000-line files, real Git history, and no JavaScript/Python/MySQL split forcing every change across three layers.
- Sort your data sources and verify the targets. Use five libraries instead of one 321KB blob, confirm auth and the exact target before any CLI write, and know which data your tool **can't** see.
- Put the AI last, and don't let it grade its own work. One builder runs the data and rules step by step first, then hands the intermediate results to the LLM. The AI only turns them into language users can follow. It doesn't decide what's right. Another split writing from checking with a separate "AI examiner" scorecard that has 7 dimensions, red lines and a customer-focus veto. Anything scoring 70 or below
- Keep the business logic in your own head. One builder hit an unclear "corner-wrap" calculation, checked it by hand against a tutorial, then revised the prototype to mark the calculation steps and cut positions explicitly. If you can't explain the rule, you can't tell whether the AI got it wrong.

Next time your AI "writes bad code," check the context it had before you open another model comparison, because in every case above the model did what its inputs told it to do. The inputs were wrong. I'd argue that's good news. You control the inputs; you don't control the model.

---

**Alternative titles**

1. 1,000-Line Files, a 321KB Knowledge Base, and Zero Model Problems: *Three AI failures that a model upgrade wouldn't have touched*
2. Stop Upgrading Your Model: *Your agent is only as right as what it reads*
3. Why Does Your AI Keep Editing the Wrong File? *A context checklist ordered by where things actually broke*
4. Token Burn Dropped from 300M to 100M Without Switching Models: *What changed was the docs, not the AI*
5. The Tool Call Succeeded. The Table Was Wrong. *How same-name files and stale data quietly steer AI agents* I don't buy Zero Model Problems.

AI Coding, Indie Hackers, Software Development, AI Agents, Claude Code, Developer Productivity, Solo Founder

*Also readable on [Telegraph](https://telegra.ph/Your-AI-Didnt-Misread-Your-Code-by-Accident-You-Handed-It-the-Wrong-Context-09-25).*


---

**Read next**

- [The Real Pitfalls of AI Agent Development: From Code Generation to Functional Verification](the-real-pitfalls-of-ai-agent-development-from-code.md)
- [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](stop-doing-manual-devops-how-i-use-loop-and-hook-to.md)
- [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md)

[All 67 write-ups](../README.md)

The 3 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 619 more, as JSON and CSV.

Topics: [AI Agents](../topics/ai-agents.md) · [Software Development](../topics/software-development.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** how long the biggest single file in your own AI-written project has grown. Reply with one number, its rough line count from memory, and say whether you've ever split it. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/77).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-ai-didn-t-misread-your-code-by-accident-you-handed-it.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-ai-didn-t-misread-your-code-by-accident-you-handed-it.md&title=%5Bcorrection%5D+Your+AI+Didn%27t+Misread+Your+Code+by+Accident.+You+Handed+It+the+Wrong+Context.) — that form knows
which write-up you came from too; corrections and counter-data are the point.
