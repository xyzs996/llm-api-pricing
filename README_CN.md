# AI 编程工具到底花多少钱:343 行数,每行带原句和日期

[English](./README.md) · **中文** · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

这是一份公开数表。36 篇实测笔记里出现过的每一个数 —— 价格、百分比、倍数、token 数、耗时 —— 都抽成一行,**每行都附上它原来所在的那句话和发布日期**。

## 跑 agent 的模型,今天多少钱

60 个在 Design Arena 的 agents 各档里排过名的模型,每百万 token 的**挂牌价**——不是账单:缓存命中、batch、不同接入方各有各的价。取自 OpenRouter 的公开目录,最后核到 2026-08-22。最便宜的三个:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #3 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[全部 60 个](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**同一个数,相反的答案。** Google 和 xAI 都在 200,000 个输入 token 上跳贵价档 —— 而**正好** 200,000 这一发,Google 按便宜的收,xAI 按贵的收。别处的价目表印一个门槛数就没了下文。哪家算在哪一边、引的是厂商自己那页上的原话、附核对日期:[same number, opposite answer](prices.md#same-number-opposite-answer)(英文)。

**上面那张是挂牌价,没有一张账单跟它对得上。** 差额在缓存命中、重试、和你要付两遍钱重发的上下文里 —— 这些目录表一样都看不见。有一篇专门去追这段差额:[钱到底花在哪儿了](https://github.com/xyzs996/llm-api-pricing/discussions/37)。它结尾问的正是这张表答不上来的那个问题:**上个月你付了多少,其中有多少是你不情愿重发一遍的上下文?** 那一页有回复框,这一页没有。

## 先看数

下面几行是**英文原文照抄**,没有翻译:一个数离开它原来那句话就没法核对 —— `$1.43` 可能是每百万 token、每月、也可能是每个席位。

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `20%` | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. | [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Office Automation with Claude Code and Codex](articles/office-automation-with-claude-code-and-codex.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |
| `90%` | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. | [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md) |
| `80%` | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. | [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) |
| `$30` | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. | [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.md) |
| `$1,000` | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. | [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](articles/how-indie-developers-are-building-ai-powered-digital.md) |
| `40-second` | When an independent developer uses Agency Agents to set up a 40-second response cycle for e-commerce listings, they are building a feedback loop that reads market conditions and adjusts, which is what separates a timed automation from a script on a timer. | [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.md) |
| `9.1%` | One reported case moved entry-group conversion from 9.1% to 55.1% by rebuilding an automated onboarding flow around what the funnel data actually showed, rather than around what the team assumed users were doing. | [Boosting AI Bot Conversion: A Deep Dive into Funnel Data](articles/boosting-ai-bot-conversion-a-deep-dive-into-funnel-data.md) |

[全部 343 行](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

字段里的 `published` 是那篇笔记发出去的日子,**不是这个价钱当时还作数的日子**。价格一直在变,每一行都得按它自己的日期读。

## 正文

正文是**英文**,在这儿:https://xyzs996.github.io/llm-api-pricing/ —— 带数表、题目页和厂商页。只想要数的话,上面两条 `curl` 就够了,不用读正文。

## 说一句

- **收藏这个仓库**,数表更新会跟着走。数据是 CC BY 的,收不收藏都随便拿,这儿不拿数据换 star。收藏改变的是**下一个找这些数的人**能不能找到 —— GitHub 的搜索排序和「相关仓库」推荐都把 star 数算进去。
- **数不对?** 哪个价钱变了、你自己跑出来是另一个数 —— 提个issue。这个仓库就是干这个的。 ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **想要的数这儿没有?** 说清楚要哪个指标、哪家、什么单位,一行就够 —— 表单只有一格必填,收到就收成新行。 ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0:随便复制、转载、再加工、拿去卖。唯一的条件是说一声出处,挂个链接回 https://xyzs996.github.io/llm-api-pricing/ 就行。
