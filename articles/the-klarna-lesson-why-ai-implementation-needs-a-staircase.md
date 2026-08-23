# The Klarna Lesson: Why AI Implementation Needs a Staircase, Not a Leap

![The Klarna Lesson: Why AI Implementation Needs a Staircase, Not a Leap](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/the-klarna-lesson-why-ai-implementation-needs-a-staircase.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/35) — that copy has a reply box under it, and this one does not.*

Klarna's AI customer service experiment, which replaced 700 human agents, initially saved $40 million in a year, but the quality of service suffered so badly that they had to rehire humans, leading the CEO to admit they "went too far" with automation after 12 months. This isn't an anti-AI story—it's a cautionary tale about delegation.

## The Four-Level Staircase for Human-to-AI Delegation

Enterprise AI adoption should follow a structured progression, not an all-or-nothing approach. The "four-level staircase" provides a framework for gradual delegation:

1. **Level 1 — Decision support**: Humans maintain full control, using AI as a decision support tool. This is where most enterprises should start—testing AI responses while keeping humans in the loop.

2. **Level 2 — Supervised automation**: Repetitive tasks get automated, but humans oversee the process. At this stage, you're building confidence in AI's capabilities while maintaining quality control.

3. **Level 3 — Pipeline automation**: AI handles complete workflows, with humans only intervening for exceptions. This is where efficiency gains appear, but this requires monitoring systems.

4. **Level 4 — Full autonomy**: Humans only handle exception cases. This is the end goal, but rushing here without proper foundations leads to Klarna-style failures.

The danger comes when companies chase "AI-native" one-step implementation. They focus on cost reduction metrics (like Klarna's claimed cost savings) while ignoring customer satisfaction. Quality degradation typically appears 6-12 months after full automation—long after the press releases have been sent.

Klarna's own timeline maps onto this staircase cleanly. It went from human agents to Level 4 without stopping anywhere in between, and the bill arrived twelve months later. The staircase isn't caution for its own sake — each level exists to answer one question before you're allowed to skip past it: does the output hold up while a human is still checking it? Klarna never had an answer, because there was never a stage where anyone was checking.

Each level looks different depending on what you're automating.

At **Level 1**, a manufacturing company might use AI to analyze sensor data from machinery, flagging potential issues for human maintenance teams to investigate, while human expertise is indispensable for diagnosing complex problems and making final decisions, even with AI's useful insights.

**Level 2** automation shines in scenarios like customer service. An AI chatbot can handle common inquiries, like password resets or order status updates, freeing up human agents to tackle more complex issues requiring empathy and nuanced understanding.

**Level 3** pipeline automation is evident in finance, where AI algorithms can process vast amounts of data to detect fraudulent transactions in real-time; while the AI handles the bulk of the work, human analysts intervene only when flags require further investigation.

Achieving **Level 4** full autonomy demands rigorous testing and continuous improvement. Self-driving cars are a prime example, where AI systems must navigate complex and unpredictable environments with no human intervention. Reaching this level requires overcoming major technical challenges and earning public trust.

So how do you know when a level is done with you? The test is boring and it works: run the level long enough that the people checking the output stop finding things. If your Level 2 reviewers are still catching errors every week, Level 3 will ship those same errors with no reviewer attached. The rate at which humans intervene is the only readout that matters here — not throughput, not cost per ticket, not how well the demo went. Klarna had every number except that one.

This also tells you which processes should never leave Level 1. When a mistake is expensive to detect and expensive to reverse — a refund, a medical note, a legal filing — the intervention rate never drops far enough to justify the climb. Staying at Level 1 permanently is not a failure of ambition. It is what the staircase is for.

## The Counterintuitive "De-AI" Approach

The fastest way to implement AI successfully is often to first remove it entirely. This "de-AI" approach involves:

1. **Manual execution first**: Run processes completely manually to define what "good" looks like. At Klarna, this step was skipped—they automated first and discovered quality issues later.

2. **Benchmark creation**: Manual processes reveal edge cases that automated systems might miss. These become your quality benchmarks.

3. **Clear performance metrics**: Before automation, establish what success looks like. Klarna had cost savings metrics but lacked customer satisfaction benchmarks.

Let's take the example of an independent developer working on a new app. Implementing the "de-AI" approach, if they start by completely manually running through the entire user journey, they can identify all the potential issues and pain points. For instance, they may find that a certain feature seems great in theory but causes confusion during manual testing. This kind of edge-case discovery can be used to set up strict quality benchmarks. And by having a manual run-through, they can clearly define what a successful user experience should look like in terms of factors like user engagement, ease of use, and task completion time. When they introduce AI into the app, they can confirm that it improves the experience based on the predefined metrics.

When it comes to enterprise AI implementation, dealing with data complexity is another aspect that ties into the "de-AI" approach. **Before fully automating data processing, it's important to manually review and understand data credibility, real-time needs, and permission settings.** This manual step helps establish clear boundaries for automation. For example, if a company rushes to automate data processing without understanding these factors, it may end up with an AI agent that produces inaccurate or unauthorized results.

## Practical Implementation: The Eight-Step Method

A structured approach transforms one-time AI successes into long-term capabilities:

1. **Real execution with human oversight**: Start with humans doing the work while AI observes
2. **Human error correction and feedback**: Document where humans intervene and why
3. **Rule extraction from successful cases**: Convert human decisions into automation rules
4. **Validation of automated rules**: Test rules against new scenarios
5. **Process documentation**: Create clear workflow documentation
6. **Agent training**: Train AI on documented processes
7. **Gradual reduction of human oversight**: Slowly increase AI autonomy
8. **Continuous monitoring**: Track both efficiency and quality metrics

This method ensures AI agents can handle new conversations without losing context. It creates reusable workflows that keep responsibilities clear, letting agents quickly return to new tasks.

To maximize effectiveness, follow these additional guidelines:
- Begin with high-frequency, low-risk scenarios that clearly show value
- Document every decision point to ensure reproducibility
- Use the eight-step method to gradually increase automation while maintaining quality
- Monitor both efficiency metrics and quality indicators to validate improvements
- Ensure all workflows remain clean and maintainable for future use

## The Cost of Proper Delegation

Proper AI delegation requires upfront investment.

- Mapping the manual process before anything gets automated
- Training and validating the agent against that baseline
- Monitoring systems, which are an ongoing cost rather than a one-off

But the payoff is large:
- A quality baseline that exists before the automation does, so a regression shows up as a number instead of as a customer complaint
- Reduced need for costly rollbacks
- Long-term stability that avoids Klarna's rehiring costs

The Klarna case shows that AI isn't the problem—improper delegation is. By following the staircase approach, using de-AI methods to establish benchmarks, and implementing structured eight-step processes, enterprises can achieve sustainable AI integration without sacrificing quality.

The key insight is that delegation success depends on:
1. Establishing clear boundaries through manual process mapping
2. Validating AI outputs against human benchmarks
3. Implementing continuous monitoring systems that evolve with business needs

These principles apply whether working with AI agents or managing human teams.

*Also readable on [Telegraph](https://telegra.ph/The-Klarna-Lesson-Why-AI-Implementation-Needs-a-Staircase-Not-a-Leap-08-19).*


---

**Read next**

- [Klarna Replaced 700 Support Agents With AI. Then It Started Hiring Again.](klarna-replaced-700-support-agents-with-ai-then-it-started.md)
- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md)

[All 49 write-ups](../README.md)

The 3 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 405 more, as JSON and CSV.

Topics: [Automation Systems](../topics/automation-systems.md) · [Artificial Intelligence](../topics/artificial-intelligence.md) · [Enterprise Automation](../topics/enterprise-automation.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** the four-rung staircase is a framework, and frameworks describe the climb, never the fall. Have you ever gone back down a rung? Yes or no in a reply — the retreat is the part nobody writes up. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/35).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fthe-klarna-lesson-why-ai-implementation-needs-a-staircase.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fthe-klarna-lesson-why-ai-implementation-needs-a-staircase.md&title=%5Bcorrection%5D+The+Klarna+Lesson%3A+Why+AI+Implementation+Needs+a+Staircase%2C+Not+a+Leap) — that form knows
which write-up you came from too; corrections and counter-data are the point.
