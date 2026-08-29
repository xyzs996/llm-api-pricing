# LLM API pricing for coding agents, re-read daily

**English** · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

> 56 models · re-read from OpenRouter every day · no signup · CC BY 4.0

Two things: a price table re-read from OpenRouter's catalog every day, and
54 write-ups on what those bills looked like in production.

## What the agent models cost (56 models)

A coding agent re-reads its context every step, so **95.6% of the tokens
it sends are cache reads**. Repriced at that mix, the list input price every other table sorts by overstates the bill by a
median **6.5×** (3.2×–7.9×). Read **2026-08-29**; the three cheapest *to run*:

| $ / 1M at agent mix | $ cache read | $ in | $ out | Model | Best agents rank |
| --- | --- | --- | --- | --- | --- |
| **$0.0283** | $0.0187 | $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #4 androidnative |
| **$0.0566** | $0.0375 | $0.375 | $1.875 | Gemini 3.6 Flash `batch` | #10 mobileapps |
| **$0.0731** | $0.06 | $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[All 56 models](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Or put your own numbers in.** [The calculator](https://xyzs996.github.io/llm-cost-calculator/) reads this same daily JSON: it resolves [DeepSeek's peak/off-peak clock](deepseek-peak-hours.md) for the moment you ask, applies the long-context price cliff to the request you actually send, and takes your own cache-hit share. One page, nothing to install, no account.

**One number, two answers.** Google and xAI both step to a higher rate at 200,000 prompt tokens — and a prompt of exactly 200,000 bills at the *cheap* rate on Google, the *expensive* rate on xAI. Every table we could find prints one number and stops there. Which side each vendor bills, quoted from the vendor's own page with the date it was read: [same number, opposite answer](prices.md#same-number-opposite-answer).

That 95.6% is **one person's measurement of one coding agent** ([8.04B tokens, 2026-05-16](https://gist.github.com/hungson175/91147b729afdf9fd691342359265731b)), not an industry figure — it is simply the only public measurement we could find. 54 of these rows publish a cached-input price, so the weights ship in the JSON: recompute with your own mix. Cache-*write* prices are not in the catalog, so that 2.7% of tokens is folded into the cache-miss share, which understates cost by roughly 0.7%.

**The table above is a list price. No bill matches it.** What moves
the number is cache hits, retries, and context you pay to send twice —
none of which a catalog can show. One write-up went after that gap:
[where the token bill actually goes](https://github.com/xyzs996/llm-api-pricing/discussions/37). It ends on one question
the table cannot answer, and answering it takes one word:

> **One thing this piece could not settle:** 1.6 billion free tokens a month is an advertised ceiling; a bill is a fact. Roughly what did you pay last month — tens, hundreds, or thousands? Reply with the bracket, no exact figure.

That page has a reply box; this one does not.

## Take the table

```shell
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json
```

56 models, 19 columns per row: list input, output and **cache-read** price per million tokens, the context window and
the long-context step, the vendor, and where the model places in the agent benchmark. Rebuilt every day from
OpenRouter's catalog at paths that do not move.

The CDN serves a branch reference and refreshes about every 12 hours; for today's build without the cache, read [`prices.csv`](https://xyzs996.github.io/llm-api-pricing/prices.csv) off the site. CC BY 4.0 — take it, no attribution ceremony needed
beyond the license.

**Star this repository** to bookmark the table and follow releases.
The data is CC BY: a star changes nothing about what you can do with
it. What a star does change is whether the next person looking for
these numbers finds them — GitHub weighs star count in search results
and in the repositories it suggests alongside this one.

**Read these on the web:** [AI Coding Field Notes](https://xyzs996.github.io/llm-api-pricing/) — the same write-ups with the figures table, the topic pages and the
links between them.

**On the figures.** Every number here traces back to a named source or
a run we did. Numbers we could not trace were cut before publishing,
not rounded or guessed. Each piece says up front that it was drafted
with AI assistance.

## The figures, as data (500 rows)

Every figure published across the 54 write-ups —
prices, percentages, multiples, token counts and durations — pulled into one table. Each row carries
the **full sentence it came from** and a link to the piece, so
you can check it without reading all of them.

One row from each of the 12 most
recent write-ups — quoted verbatim, not summarised:

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$35M` | Respond.io crossed $35M in annual recurring revenue last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to per-customer billing — made the difference between flat growth and explosive scale. | [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md) |
| `$0.81` | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. | [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `$22,000` | The organic channel that produced $22,000 a month is running at roughly half the traffic a million-dollar year would need, and it took three months to get there. | [The $22K-a-Month AI Tool That Never Bought a Single Ad](articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.md) |
| `$24,000` | One watched competitor prices, one produced ad creative, one answered customer mail, and together they pulled 170,000 yuan a month out of them, somewhere near $24,000. | [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](articles/stop-using-ai-as-a-chatbot-how-to-build-an-indie.md) |
| `30%` | Agency Agents goes wider still, with 232 structured expert persona files, each carrying an identity, a workflow, delivery criteria and success metrics, compatible with 14 mainstream tools, and claiming an output-quality improvement of over 30%. | [Never Use a Model Where Code Can Decide](articles/never-use-a-model-where-code-can-decide.md) |
| `20%` | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. | [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md) |
| `$22,000` | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. | [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Claude Code and Codex for Office Automation](articles/claude-code-and-codex-for-office-automation.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |

[All 500 rows](figures.md) — or as data:

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Fields: `value`, `kind` (`price` / `percent` / `multiple` / `tokens` / `duration`), `unit`, `context`, `article`, `published`, `url` (the copy on this site — no reply box), `medium` (published there first, empty if it never was), `thread` (same piece as a GitHub discussion, with a reply box). `published` is the day that
write-up went out, not the day the figure was in force —
prices move, so read each row as of its own date.
Browse it as a table:
[figures.md](figures.md).

Those two go through jsDelivr, which caches `@main` for up to 12
hours — fine for a table that is rebuilt once a day. If you want
it uncached, the origin is
`https://xyzs996.github.io/llm-api-pricing/data/figures.json`.

A number without its sentence is not checkable — `$1.43` could be
per million tokens, per month, or per seat. The sentence is quoted
verbatim, not summarised.

**Citing a row?** `@main` moves — today's row 88 may be somewhere
else tomorrow. Every snapshot is also frozen as a dated release,
and these two always resolve to the newest frozen one:

```
curl -sL https://github.com/xyzs996/llm-api-pricing/releases/latest/download/figures.json
curl -sL https://github.com/xyzs996/llm-api-pricing/releases/latest/download/figures.csv
```

[All snapshots](https://github.com/xyzs996/llm-api-pricing/releases) — one per day the table actually changed.

**Corrections wanted.** If a figure is stale, a tool changed its
pricing, or you ran the same thing and got something else — [open an
issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml). That is
what this repo is for.

**Want a figure that is not here yet?** Say which metric, which
provider, which unit — [in one line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml).
The form has one required field and that is the whole of it.

**Or read one of these first.** Each answers a question people
actually search for, with every figure this repo has on it — the
sentence and the date included:

- [AI agent loop engineering: what does the 5x claim actually measure?](https://github.com/xyzs996/llm-api-pricing/discussions/2) — every figure published about running an agent in a loop instead of re-prompting it — including the one the write-up itself refuses.
- [Which Chinese AI agent tools are actually free for coding, and what do they cost once they are not?](https://github.com/xyzs996/llm-api-pricing/discussions/3) — the per-million input prices behind the free-token grants, each kept with the sentence and the date it was published in.
- [Which AI programming tool should I pick — and does the 70% time-saving figure apply to me?](https://github.com/xyzs996/llm-api-pricing/discussions/4) — why that one widely-quoted time-saving figure holds for one kind of reader and is close to meaningless for the other.
- [Two AI code reviewers score within two points. One costs a sixth as much per run.](https://github.com/xyzs996/llm-api-pricing/discussions/5) — both benchmark scores and both per-run prices side by side, with the vendor self-reports marked as such.
- [What does a coding agent actually cost per month — and which figure on the pricing page is the one that moves it?](https://github.com/xyzs996/llm-api-pricing/discussions/6) — every published per-million price this repo has collected, and why the one that decides the bill is usually not on the page.
- [Klarna saved $4M replacing 700 agents, then rehired. Which number arrived first, and which one would have warned you?](https://github.com/xyzs996/llm-api-pricing/discussions/7) — the savings, the satisfaction drop and the months between them, in the order they were published.
- [What does a one-person software product actually make — and how many months before it made anything?](https://github.com/xyzs996/llm-api-pricing/discussions/8) — the published monthly revenue figures next to the months each one took to get there, including the eighteen-month one.
- [Short video for indie products: 95% organic sounds great until you ask how many hours a week it costs](https://github.com/xyzs996/llm-api-pricing/discussions/9) — the reach figures next to the weekly hour counts behind them, and why an organic share with no denominator is not a result.

**Follow along.** [Atom feed](https://xyzs996.github.io/llm-api-pricing/feed.xml) — new
write-ups land there first.

**Reading this with a model?** [llms.txt](https://xyzs996.github.io/llm-api-pricing/llms.txt)
— the dataset first, then every write-up with one line of what it says.

**By provider.** [Claude](providers/claude.md) (36) · [GPT-5.6](providers/gpt-5-6.md) (19) · [WorkBuddy](providers/workbuddy.md) (13) · [BrowserAct](providers/browseract.md) (12) · [Klarna](providers/klarna.md) (12) · [Gemini](providers/gemini.md) (11) · [Kimi](providers/kimi.md) (9) · [OpenAI](providers/openai.md) (9) · [GLM](providers/glm.md) (8) · [Fable 5](providers/fable-5.md) (7) · [DeepSeek](providers/deepseek.md) (6) · [GPT-5](providers/gpt-5.md) (5) · [ChatGPT](providers/chatgpt.md) (4) — prices where there are prices, and every figure whose sentence names it, with the date.

**By topic.** [Indie Development](topics/indie-development.md) (16) · [Automation Systems](topics/automation-systems.md) (15) · [SaaS Business](topics/saas-business.md) (11) · [AI Implementation](topics/ai-implementation.md) (9) · [Niche Market](topics/niche-market.md) (9) · [AI Costs](topics/ai-costs.md) (8) · [Artificial Intelligence](topics/artificial-intelligence.md) (8) · [Productivity](topics/productivity.md) (8) · [AI](topics/ai.md) (6) · [AI Features](topics/ai-features.md) (6) · [AI Programming](topics/ai-programming.md) (6) · [Cost Savings](topics/cost-savings.md) (6) · [Chinese AI](topics/chinese-ai.md) (5) · [Development Tools](topics/development-tools.md) (5) · [AI Tools](topics/ai-tools.md) (4) · [Revenue Growth](topics/revenue-growth.md) (4) · [Automation](topics/automation.md) (3) · [Code Review](topics/code-review.md) (3) · [Enterprise Automation](topics/enterprise-automation.md) (3) · [Micro SaaS](topics/micro-saas.md) (3) · [Token Optimization](topics/token-optimization.md) (3)

## The write-ups

### [The Cost-Effective Guide to Using Open Code Review for AI Programming Tools](articles/the-cost-effective-guide-to-using-open-code-review-for-ai.md)

Open Code Review is an open-source review tool built for AI-assisted development, and in benchmark tests spanning 200 real pull requests across 50 open-source repositories it scored higher on both…

`Code Review` `Cost Savings` `SaaS Business` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/11) · [telegra.ph](https://telegra.ph/The-Cost-Effective-Guide-to-Using-Open-Code-Review-for-AI-Programming-Tools-08-19)

### [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.md)

Chinese AI agent tools offer a game-changing strategy for independent developers to access a massive pool of 1.6 billion free tokens monthly.

`Token Optimization` `Cost Savings` `Chinese AI` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/10) · [telegra.ph](https://telegra.ph/How-Chinese-AI-Agent-Tools-Leverage-16-Billion-Free-Tokens-08-19)

### [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md)

Respond.io crossed **$35M in annual recurring revenue** last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to…

`Artificial Intelligence` `Customer Service AI` `SaaS Business` `AI Features` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/67)

### [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md)

Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x.

`LLM` `AI Cost Optimization` `Coding Agents` `Machine Learning` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/66) · [telegra.ph](https://telegra.ph/Chinese-Models-Are-Not-2x-Cheaper-Once-Your-Agent-Starts-Caching-08-24)

### [Never Use a Model Where Code Can Decide](articles/never-use-a-model-where-code-can-decide.md)

Writing code got cheap.

`AI` `SoftwareDevelopment` `IndieDev` `Coding` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/65) · [telegra.ph](https://telegra.ph/Never-Use-a-Model-Where-Code-Can-Decide-08-23)

### [The $22K-a-Month AI Tool That Never Bought a Single Ad](articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.md)

StoryShort hit $22,000 a month in its first three months.

`AI Tools` `Indie Hacking` `SEO` `YouTube Marketing` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/64) · [telegra.ph](https://telegra.ph/The-22K-a-Month-AI-Tool-That-Never-Bought-a-Single-Ad-08-23)

### [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](articles/stop-using-ai-as-a-chatbot-how-to-build-an-indie.md)

Ninety percent of the people who open an AI tool type a question into it.

`AI` `Productivity` `IndieDev` `AIWorkflows` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/63) · [telegra.ph](https://telegra.ph/Stop-Using-AI-as-a-Chatbot-How-to-Build-an-Indie-Workstation-with-Skills-and-Automation-08-23)

### [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md)

Selling one workflow to a hundred people costs roughly what selling it to one person costs, and selling custom code to a hundred people costs a hundred times as much, because the thing being sold i…

`Recurring Revenue` `Cost Savings` `SaaS Business` `AI Features` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/47) · [telegra.ph](https://telegra.ph/How-to-Turn-Your-Obsidian-Vault-Into-an-Autonomous-AI-Research-Agent-08-23)

### [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md)

English write-ups rank these tools on model quality and price per token.

`AI Productivity` `Development Tools` `AI Pricing` `Chinese AI` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/50) · [telegra.ph](https://telegra.ph/The-Hidden-Costs-of-AI-Coding-Tools-What-English-Developers-Dont-Know-08-23)

### [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md)

As a solo developer shipping products alone, manual DevOps and repetitive data processing tasks are the silent killers of your side-project momentum, but configuring raw AI agents often creates mor…

`Indie Hacking` `Artificial Intelligence` `Software Development` `Automation` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/43) · [telegra.ph](https://telegra.ph/Stop-Doing-Manual-DevOps-How-I-Use-loop-and-hook-to-Automate-My-Daily-Indie-Hacker-Tasks-08-22)

### [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.md)

In special-purpose vehicles — tankers, sweepers, the trucks nobody films for fun — one effective sales lead costs somewhere between 100 and 1,000 yuan, and a buyer who actually signs wires a hundre…

`Revenue Growth` `Automation Systems` `Niche Market` `AI Startups` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/53) · [telegra.ph](https://telegra.ph/Why-Vanity-Metrics-Kill-AI-Startups-700-Customers-and-60000-RMB-From-One-Niche-Account-08-23)

### [Claude Code and Codex for Office Automation](articles/claude-code-and-codex-for-office-automation.md)

Claude Code and Codex offer powerful tools for office automation, improving task efficiency and productivity.

`Technology` `Productivity` `SaaS Business` `AI Features` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/59) · [telegra.ph](https://telegra.ph/Office-Automation-with-Claude-Code-and-Codex-08-23)

### [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md)

Managing AI Agent skills is not merely about tools; it's about designing workflows to boost your productivity.

`Productivity` `AI Programming` `AI Features` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/18) · [telegra.ph](https://telegra.ph/Best-Practices-for-AI-Agent-Skill-Management-08-21)

### [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md)

A six-hour Chrome extension pays $400 a month.

`Artificial Intelligence` `Productivity` `SaaS Business` `Niche Market` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/23) · [telegra.ph](https://telegra.ph/Debunking-the-Myth-of-Overnight-Success-in-Micro-SaaS-08-21)

### [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md)

On ReactBench, GPT 5.6 Sol and Fable 5 posted Pass@1 scores of 43.1% and 41.2%.

`Artificial Intelligence` `Software Development` `Machine Learning` `AI code review` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/36) · [telegra.ph](https://telegra.ph/Choosing-the-Right-AI-Code-Review-Tool-A-Developers-Guide-08-21)

### [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.md)

Most indie developers open SimilarWeb, look at the big monthly visits number, and close the tab.

`AI tools` `Indie developers` `Niche market` `Indie development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/30) · [telegra.ph](https://telegra.ph/Stop-Reading-SimilarWeb-Like-a-Traffic-Dashboard--Read-It-Like-a-Feasibility-Test-08-21)

### [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](articles/how-indie-developers-are-building-ai-powered-digital.md)

Independent developers are using AI to mass-produce local SEO content and build vertical service sites, packaging them into "digital properties" and renting them to local businesses for monthly ren…

`Passive Income` `Indie Development` `AI-Powered` `Digital Landlords` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/26) · [telegra.ph](https://telegra.ph/How-Indie-Developers-Are-Building-AI-Powered-Digital-Landlords-and-Renting-Them-Out-for-Monthly-Cash-Flow-08-21)

### [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md)

When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks.

`Developer Productivity` `Code Review` `AI Features` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/40) · [telegra.ph](https://telegra.ph/Why-Stripping-80-of-System-Prompts-Actually-Improved-Claude-Codes-Performance-08-21)

### [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.md)

If you run a solo dev shop, the day goes to fragmented feeds, forty open tabs, and backend maintenance that eats the hours meant for product logic.

`Productivity` `Recurring Revenue` `AI Features` `Niche Market` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/29) · [telegra.ph](https://telegra.ph/Stop-Chatting-With-AI-How-I-Use-loop-and-hook-to-Automate-My-Indie-Dev-Workflow-08-19)

### [Boosting AI Bot Conversion: A Deep Dive into Funnel Data](articles/boosting-ai-bot-conversion-a-deep-dive-into-funnel-data.md)

One reported case moved entry-group conversion from 9.1% to 55.1% by rebuilding an automated onboarding flow around what the funnel data actually showed, rather than around what the team assumed us…

`AI Implementation` `AI Bot Conversion` `Funnel Data Analysis` `Enterprise AI Adoption` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/21) · [telegra.ph](https://telegra.ph/Boosting-AI-Bot-Conversion-A-Deep-Dive-into-Funnel-Data-08-19)

### [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md)

OmniRoute aggregates 237 providers and advertises roughly 1.6 billion free tokens a month, and that figure is arithmetic rather than a promotion, because the RTK+Caveman layer compresses 10,000 tok…

`Token Optimization` `Cost Savings` `Indie Development` `Development Tools` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/12) · [telegra.ph](https://telegra.ph/16-Billion-Free-Tokens-Is-a-Compression-Ratio-Not-a-Strategy-08-19)

### [From AI Demo to Product: Loop Engineering for Indie Devs](articles/from-ai-demo-to-product-loop-engineering-for-indie-devs.md)

The agent processes 40-plus podcast channels overnight, transcribed and summarized, ready to read by morning.

`Productivity` `AI Implementation` `Automation Systems` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/24) · [telegra.ph](https://telegra.ph/From-AI-Demo-to-Product-Loop-Engineering-for-Indie-Devs-08-19)

### [The 5 AI Features That Separated 27 Profitable Solopreneurs From the Rest](articles/the-5-ai-features-that-separated-27-profitable-solopreneurs.md)

Of the 27 AI-powered micro-SaaS projects that generated predictable monthly revenue in a recent analysis, every profitable one used at least three of the same five architectural components.

`AI Automation` `Micro SaaS` `Indie Developer` `AI for Solopreneurs` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/31) · [telegra.ph](https://telegra.ph/The-5-AI-Features-That-Separated-27-Profitable-Solopreneurs-From-the-Rest-08-19)

### [Token Optimization for Indie Developers' AI API Bills](articles/token-optimization-for-indie-developers-ai-api-bills.md)

In July 2026, while indie developers building AI coding products full-time watched their API burn rate climb toward their revenue, a quieter shift in the Chinese developer stack showed a different…

`AI Costs` `Token Optimization` `SaaS Business` `Chinese AI` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/37) · [telegra.ph](https://telegra.ph/Token-Optimization-for-Indie-Developers-AI-API-Bills-08-19)

### [Why Pi's 1000-Token Agent Engine Needs a Sandbox Before You Touch It](articles/why-pi-s-1000-token-agent-engine-needs-a-sandbox-before-you.md)

Pi's system prompt and its 4 tool descriptions come to under 1,000 tokens, which is the whole reason to like it.

`Security` `AI Programming` `Indie Development` `Sandbox` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/39) · [telegra.ph](https://telegra.ph/Why-Pis-1000-Token-Agent-Engine-Needs-a-Sandbox-Before-You-Touch-It-08-19)

### [How to Build a Micro-SaaS Without Spending a Dime on Ads](articles/how-to-build-a-micro-saas-without-spending-a-dime-on-ads.md)

Jordan posted an introduction thread across 3 Reddit sub-boards and had 200 people asking for access within days, at zero cost, and those users stuck around better than the paid traffic he never bo…

`Micro-SaaS` `Rental Business` `SaaS Business` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/27) · [telegra.ph](https://telegra.ph/How-to-Build-a-Micro-SaaS-Without-Spending-a-Dime-on-Ads-08-19)

### [Beyond Chat: How Codex Can Automate Your Word/Excel/PPT/PDF Workflows](articles/beyond-chat-how-codex-can-automate-your-word-excel-ppt-pdf.md)

Codex's office automation capabilities, which are severely underestimated, can be transformed into powerful document processing agents, as shown by real-world developers, one of whom automated PDF…

`Codex` `AI Programming` `Automation Systems` `Office Automation` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/19) · [telegra.ph](https://telegra.ph/Beyond-Chat-How-Codex-Can-Automate-Your-WordExcelPPTPDF-Workflows-08-19)

### [When AI Customer Service Backfired: Klarna’s Case and the Four-Stage Path to Enterprise AI Adoption](articles/when-ai-customer-service-backfired-klarna-s-case-and-the.md)

Klarna reported $4 million a year in savings and a 99.96 percent conversation engagement rate, the kind of pair of numbers that ends an internal debate before it starts.

`AI Implementation` `AI Costs` `Niche Market` `Profitable Business` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/38) · [telegra.ph](https://telegra.ph/When-AI-Customer-Service-Backfired-Klarnas-Case-and-the-Four-Stage-Path-to-Enterprise-AI-Adoption-08-19)

### [The AI Branding Revolution: How Indie Developers Are Ditching Design Costs with AI](articles/the-ai-branding-revolution-how-indie-developers-are.md)

Chris launched WiseMindAI last year and came out of a single session with Miora's brand visual template holding more than ten finished assets, covering color schemes, typography and social graphics…

`AI Tools` `Cost Savings` `SaaS Business` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/32) · [telegra.ph](https://telegra.ph/The-AI-Branding-Revolution-How-Indie-Developers-Are-Ditching-Design-Costs-with-AI-08-19)

### [MonkeyCode: The Open-Source AI Coding Platform With 900 Million Free Tokens](articles/monkeycode-the-open-source-ai-coding-platform-with-900.md)

MonkeyCode's free tier includes 900 million tokens, deploys to your own network with 1 command, and ships as open source you can read.

`Open-Source` `AI Costs` `Indie Development` `Development Tools` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/28) · [telegra.ph](https://telegra.ph/MonkeyCode-The-Open-Source-AI-Coding-Platform-With-900-Million-Free-Tokens-08-19)

### [Charge Per Conversation, Not Per Seat: The Billing Model Behind AI Support](articles/charge-per-conversation-not-per-seat-the-billing-model.md)

Respond.io bills its customers for every contact who had a conversation in a given month rather than for every employee login, and I think that one decision explains more about the company's positi…

`Customer Service AI` `Revenue Growth` `SaaS Business` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/46) · [telegra.ph](https://telegra.ph/Charge-Per-Conversation-Not-Per-Seat-The-Billing-Model-Behind-AI-Support-08-23)

### [When the AI Picks for the Customer, You Become a Supplier](articles/when-the-ai-picks-for-the-customer-you-become-a-supplier.md)

WeChat's Xiaowei agent went into closed testing this year, and Qwen's brand agents already have Luckin Coffee and KFC connected to them.

`Automation` `Indie Development` `AI Branding` `Merchants` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/52) · [telegra.ph](https://telegra.ph/When-the-AI-Picks-for-the-Customer-You-Become-a-Supplier-08-23)

### [A 30-Line Script, 200 Users, and a Niche Nobody Wanted](articles/a-30-line-script-200-users-and-a-niche-nobody-wanted.md)

"Solving a niche problem is the secret to building a profitable Micro-SaaS." This common advice ignores the power of focusing on a single, well-defined pain point in a specific market.

`AI Automation` `Micro SaaS` `SaaS Business` `Niche Market` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/14) · [telegra.ph](https://telegra.ph/A-30-Line-Script-200-Users-and-a-Niche-Nobody-Wanted-08-19)

### [AI Took Over My Coding. What Broke Was How I Learn.](articles/ai-took-over-my-coding-what-broke-was-how-i-learn.md)

One indie developer writing in Chinese in July 2026 put it about as plainly as anyone has: AI has already replaced all of his coding work, and the systematic knowledge he accumulates keeps shrinking.

`AI Implementation` `AI Costs` `Chinese AI` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/45) · [telegra.ph](https://telegra.ph/AI-Took-Over-My-Coding-What-Broke-Was-How-I-Learn-08-23)

### [AI Side Hustle: Stop Selling Hours, Start Selling Plans](articles/ai-side-hustle-stop-selling-hours-start-selling-plans.md)

The most honest numbers I have seen attached to an AI side hustle are small enough that nobody would put them in a headline: one operator, Xiaomin, clears about 3,873 yuan a month generating images…

`Automation` `Passive Income` `Niche Market` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/49) · [telegra.ph](https://telegra.ph/Sell-Plans-Not-Hours-What-an-AI-Side-Hustle-Actually-Earns-08-23)

### [Sell It Before You Build It: How Indie Devs Validate AI Products](articles/sell-it-before-you-build-it-how-indie-devs-validate-ai.md)

The most useful number I've come across in indie product write-ups this year is a hundred orders in twenty-four hours, and the thing worth noticing is what produced it: Pieter Levels put up a crude…

`Productivity` `AI Costs` `Automation Systems` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/48) · [telegra.ph](https://telegra.ph/Sell-It-Before-You-Build-It-How-Indie-Devs-Validate-AI-Products-08-23)

### [58 Million Plays Started With One Account, Not Four](articles/58-million-plays-started-with-one-account-not-four.md)

Two brothers ran a single short-video account until one piece of content took off, and only then copied it across several accounts, which is how the cumulative play count passed 58 million.

`Content Marketing` `Video Marketing` `SaaS Business` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/13) · [telegra.ph](https://telegra.ph/Why-Most-Indie-Dev-Short-Videos-Never-Make-Money-08-19)

### [Choosing the Right AI Model for Coding: Cost vs. Efficiency](articles/choosing-the-right-ai-model-for-coding-cost-vs-efficiency.md)

Fable 5, the cheapest option at $9.05 per run, delivers only 41.2% accuracy in React projects.

`Code Review` `AI Costs` `Indie Development` `Development Tools` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/22) · [telegra.ph](https://telegra.ph/Choosing-the-Right-AI-Model-for-Coding-Cost-vs-Efficiency-08-19)

### [The Hidden Costs of GPT-5.6 Model Selection: A Developer's Real-World Guide](articles/the-hidden-costs-of-gpt-5-6-model-selection-a-developer-s.md)

"Choosing the right GPT-5.6 model for your business is more about avoiding cost overruns than just picking the cheapest option."

`AI Implementation` `AI Costs` `AI Programming` `Cost Savings` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/34) · [telegra.ph](https://telegra.ph/The-Hidden-Costs-of-GPT-56-Model-Selection-A-Developers-Real-World-Guide-08-19)

### [Your Agent Writes Code Faster Than Anyone Can Review It](articles/your-agent-writes-code-faster-than-anyone-can-review-it.md)

The bottleneck in AI-assisted development moved, and most teams have not moved their tooling to follow it.

`AI` `Artificial Intelligence` `Startup` `Programming` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/55) · [telegra.ph](https://telegra.ph/Your-Agent-Writes-Code-Faster-Than-Anyone-Can-Review-It-08-23)

### [Why Your Indie App Needs Short-Form Video Marketing (And How to Get Started)](articles/why-your-indie-app-needs-short-form-video-marketing-and-how.md)

The videos run about 60 seconds.

`Productivity` `Content Creation` `Indie Development` `Short Form Video` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/41) · [telegra.ph](https://telegra.ph/Why-Your-Indie-App-Needs-Short-Form-Video-Marketing-And-How-to-Get-Started-08-19)

### [Your AI Coding Bill Scales With Your Repo, Not Your Output](articles/your-ai-coding-bill-scales-with-your-repo-not-your-output.md)

Most people budgeting for a coding assistant reason about it the way they reason about a printer, as though the cost tracked how much comes out.

`AI` `Artificial Intelligence` `Programming` `Software Engineering` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/56) · [telegra.ph](https://telegra.ph/Your-AI-Coding-Bill-Scales-With-Your-Repo-Not-Your-Output-08-23)

### [The Klarna Lesson: Why AI Implementation Needs a Staircase, Not a Leap](articles/the-klarna-lesson-why-ai-implementation-needs-a-staircase.md)

Klarna's AI customer service experiment, which replaced 700 human agents, initially saved $40 million in a year, but the quality of service suffered so badly that they had to rehire humans, leading…

`Artificial Intelligence` `AI Systems` `Automation Systems` `Enterprise Automation` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/35) · [telegra.ph](https://telegra.ph/The-Klarna-Lesson-Why-AI-Implementation-Needs-a-Staircase-Not-a-Leap-08-19)

### [AI Local Websites Don’t Rent for $3K/Month—Until You Do This](articles/ai-local-websites-don-t-rent-for-3k-month-until-you-do-this.md)

You can build AI-generated local business websites, rent them to plumbers or dentists for $500–$3,000 a month, and scale to passive income.

`AI Tools` `Local SEO` `Niche Market` `Revenue Growth` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/57) · [telegra.ph](https://telegra.ph/AI-Generated-Local-Business-Websites-Dont-Rent-for-3000Month-Until-You-Do-This-08-19)

### [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](articles/the-token-cost-war-why-price-per-million-tokens-now-decides.md)

The competition among model vendors used to be argued in benchmark scores, and it is now being argued in cost per million tokens — Indian enterprises are adopting Chinese models at input prices as…

`AI` `Artificial Intelligence` `Startup` `Business` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/51) · [telegra.ph](https://telegra.ph/The-Token-Cost-War-Why-Price-per-Million-Tokens-Now-Decides-the-AI-Market-08-23)

### [Rank and Rent: Local SEO Sites That Earn $500 to $3,000 a Month](articles/rank-and-rent-local-seo-sites-that-earn-500-to-3-000-a-month.md)

The rank-and-rent model is old enough that most people have heard of it and specific enough that almost nobody runs the numbers before starting: you build a website for a local service category, yo…

`AI` `Digital Marketing` `Entrepreneurship` `Content Marketing` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/61) · [telegra.ph](https://telegra.ph/Rank-and-Rent-Building-Local-SEO-Sites-That-Earn-500-to-3000-a-Month-08-23)

### [AI Agent Loop Engineering: Karpathy's Method for 5x Productivity Gains](articles/ai-agent-loop-engineering-karpathy-s-method-for-5x.md)

A developer in China’s AI community achieved 5x productivity gains using loop engineering, reducing MVP development time from four prompt tuning sessions to a single command installation.

`Enterprise AI` `Developer Tools` `Automation Systems` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/15) · [telegra.ph](https://telegra.ph/AI-Agent-Loop-Engineering-Karpathys-Method-for-5x-Productivity-Gains-08-19)

### [Klarna Replaced 700 Support Agents With AI. Then It Started Hiring Again.](articles/klarna-replaced-700-support-agents-with-ai-then-it-started.md)

In early 2024 the European payments company Klarna put an AI customer-service assistant in place of roughly 700 human agents and said the move was worth about $40 million a year in additional profit.

`Business` `AI Implementation` `Automation Systems` `Enterprise Automation` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/58) · [telegra.ph](https://telegra.ph/Klarna-Replaced-700-Support-Agents-With-AI-Then-It-Started-Hiring-Again-08-23)

### [The First Line of Defense in AI Programming: Environment Variable Management](articles/the-first-line-of-defense-in-ai-programming-environment.md)

MonkeyCode ships with 900 million free tokens and supports private deployment, which tells you exactly what its users are doing: pointing an AI coding tool at their own keys, on their own infrastru…

`AI Development` `AI Programming` `Environment Variables` `AI Security` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/33) · [telegra.ph](https://telegra.ph/The-First-Line-of-Defense-in-AI-Programming-Environment-Variable-Management-08-19)

### [AI Programming Tool Selection Strategy: From Rapid Prototyping to Long-term Collaboration](articles/ai-programming-tool-selection-strategy-from-rapid.md)

A specialized code review agent beat Claude Code on accuracy across 200 real pull requests and 50 open-source repositories while burning about one-ninth the tokens.

`AI Implementation` `AI Costs` `Development Tools` `Enterprise Automation` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/16) · [telegra.ph](https://telegra.ph/AI-Programming-Tool-Selection-Strategy-From-Rapid-Prototyping-to-Long-term-Collaboration-08-19)

### [How Chinese Developers Are Using Codex Record & Replay to Streamline Repetitive Workflows](articles/how-chinese-developers-are-using-codex-record-replay-to.md)

A monthly report that used to take four hours now takes a few minutes.

`Workflow Automation` `AI Development` `Chinese AI` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/25) · [telegra.ph](https://telegra.ph/How-Chinese-Developers-Are-Using-Codex-Record--Replay-to-Streamline-Repetitive-Workflows-08-19)

### [AI Model Costs: Beyond Per-Token Pricing](articles/ai-model-costs-beyond-per-token-pricing.md)

Microsoft's evaluation of Kimi K3 landed on a number that should change how you read a pricing page: about 60 percent of the cost difference between models comes from the thinking depth a task requ…

`AI Systems` `AI Implementation` `AI Pricing` `Indie Development` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/20) · [telegra.ph](https://telegra.ph/Beyond-Token-Pricing-How-Indie-Devs-Should-Really-Evaluate-AI-Model-Costs-08-19)

### [One Person, 8 AI Agents, 3,000 Baseball Caps in Two Months](articles/one-person-8-ai-agents-3-000-baseball-caps-in-two-months.md)

Zhang Qianchao runs a custom baseball cap export business on Alibaba.com with 8 AI agents and no employees, and in 2 months he shipped 3,000 caps to buyers across Europe, the Americas and South Ame…

`AI Agents` `Revenue Growth` `Niche Market` `Automation Systems` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/60) · [telegra.ph](https://telegra.ph/One-Person-8-AI-Agents-3000-Baseball-Caps-in-Two-Months-08-23)

### [Why Your AI Agent Goes Off the Rails: Give It Boring Work First](articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.md)

One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology:…

`AI Agents` `AI Implementation` `AI Programming` `AI Limits` · [reply box](https://github.com/xyzs996/llm-api-pricing/discussions/54) · [telegra.ph](https://telegra.ph/Why-Your-AI-Agent-Goes-Off-the-Rails-Give-It-Boring-Work-First-08-23)

## Related

- [llm-cost-calculator](https://github.com/xyzs996/llm-cost-calculator) — the same price table as a calculator: put your own token counts in and get a bill, with peak/off-peak and the long-context cliff handled.
- [free-llm-api](https://github.com/xyzs996/free-llm-api) — verified free LLM API tiers, rate limits, and no-card options.

## Reuse

Copyright © 2026 xyzs996. Everything here — the write-ups in
`articles/` and the dataset in `data/` alike — is licensed
[CC BY 4.0](LICENSE): copy it, republish it, build on it, sell it.

One condition: say where it came from. A link back to
<https://xyzs996.github.io/llm-api-pricing/> next to whatever you reuse is enough.
