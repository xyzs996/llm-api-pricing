# Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation

![Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/stop-using-ai-as-a-chatbot-how-to-build-an-indie.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/63) — that copy has a reply box under it, and this one does not.*

Ninety percent of the people who open an AI tool type a question into it. The ones earning a living from it type a schedule instead. A former Alibaba P8 engineer, laid off and three months into a job hunt that went nowhere, ended up running three AI instances on timers — one watching competitor prices, one producing ad creative, one answering customer mail — and pulled 170,000 yuan a month out of them, somewhere near $24,000. Not one piece of that setup is a chat window. The skill that separates the two groups is no longer asking a good question; it is handing off a task and walking away.

## The Chatbot Trap

Most people never leave the chat box. They ask, they read, they paste the answer somewhere else, and that is the entire loop. The indie developers who get real work out of the same subscription have quietly changed the verb: they describe a job, hand it over, and come back later to inspect what came out. Same model, same monthly bill, completely different relationship.

I would not defend the 90% too hard — nobody audited it, and it reads like a number someone rounded up on stage. The part I do trust is what sits underneath it: the gap is not talent or model access, it is whether anything runs while you are asleep.

Look closer at what that laid-off engineer actually built. Scheduled automation, several agents running at once, Skill packages, MCP connectors, memory: five parts, and the report he came from counted 27 similar cases in which every single earner had used at least three of them. The income figure is the least interesting thing in that story. What matters is that none of his three instances needed him sitting in front of them.

Another operator runs Skills that build three to six websites a day in parallel; in under two weeks, 30 of them were live. The 30 is believable to me precisely because the sites are almost certainly near-identical — parallelism buys you volume of the same shape, not 30 different products, and that distinction is where most people who copy this end up disappointed.

The Agency Agents project keeps 232 structured expert persona files, each one pinning down an identity, a workflow, a delivery standard and a definition of success; the project claims over 30% better output across the 14 AI tools it supports.

I have no idea how they measured that 30%, and I suspect nobody outside the project does either. The 232 is the number I would look at. That is a corpus somebody maintained, not a prompt somebody tweeted.

OpenWorker breaks a job into steps, opens the files and applications on your machine, and hands back something you can edit and send on. The output is the deliverable, not a transcript you still have to transcribe.

I think indie developers using the open-source Agent base Pi for AI programming should note its limitations. Pi’s system prompt and default tools only have four basic functions (read, write, edit, bash) and initial tokens under 1000. This means that for most practical tasks, Pi’s capabilities are quite constrained, and developers will need to extend its functionality through additional tools and integrations to achieve their goals.

Under 1000 tokens of system prompt is not a ceiling, though — it is a starting position, and a deliberate one. A base that small tells you exactly what it does; every capability past read, write, edit and bash is something you added on purpose and can therefore remove when it misbehaves.

harness-anything goes at the same problem from the other end. It is MIT-licensed, it drives Windows software through COM, and it ships command sets for office, academic and design work. COM is an unglamorous choice and that is the point: the integration surface already exists on every Windows machine, so nobody has to wait for a vendor to publish an API.

Every model release drags a spike of searches behind it for the tools around that model. Watching that curve is a cheap way to pick what to build next.

None of it needs a better model.

What these projects share has nothing to do with chat transcripts. It is a manifest: what the tool may touch, what it must produce, when it runs.

## Skills as Workflow Building Blocks

A skill package is just a workflow that stopped being retyped. skill-mcp is the version of this idea I find easiest to argue for, because it treats skills the way we already treat code: versioned, permissioned, and rollback-able when a prompt edit turns out to be a mistake, with five tools exposed for listing skills, inspecting them, reading their files, orchestrating a sequence and sending feedback back in, plus a system-prompt mechanism that pushes the model to go looking for a skill instead of improvising one. The results people report from this are unglamorous and large: a security team that froze its vulnerability-scanning routine into a package watched its bug bounty income triple, and a daily-report routine standardised the same way dropped from 90 minutes to 8.

Codex wraps the same idea in a visual interface: what is installed, what each skill does, how to fire it. Sounds cosmetic. It is not — a skill nobody can find is a skill nobody reuses, and a solo developer has no colleague to ask.

skill-mcp runs in three modes: local standalone, hybrid, distributed. One environment variable moves a skill between them.

Three deployment modes behind one environment variable is the part I would watch closely. Local and distributed fail in different ways, and a switch that makes them look identical while you are writing the skill is exactly the switch that hides the difference until the skill is running on a schedule at three in the morning.

Miora, a design agent, can generate complete brand design solutions, including logos, brand manuals, product designs, 3D models, IP images, app UIs, and TVC videos. It also provides memory functions and workflow preservation and reuse, improving the efficiency and quality of creative work. This creates specialized agents for specific industries or tasks. I think Miora's ability to handle such a wide range of design tasks is impressive, but I'm skeptical about how well it can adapt to highly specialized or niche design requirements.

 By starting with specific positions and running through prompts before sedimenting them as skills, enterprises integrate AI tools into their workflows. Management involvement in defining goals and reviewing responsibilities is important for successful AI implementation. This approach avoids the pitfalls of generalized tool shells and ensures AI tools are tailored to specific, high-frequency scenarios.

The management half of that advice sounds like consultant filler until you notice what it is actually solving: a skill file encodes a delivery standard, and somebody has to own what "delivered" means. Skip that and you get a tool shell that produces output nobody accepts.

Skill packages let developers automate workflows by scripting AI to explore paths, check states, log errors, test batches, and execute scripts—turning repetitive tasks into reusable SOPs. Multi-account management is the case that convinced me: the loop is dull, the state is easy to check, and a failed step leaves a log instead of a mystery. The real power arrives when those SOPs are standardised across a team rather than living in one person's shell history.

Speed is the headline and the wrong metric. What a packaged SOP actually buys is that the same job fails the same way twice, which is the only condition under which you can fix it once.

## Automation with Cron Jobs and Memory

A schedule without memory is a cron job. Memory without a schedule is a very well-informed chat window. Put them together and you get the loop: the Alibaba engineer's three instances each woke on their own timer and each remembered what the last run had done. In the agent tools that have grown one, the scheduling half shows up as a /loop command. The economics arrived quietly underneath all this: once a model costs less per run than the minutes you would have spent, automating a boring job stops being a project and becomes the default.

Memory is the piece I see oversold most often. Persisting context across sessions is not the same as understanding it, and a scheduled job with a long memory and no verification step will happily carry a wrong assumption forward every night for a month.

One developer points /loop at 40 AI podcasts and YouTube channels every night at 10 and wakes up to the whole batch processed into a knowledge base. Memory is what makes the second night cheaper than the first: the run knows which file it stopped at and what it still owes, so nobody has to hold that in their head between sessions.

WorkBuddy and BrowserAct put numbers on the same shift for e-commerce sellers: a competitor pricing table in 5 minutes, a product opportunity report in 7. I would want to see those reports before trusting them. But the sellers running them are not comparing against a better report. They are comparing against no report at all, which is what they had last quarter.

## The Toolchain Advantage

The developers getting the most out of this are not the ones on the newest model. Someone on GPT-4 with a full toolchain around it out-produces someone on GPT-5.6 who only knows how to chat, and the gap is not close. That ordering should be uncomfortable for anyone who spends their week reading benchmark threads.

Look at what the earners actually assembled and the same short list keeps appearing: scheduled runs, several agents working at once, packaged skills, connectors into real software, and memory that survives a restart. Nobody used all five. Almost everybody used three.

Three out of five. That is the entire bar.

It is lower than the phrase "AI automation" makes it sound, and it is cleared by picking one recurring job you already do badly and putting it on a timer this week.

The honest catch is that a workstation demands something a chat box never does: you have to define what finished looks like before you walk away. That is the actual work, and no model release is going to do it for you.

*Also readable on [Telegraph](https://telegra.ph/Stop-Using-AI-as-a-Chatbot-How-to-Build-an-Indie-Workstation-with-Skills-and-Automation-08-23).*


---

**Read next**

- [Never Use a Model Where Code Can Decide](never-use-a-model-where-code-can-decide.md)
- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- [Why Your Indie App Needs Short-Form Video Marketing (And How to Get Started)](why-your-indie-app-needs-short-form-video-marketing-and-how.md)

[All 52 write-ups](../README.md)

The 7 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 422 more, as JSON and CSV.

Topics: [Productivity](../topics/productivity.md) · [AI](../topics/ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** the five parts are a schedule, parallel agents, skill packages, connectors, and memory. How many of them are running for you right now? Reply with one digit, 0 to 5 — zero is the answer I most want to see. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/63).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fstop-using-ai-as-a-chatbot-how-to-build-an-indie.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fstop-using-ai-as-a-chatbot-how-to-build-an-indie.md&title=%5Bcorrection%5D+Stop+Using+AI+as+a+Chatbot%3A+How+to+Build+an+Indie+Workstation+with+Skills+and+Automation) — that form knows
which write-up you came from too; corrections and counter-data are the point.
