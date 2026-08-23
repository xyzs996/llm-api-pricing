# AI 코딩 에이전트의 실제 비용: 341개 수치, 모두 출처 문장과 날짜 포함

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · **한국어** · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

공개 데이터셋입니다. 35편의 현장 기록에 나온 모든 수치 —— 가격, 비율, 배수, 토큰 수, 소요 시간 —— 를 한 줄씩 뽑아내고 **원래 문장 전체와 게시 날짜를 함께** 실었습니다.

## 에이전트 모델의 오늘 가격

Design Arena의 *agents* 부문에 순위가 있는 60개 모델의 100만 토큰당 **정가**입니다. 청구서가 아닙니다 — 캐시, 배치, 제공자마다 가격이 다릅니다. OpenRouter의 공개 카탈로그에서 2026-08-22에 마지막으로 읽었습니다. 가장 싼 3개:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #3 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[60개 전체](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**같은 숫자, 반대의 답.** Google 와 xAI 모두 입력 200,000 토큰에서 비싼 요금으로 넘어갑니다. 그런데 **정확히** 200,000 인 요청은 Google 에서는 싼 쪽, xAI 에서는 비싼 쪽으로 청구됩니다. 다른 가격표는 경계 숫자만 적고 끝납니다. 어느 쪽인지를 각 업체 공식 페이지의 원문과 확인 날짜와 함께: [same number, opposite answer](prices.md#same-number-opposite-answer) (영문).

**위 표는 정가일 뿐, 이와 일치하는 청구서는 없습니다.** 숫자를 움직이는 것은 캐시 적중, 재시도, 그리고 두 번 값을 치르고 다시 보내는 컨텍스트인데 카탈로그는 그 어느 것도 보여주지 못합니다. 그 간극을 따라간 글이 하나 있습니다: [토큰 요금은 실제로 어디로 가는가](https://github.com/xyzs996/llm-api-pricing/discussions/37). 이 표가 답할 수 없는 질문 하나로 끝납니다 — **지난달에 얼마를 냈고, 그중 다시 보내기 아까웠던 컨텍스트는 얼마였습니까?** 답장 상자는 그 페이지에 있습니다. 이 페이지에는 없습니다.

## 수치 먼저

아래 줄들은 **영어 원문 그대로**이며 번역하지 않았습니다. 수치는 원래 문장에서 떼어내면 검증할 수 없기 때문입니다 —— `$1.43`이 100만 토큰당인지, 월 요금인지, 좌석당인지는 그 문장에만 적혀 있습니다.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
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
| `$1.25` | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. | [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md) |

[341개 전체](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

`published`는 그 기록을 게시한 날이지 **그 가격이 유효하던 날이 아닙니다**. 가격은 계속 바뀌므로 각 줄은 그 줄 자신의 날짜 기준으로 읽으십시오.

## 본문

본문은 **영어**이며 여기 있습니다: https://xyzs996.github.io/llm-api-pricing/ —— 수치 표, 주제별 페이지, 업체별 페이지가 있습니다. 수치만 필요하다면 위의 `curl` 두 줄이면 충분합니다.

## 한마디

- **이 저장소에 별을** 누르면 갱신을 따라갈 수 있습니다. 데이터는 CC BY라서 별과 무관하게 무엇이든 하실 수 있습니다. 별이 바꾸는 것은 **다음 사람이 이 숫자를 찾을 수 있는지**입니다. GitHub은 검색 순위에도, 비슷한 저장소 추천에도 별 개수를 반영합니다.
- **수치가 틀렸나요?** 가격이 바뀌었거나 직접 재보니 다른 값이 나왔다면 issue를 열어 주십시오. 이 저장소는 그러라고 있습니다. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **원하는 수치가 없나요?** 어떤 지표를, 어느 업체의, 어떤 단위로 —— 한 줄이면 됩니다. 필수 항목은 하나뿐이고, 들어온 요청은 새 줄이 됩니다. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: 복제, 재게시, 가공, 판매 모두 자유입니다. 조건은 하나, 출처를 밝히는 것 —— https://xyzs996.github.io/llm-api-pricing/ 링크면 됩니다.
