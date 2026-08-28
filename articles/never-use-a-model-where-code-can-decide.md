# Never Use a Model Where Code Can Decide

![Never Use a Model Where Code Can Decide](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/never-use-a-model-where-code-can-decide.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/65) — that copy has a reply box under it, and this one does not.*

Writing code got cheap. Checking it did not. That gap is where the CI failures live, and the fix is not a better agent. It is a second program that does not trust the first one.

## The Bottleneck Moved and Nobody Moved With It

AI coding agents raised output speed sharply, while the cost of review, tests and lint stayed exactly where it was.

That is the whole problem in one sentence. Production is up, verification is flat, and the queue forms at the narrow end.

Here is the sharper way to say it. As code gets cheaper, the expensive parts of a project stand out more clearly: finding the real problem, defining what the business actually means by a term, handling external systems that misbehave, and being answerable for what happens in production.

None of those got cheaper. So the honest reading of "AI wrote it in four minutes" is that the four minutes moved out of your day and landed somewhere further downstream, usually on a red pipeline at eleven at night.

## The Rule That Makes Gates Work

One evaluation framework states the priority as a strict order: deterministic scorer first, rubric scorer second, human scorer last. Never use a model where code can decide, use a model only where it must, and reserve humans for calibration.

I have not seen a cleaner statement of the principle anywhere, though I may simply have missed it. It is also the part everybody skips, because asking a model "is this good?" takes one line and writing a real check takes an afternoon.

The same framework spans 5 dimensions (functional correctness, process quality, efficiency and cost, robustness and safety, and alignment with the intended experience), and it has been run in production on TPerf's performance-analysis agent rather than only argued about.

Five is more than most teams check.

Most check 1: did it compile.

## What Code Can Actually Decide

The deterministic half is narrower than it sounds, and knowing its edges is what stops you from over-claiming. It covers 4 kinds of check: whether the specified tool was called and with the right arguments, whether the expected file exists and its contents look the way they should, whether the response contains or conspicuously does not contain a particular string, and whether the number of tool calls and the token spend stayed inside a threshold.

Fast, objective, reproducible.

Those three words are doing real work: a check that gives a different verdict on Tuesday is not a gate, it is a mood. Two out of three does not pass here.

The rubric scorer picks up what is left: the things code cannot judge but you can still describe in a structured way, like answer quality, tone, or how closely a convention was followed.

I would treat every rubric check as a debt rather than a feature. It costs a model call per run, it drifts when the model version changes, and it is the first thing to become quietly wrong without anyone noticing. That last part is what makes it dangerous rather than merely expensive, because a deterministic check that breaks starts failing loudly on the next run, while a rubric check that has drifted keeps returning a number and the number keeps looking fine.

## Separate the Thing That Judges From the Thing That Works

Loop engineering describes the minimum viable automation as 5 parts: a goal, an executor, a verifier, a state log, and a stop condition, with the constraint that the evaluator and the executor must be separate. Karpathy is the reference point the source leans on: loop engineering is what fixes automation that keeps falling over.

The stop condition is the part I would install first. An agent with a verifier and no stop condition does not fail. It loops, which is worse, because a failure is loud and a loop is billable.

The same advice appears one level up, in how you organise the agents themselves: split them by responsibility instead of letting one conversation accumulate the requirements, the error output and the entire history, because a single agent playing several roles has nobody checking it.

It is the code review argument, restated for agents. You would not merge your own PR on a team of four, and there is no reason the rule relaxes when the other engineer is a model, especially when that model has already showed it will summarise its own output as a success while the tests are still red.

There is a prerequisite nobody enjoys. Making a workflow automatable means breaking it down to atomic steps and writing out the input, the output and the judgement rule for each. The implicit reasoning has to become explicit, or the agent skips a rung and drifts.

That is a day of writing before a single check runs, which is exactly why most people buy a tool instead. One definition of going AI-native is precisely the opposite: rewrite the workflow, the review, the quality gate and the measurement system, rather than procuring something.

## What the Shipped Tools Actually Implement

no-mistakes runs a 9-step quality pipeline on every submission, deliberately does not bind to a single coding agent, and takes the stance that the human decides while the agent works.

It also handles the two things that get a PR bounced for reasons unrelated to the code: it routes fork pushes and PRs correctly, protects against data loss, and writes the PR description itself.

Unglamorous.

I suspect it is the highest-yield item in the whole list, because a rejected PR costs you the same round trip whether the code was wrong or the description was, and only one of those two is interesting work.

Agent Skills takes the other route: engineering discipline encoded as 24 structured workflows covering Define through Ship, with a checkpoint at every stage.

The detail I find genuinely clever is the Common Rationalizations table attached to each of the 24: a list of the excuses an agent reaches for when it wants to skip a step, each one answered in advance.

That is a very specific piece of engineering.

Somebody watched a model talk itself out of running the tests often enough to sit down and write the rebuttals, one by one, which nobody arrives at from first principles. It is a scar.

Agency Agents goes wider still, with 232 structured expert persona files, each carrying an identity, a workflow, delivery criteria and success metrics, compatible with 14 mainstream tools, and claiming an output-quality improvement of over 30%.

I do not believe the 30%. Not because it is implausible, but because "output quality" is undefined in the claim, and an undefined metric that improves by a specific percentage is a marketing number. The 232 files I believe.

## Evidence Beats Assertion

The verification loop breaks at the same place on every platform: the agent can write the change but cannot see whether it worked on a real device. One tool closes that by reading the system accessibility tree into a structured page snapshot, then exposing a command line that lets an agent open the app, click, type, swipe and assert — saving screenshots, video, logs and performance traces as it goes. The tool is called agent-device.

Evidence, not a claim of success. I think this is the single distinction that matters. The difference matters because a model reporting on its own work is the least reliable narrator in the pipeline.

OfficeCLI reaches the same instinct through a much smaller decision: every command emits JSON, and the error messages are structured too, so the agent can reason about a failure and adjust instead of guessing at prose.

Structured errors are what turn a retry into a correction, and the gap between those two words is most of the difference between an agent that converges on an answer and one that burns your budget circling it.

## Keep the Surface Small

One counterweight runs against all of this, and it comes from a coding agent built on an open base called Pi with only four tools, namely read, write, edit and bash, whose initial system prompt and tool descriptions together came to under 1,000 tokens.

Four tools, and I doubt most setups need a fifth.

A gate is only free if the thing being gated stays comprehensible, and every workflow you encode is surface area you now maintain. The tools in this piece all point the same way, but they point at different amounts of machinery, and the amount is the decision you actually make.

The discipline that keeps that honest is cold-start acceptance: turn the repeating work into a skill template, then verify from a clean start that the agent finds the right entry point and runs it without being nudged.

If it only works while you are watching, you built a demo.

## What It Costs

A day of decomposition before the first check runs. A model call per rubric check, forever. A stop condition you will get wrong at least once. And the ongoing tax of maintaining every workflow you wrote down.

What you get back is narrow and worth it: the pipeline stops telling you things are fine.

*Also readable on [Telegraph](https://telegra.ph/Never-Use-a-Model-Where-Code-Can-Decide-08-23).*


---

**Read next**

- [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](stop-using-ai-as-a-chatbot-how-to-build-an-indie.md)
- [Your Agent Writes Code Faster Than Anyone Can Review It](your-agent-writes-code-faster-than-anyone-can-review-it.md)
- [Your AI Coding Bill Scales With Your Repo, Not Your Output](your-ai-coding-bill-scales-with-your-repo-not-your-output.md)

[All 54 write-ups](../README.md)

The 3 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 497 more, as JSON and CSV.

Topics: [AI](../topics/ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** does anything in your pipeline right now ask a model to judge something code could have checked instead? Reply with yes or no — and if yes, one word for what it judges: style, naming, docs, tests. "no" is a real answer, and the cleanest one. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/65).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fnever-use-a-model-where-code-can-decide.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fnever-use-a-model-where-code-can-decide.md&title=%5Bcorrection%5D+Never+Use+a+Model+Where+Code+Can+Decide) — that form knows
which write-up you came from too; corrections and counter-data are the point.
