# Claude Code Can Model a Flange but Not a Freeform Surface: A Six-Step Handoff Checklist for Non-Code Agent Output

![Claude Code Can Model a Flange but Not a Freeform Surface: A Six-Step Handoff Checklist for Non-Code Agent Output](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/claude-code-can-model-a-flange-but-not-a-freeform-surface-a.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/72) — that copy has a reply box under it, and this one does not.*

If you are using agents like Claude Code or GPT-5.6 Sol to generate CAD parts, 3D web scenes, or application UIs, you already know the demo phase is over. The current generation of models can produce rule-based CAD parts—like holes, ribs, and flanges—and export a STEP file with a browser preview in minutes. However, the moment you ask for a freeform surface or a complex scene, the output often becomes unstable. Relying on these tools without a handoff process is how you end up with production errors. This checklist, based on developer field tests from July 2026, maps out exactly where the agent stops and where you must take over.

## The goal: a handoff line you can defend

Shipping agent output depends less on the initial demo and more on how you manage the gap between AI generation and real deployment. The hardest part of an AI product is not building the demo, but deciding which tasks go to the agent and which ones require human confirmation.

Instead of trying to automate everything, treat human review as a measurable budget line. In one agent-based writing workflow, manual work dropped from a range of 115–215 minutes down to 11 minutes of machine run time, plus 10–20 minutes of human review. This shift reduced the total time required for content production. The final quality check remains a human responsibility.

To bridge this gap effectively, you must define the boundaries of your agent’s capabilities. For instance, Alibaba’s Open Code Review tool outperforms general-purpose models. In benchmarks across 200 real pull requests and 50 open-source repositories, this tool achieved higher accuracy and F1 scores while consuming only about 1/9 of the tokens compared to general agents like Claude Code. By integrating such domain-specific agents, you can lower API costs and focus human oversight on critical decisions rather than routine verification.

you should implement structural safeguards to prevent the agent from cutting corners Advanced frameworks like Agent Skills incorporate anti-rationalization tables and parallel review mechanisms. These features force the system to justify its steps across the entire software development lifecycle—from the initial definition to the final shipment By forcing these checks, you reduce the likelihood of the AI skipping necessary steps or delivering output that fails under real-world scrutiny.

## Step 1 — Sort the task by shape before you prompt

Rule-based solids are where CAD agents currently shine. If your task involves standard geometric features like holes, ribs, or flanges, the agent can generate a usable STEP file with a 3D browser preview, effectively cutting your concept-to-model time.

However, freeform or organic shapes are where the handoff line is drawn. These surfaces are often unstable and cannot be used directly for complex designs. Even when the preview looks perfect, the underlying dimensions are frequently incorrect This is the most common point of failure. The agent does not throw an error, and the visual preview looks correct, but the production file is flawed. You must perform a manual dimension check before sending anything to production.

Beyond simple modeling, developers can use specialized CAD plugins to transition from static shapes to parameter-driven design By using natural language to generate parametric CAD source code, you can enable rapid design iterations and version control, which boosts efficiency for mechanical engineering tasks

If your project involves robotics, the workflow extends into simulation and verification. You can use Claude Code’s URDF, SRDF, and SDF skills to generate robot description files and world files However, you should not rely on the agent for the final simulation; instead, integrate these files with third-party toolchains like MoveIt or SendCutSend to conduct rigorous motion planning and physical validation.

## Step 2 — Put a machine check in front of human eyes

Before a person reviews the output, run automated checks. A deterministic evaluation system uses three types of graders: rubric-based and human.

* **Deterministic graders**: Check for hard facts. Did the agent call the correct tool? Does the file exist? You can validate tool-call correctness using JSON Schema.
* **Rubric graders**: Handle structured natural-language output where the quality is subjective.
* **Human graders**: Reserved for high-risk cases.

For application UI, you can use tools like `agent-device` to smoke-test the app. Commands like `agent-device open com.example.app --platform android` can open your app, tap controls using tool-provided references, and perform exploratory tests before a developer ever looks at the screen.

Using such an evaluation system saves human resources and improves the efficiency and accuracy of the review process. For independent developers, this reduces the time and cost of app development. By automating the verification of hard metrics like tool calls and file existence, deterministic graders help developers quickly identify and fix issues. When designing the Coding Agent architecture, developers can adopt a hybrid architecture with a replaceable model call layer. This approach combines local inference and cloud-based planning, which helps avoid the risk of model binding and further optimizes task execution through test feedback loops.

## Step 3 — Price the run before you press go

Complex tasks like generating a 3D scene force a trade-off between quality, delivery time, and compute resources. For example, GPT-5.6 Sol Ultra mode runs four sub-agents in parallel, which can take 2h41m35s to complete a detailed scene like a Manhattan block. While the quality is superior to other models, the high token consumption requires developers to carefully balance cost and efficiency.

Do not rely solely on leaderboard scores. One GPT-5.6 Sol run might cost $1.43, while other models could cost upwards of $9.00 for the same task. Run a small evaluation on your specific task to verify both cost and GPU impact. If the agent generates a page that renders but freezes the user's browser, you have failed the handoff.

That small evaluation doesn't have to be expensive. DeepSeek V4 Flash costs $0.028 per million tokens and is fast. On a tight budget, that price lets you run the same task over and over on a cheap model to see where it falls apart. Then you can decide whether the job really needs a premium multi-agent run.

Some of the bill has nothing to do with which model you pick. It comes from vague instructions. When a requirement is fuzzy, Superpowers ends up running review passes again and again, and every pass burns tokens. Grill-me works the other way. It asks the developer about the requirements one question at a time and finishes confirming them in 37 questions. So the agent starts with a clear goal and doesn't have to work out halfway through what you meant.

## Step 4 — Pick the effort tier on purpose

Agent performance is not a fixed attribute; it changes based on the tier you choose. In many systems, such as Miora, the same prompt will yield different results on Standard, Pro, or Max tiers. For instance, on the Standard tier, Miora might handle simpler tasks with basic outputs, but when you switch to the Pro tier, it can refine details and provide more accurate results for moderately complex assignments. If you were to base your judgment of an agent solely on its Standard-tier performance, you might prematurely dismiss its capabilities for more involved tasks. Conversely, using the top-tier (Max) for a straightforward task is a waste of resources. By intentionally selecting the effort tier, you can optimize costs—using a lower tier for simple jobs to save budget and a higher tier for complex tasks to ensure quality. This approach turns cost into a deliberate choice rather than a default setting. Sol models use internal multi-agent systems to handle tasks efficiently, and choosing the right tier aligns with these efficiency benefits, avoiding underutilization and overspending.

## Step 5 — Chain taste guidance before AI-made UI ships

Without specific design guidance, AI-generated UI tends to drift toward a generic template look. To fix this, you need a skill chain that separates strategy from execution.

* **Layers**: Clarify product decisions.
* **taste-skill**: Set the visual direction.
* **Impeccable**: Perform the final overall review.

Specific, small guidance often beats new tooling. For example, Anthropic’s frontend-design `SKILL.md` (approximately 400 tokens) uses a two-pass method for aesthetic guidance and has been installed over a million times. Aesthetic guidance is frequently worth more than the model's inherent tool innovation.

## Step 6 — Draw the confirm line inside your own product

Finally, design the handoff into your product. You must decide what the agent executes directly, what the user confirms, and what the user sees when an error occurs.

Do not hide the original inputs. Users need to understand what they uploaded, what the AI changed, and what they received. If an AI image team only shows polished outputs, the user cannot form a mental model of the product's capabilities. Show the side-by-side input and result so the user can predict the outcome.

Establish clear task boundaries within your AI product. This involves determining which actions the AI can perform directly and which require user confirmation. Careful consideration should be given to the user experience when errors occur. Setting these boundaries ensures a user-friendly experience.

*Also readable on [Telegraph](https://telegra.ph/Claude-Code-Can-Model-a-Flange-but-Not-a-Freeform-Surface-A-Six-Step-Handoff-Checklist-for-Non-Code-Agent-Output-09-15).*


---

**Read next**

- [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](why-stripping-80-of-system-prompts-actually-improved-claude.md)
- [How to Turn the Workflows You Won't Document Into Agent Skills](how-to-turn-the-workflows-you-won-t-document-into-agent.md)
- [Claude Code and Codex for Office Automation](claude-code-and-codex-for-office-automation.md)

[All 62 write-ups](../README.md)

The 7 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 558 more, as JSON and CSV.

Topics: [Indie Development](../topics/indie-development.md) · [AI Features](../topics/ai-features.md) · [Productivity](../topics/productivity.md) · [Code Review](../topics/code-review.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** In the example of the agent - based writing workflow where manual work dropped, you were given a range for the initial manual work time. Can you reply with the lower limit of that initial manual work time from memory? [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/72).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fclaude-code-can-model-a-flange-but-not-a-freeform-surface-a.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fclaude-code-can-model-a-flange-but-not-a-freeform-surface-a.md&title=%5Bcorrection%5D+Claude+Code+Can+Model+a+Flange+but+Not+a+Freeform+Surface%3A+A+Six-Step+Handoff+Checklist+for+Non-Code+Agent+Output) — that form knows
which write-up you came from too; corrections and counter-data are the point.
