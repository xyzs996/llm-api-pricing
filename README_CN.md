# AI 编程工具到底花多少钱:999 行数,每行带原句和日期

[English](./README.md) · **中文** · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

这是一份公开数表。81 篇实测笔记里出现过的每一个数 —— 价格、百分比、倍数、token 数、耗时 —— 都抽成一行,**每行都附上它原来所在的那句话和发布日期**。

## 跑 agent 的模型,今天多少钱

110 个在 Design Arena 的 agents 各档里排过名的模型,每百万 token 的**挂牌价**——不是账单:缓存命中、batch、不同接入方各有各的价。取自 OpenRouter 的公开目录,最后核到 2026-11-28。最便宜的三个:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #18 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #45 pdf |

[全部 110 个](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**同一个数,相反的答案。** Google 和 xAI 都在 200,000 个输入 token 上跳贵价档 —— 而**正好** 200,000 这一发,Google 按便宜的收,xAI 按贵的收。别处的价目表印一个门槛数就没了下文。哪家算在哪一边、引的是厂商自己那页上的原话、附核对日期:[same number, opposite answer](prices.md#same-number-opposite-answer)(英文)。

**上面那张是挂牌价,没有一张账单跟它对得上。** 差额在缓存命中、重试、和你要付两遍钱重发的上下文里 —— 这些目录表一样都看不见。有一篇专门去追这段差额:[钱到底花在哪儿了](https://github.com/xyzs996/llm-api-pricing/discussions/37)。它结尾问的正是这张表答不上来的那个问题:**上个月你付了多少,其中有多少是你不情愿重发一遍的上下文?** 那一页有回复框,这一页没有。

## 先看数

下面几行是**英文原文照抄**,没有翻译:一个数离开它原来那句话就没法核对 —— `$1.43` 可能是每百万 token、每月、也可能是每个席位。

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$5` | For contrast, consider a developer who ran Google Ads at $5/day, initially picking up 7–8 users per day, and reached 20-plus paying customers in 65 days. | [Your Channel Report Is Lying — 107 Signups, 0 Paying Customers](articles/your-channel-report-is-lying-107-signups-0-paying-customers.md) |
| `$3` | A developer running three agents for daily work — email, calendar, research — reported a real cost of roughly $3–5 per month on DeepSeek V4 Flash, against $200–260 per month for the same workload on Opus 4.7. | [DeepSeek's Peak-Hour Price Is Double — How to Schedule Your Batch Agent Jobs Around It](articles/deepseek-s-peak-hour-price-is-double-how-to-schedule-your.md) |
| `$60` | The $60 applies to DeepSeek V4.1 Flash as a model, not as a general-purpose wallet you can spend across whatever OpenCode hosts, and because this credit does not follow you there if your agent workflow leans on a second model for a specific step, it stays tied to that one model rather than extending to any other model your workflow might call on. | [The DeepSeek Quota Math Nobody Publishes: $10/Month, Peak-Hour Doubling, or a 3-Million-Yuan Server](articles/the-deepseek-quota-math-nobody-publishes-10-month-peak-hour.md) |
| `$0.87` | If you think in dollars, another data point puts DeepSeek V4 at $0.87 per million output tokens, against GLM-5.2 at $4.4 and Kimi K3 at $15, while a third puts V4-Flash at $0.028 per million tokens, which is an order of magnitude off the previous figures. | [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md) |
| `$0.26` | DeepSeek V3.2 under the OpenClaw framework comes in at $0.26 per million input tokens and $0.38 output, the lowest-cost model in that particular comparison, while MiniMax M2.7 sits at $0.30 input and $1.20 output with a 204.8K context window, built for coding and agent workflows. | [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md) |
| `$3` | One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day. | [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md) |
| `$7` | One developer launched a SaaS and waited 2.5 months for the first paying customer, a $7 sale, and reported that the customer found the product through Google organic search. | [Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else](articles/your-channel-report-is-lying-1-215-of-1-463-branded-search.md) |
| `$3` | Another framing: Kimi K3 at $3/$15 per million tokens against Fable 5 at $10/$50, with intelligence index scores of 59.7 and 62.1. | [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md) |
| `$0.181` | Sources are already presenting $0.181 per successful task next to a coding score of 96.0, side by side, which is the shape the conversation is heading toward. | [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md) |
| `$3` | For scale on what a real month looks like: three agents doing email, calendar, and research ran about $3–5 per month on DeepSeek V4 Flash against $200–260 on Opus 4.7, with what the user described as a small quality gap. | [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md) |
| `60%` | For rider recruitment, this meant focusing on repetitive actions like resume browsing and initial outreach, which is where the team, using Codex, developed a tool that iterated 28 times before it was able to achieve a 60% efficiency increase in public domain recruitment tasks — the same repetitive work of resume browsing and initial outreach that had been the focus from the start. | [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](articles/the-hidden-cost-of-ai-automation-turning-human-instincts.md) |
| `$10` | OpenCode Go users pay $10/month and receive $60 of DeepSeek V4.1 Flash usage credit that never expires — up from the original $30/month allotment, upgraded in Phase 2 to $60 and kept long-term. | [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) |

[全部 999 行](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

字段里的 `published` 是那篇笔记发出去的日子,**不是这个价钱当时还作数的日子**。价格一直在变,每一行都得按它自己的日期读。

## 正文

正文是**英文**,在这儿:https://spectracodeai.com/ —— 带数表、题目页和厂商页。只想要数的话,上面两条 `curl` 就够了,不用读正文。

## 说一句

- **收藏这个仓库**,数表更新会跟着走。数据是 CC BY 的,收不收藏都随便拿,这儿不拿数据换 star。收藏改变的是**下一个找这些数的人**能不能找到 —— GitHub 的搜索排序和「相关仓库」推荐都把 star 数算进去。
- **数不对?** 哪个价钱变了、你自己跑出来是另一个数 —— 提个issue。这个仓库就是干这个的。 ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **想要的数这儿没有?** 说清楚要哪个指标、哪家、什么单位,一行就够 —— 表单只有一格必填,收到就收成新行。 ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0:随便复制、转载、再加工、拿去卖。唯一的条件是说一声出处,挂个链接回 https://spectracodeai.com/ 就行。
