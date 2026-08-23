# Klarna Replaced 700 Support Agents With AI. Then It Started Hiring Again.

![Klarna Replaced 700 Support Agents With AI. Then It Started Hiring Again.](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/klarna-replaced-700-support-agents-with-ai-then-it-started.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

In early 2024 the European payments company Klarna put an AI customer-service assistant in place of roughly 700 human agents and said the move was worth about $40 million a year in additional profit. A little over a year later the same CEO said publicly that they had gone too far, and the company started hiring people back. I think that pair of announcements is the most useful data point available on agent deployment right now, more useful than any benchmark, because both halves came from the same executive with the same incentives, and the second half cost him something to say.

## What the Reversal Actually Tells You

The lesson people draw from Klarna is usually "AI can't do support," which I'd argue is the wrong reading.

The reversal was not a capability failure. The assistant handled the volume; the reported savings were real enough to announce publicly. What degraded was service quality, and service quality is the thing an efficiency metric is structurally incapable of showing you. Tickets closed went up. Cost per ticket went down. Both numbers looked excellent while the experience underneath them got worse, and by the time that showed up anywhere a person could see it, 700 jobs had already been cut and the knowledge attached to them had walked out the door.

So the failure was in the measurement, not the model.

This is why I have come to distrust "efficiency" as the headline claim on any AI project. The framing that holds up better asks harder questions: whose efficiency improved, where did the saved time go, did rework fall, did conversion rise, did service cost drop, did the user experience get better. Resolution rate, delivery cycle time, rework volume, service cost. Those are verifiable, and honestly, an AI project that cannot name which of them it moves is probably not embedded in a real business process at all.

## Four Steps, Not One Jump

There is a framing I find genuinely useful here, borrowed from loop engineering, that treats delegation as a staircase with 4 steps rather than a switch.

At the bottom the interaction is turn-based: a person asks, the agent answers, the person decides what to do with the answer. At the top it is pipeline-style, where the agent runs a bounded process end to end and a human inspects the output rather than each step. The steps in between are where you find out what your process actually requires, and skipping them is what "going AI-native" usually means in practice. Chasing that jump produces exactly the pattern Klarna reported: efficiency metrics inflate while service quality quietly falls, because nobody spent time on the middle steps where you would have noticed.

The advice that follows sounds backwards and I think it is right. The fastest way to get AI working is to de-AI first, running the process manually until you have ground the rough edges off it and can say precisely what "done well" means, and only then automating. You cannot write acceptance criteria for a process you have never run by hand. An agent without acceptance criteria does not stop when it is uncertain; it produces something confident and wrong, which in a support queue means a customer who leaves.

De-AI first. Automate second.

## The Boundary Is About Signal, Not Intelligence

A recruiting team that decomposed a job into observable, scoreable dimensions went from screening 100 résumés a day to handling dozens of candidate conversations a day, which is a real gain from handing the model a rubric. They kept the interview human, and the reason they gave is the cleanest statement of the boundary I have read anywhere: tone, pauses and hesitation are signals the AI never receives.

That is not a claim about reasoning ability. It is a claim about input. The agent is not worse at judging hesitation; it simply has no hesitation to judge, and no amount of model improvement changes what never reached the context window. That same team also caught the model amplifying a candidate's story past what the record supported, and fixed it by auditing the claims themselves.

Support has the same shape. Order status, refund eligibility, policy lookup: all of it arrives as text and resolves against a rule, and an agent handles it well. A customer escalating because this is the third time they have written in is transmitting most of their meaning in ways your ticket schema does not capture. Route the first category to the machine and the second to a person, and I suspect a large part of the Klarna problem disappears.

## Write the Job Description Before You Build the Agent

An agent, in the definition I find most workable, is an execution unit given 4 things: a goal, a working boundary, tools, and acceptance criteria. A Skill is its operating manual, collecting the business process, the operating rules, the judgment boundaries, the tools and the acceptance standard, including what to check before starting and in what order to proceed.

Notice that acceptance criteria appear in both, and notice how rarely anyone writes them.

The 8-step method for making an agent stick is basically a loop around that gap: real execution, human correction, rule distillation, re-verification. You run it, you fix what it got wrong, you write the fix down as a rule, then you verify the rule survives in a fresh session. Maybe that last step sounds pedantic. Skipping it is how a team ends up with an agent that works only inside the conversation where it was tuned.

At company scale the minimum unit should be a real high-frequency, low-risk, automatable scenario rather than a job title, because a role-shaped SOP generalizes into a hollow tool shell. Let staff run personal agents first so genuine usage records accumulate, and build the organizational layer from that evidence afterward. When you connect real systems, the engineering is unglamorous and non-optional: data trustworthiness, real-time access, permissions, risk control.

## Where Agents Clearly Do Pay Off

None of this is an argument against deployment, and the counterexamples are specific.

Feishu Shennuo's Marvy 2.0 puts 5 agents — market insight, media strategy, creative, delivery and analytics — into a single AgentOS, and a Chinese consumer-electronics brand entering the Nigerian market reported overall optimization efficiency up 74% with manual hours down 89%. Agency Agents ships 232 structured expert-persona files covering identity, workflow, delivery standards and success metrics, reports output quality gains above 30%, and works across 14 mainstream AI tools; the practical difference is that a setup which used to mean hand-tuning 4 separate prompts now installs with 1 command.

What those cases share is a bounded scope and a check at the end. What the Klarna rollout lacked was the check.

The cheap version of the same discipline is available to a single developer. WorkBuddy paired with BrowserAct produces a competitor pricing table in about 5 minutes and a product-opportunity report in about 7, and a free WorkBuddy account carries 100 credits a day against roughly 10 credits per complex task, so the first 10 experiments cost attention rather than money. BrowserAct drives your real local Chrome instead of a headless browser, which matters because the failure it avoids is the one that kills scraped data quietly rather than loudly. I would test any of that against a week of real work before trusting the numbers, but the scope is bounded and the output is checkable, which are the same 2 properties the enterprise cases had.

One more piece of evidence that operators underweight the fragility of what they build on: a developer's Stripe account was frozen for a dispute rate above 1%, and 1,500-plus paying subscriptions stopped with it. The product worked perfectly. The business stopped anyway, and the fix was spreading collection across channels and watching the metric that predicts enforcement rather than the ones that flatter you.

Klarna's $40 million was probably accurate on the day it was published. The question I would ask before copying anything about that deployment is which number would have gone red first if quality had started slipping in month two, and whether anyone was watching it.

*Also readable on [Telegraph](https://telegra.ph/Klarna-Replaced-700-Support-Agents-With-AI-Then-It-Started-Hiring-Again-08-23).*


---

**Read next**

- [The Klarna Lesson: Why AI Implementation Needs a Staircase, Not a Leap](the-klarna-lesson-why-ai-implementation-needs-a-staircase.md)
- [AI Programming Tool Selection Strategy: From Rapid Prototyping to Long-term Collaboration](ai-programming-tool-selection-strategy-from-rapid.md)
- [From AI Demo to Product: Loop Engineering for Indie Devs](from-ai-demo-to-product-loop-engineering-for-indie-devs.md)

[All 43 write-ups](../README.md)

The 7 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 389 more, as JSON and CSV.

Topics: [Automation Systems](../topics/automation-systems.md) · [AI Implementation](../topics/ai-implementation.md) · [Enterprise Automation](../topics/enterprise-automation.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.
**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fklarna-replaced-700-support-agents-with-ai-then-it-started.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fklarna-replaced-700-support-agents-with-ai-then-it-started.md&title=%5Bcorrection%5D+Klarna+Replaced+700+Support+Agents+With+AI.+Then+It+Started+Hiring+Again.) — that form knows
which write-up you came from too; corrections and counter-data are the point.
