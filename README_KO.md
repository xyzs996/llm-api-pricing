# AI 코딩 에이전트의 실제 비용: 999개 수치, 모두 출처 문장과 날짜 포함

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · **한국어** · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

공개 데이터셋입니다. 81편의 현장 기록에 나온 모든 수치 —— 가격, 비율, 배수, 토큰 수, 소요 시간 —— 를 한 줄씩 뽑아내고 **원래 문장 전체와 게시 날짜를 함께** 실었습니다.

## 에이전트 모델의 오늘 가격

Design Arena의 *agents* 부문에 순위가 있는 110개 모델의 100만 토큰당 **정가**입니다. 청구서가 아닙니다 — 캐시, 배치, 제공자마다 가격이 다릅니다. OpenRouter의 공개 카탈로그에서 2026-11-28에 마지막으로 읽었습니다. 가장 싼 3개:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #18 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #45 pdf |

[110개 전체](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**같은 숫자, 반대의 답.** Google 와 xAI 모두 입력 200,000 토큰에서 비싼 요금으로 넘어갑니다. 그런데 **정확히** 200,000 인 요청은 Google 에서는 싼 쪽, xAI 에서는 비싼 쪽으로 청구됩니다. 다른 가격표는 경계 숫자만 적고 끝납니다. 어느 쪽인지를 각 업체 공식 페이지의 원문과 확인 날짜와 함께: [same number, opposite answer](prices.md#same-number-opposite-answer) (영문).

**위 표는 정가일 뿐, 이와 일치하는 청구서는 없습니다.** 숫자를 움직이는 것은 캐시 적중, 재시도, 그리고 두 번 값을 치르고 다시 보내는 컨텍스트인데 카탈로그는 그 어느 것도 보여주지 못합니다. 그 간극을 따라간 글이 하나 있습니다: [토큰 요금은 실제로 어디로 가는가](https://github.com/xyzs996/llm-api-pricing/discussions/37). 이 표가 답할 수 없는 질문 하나로 끝납니다 — **지난달에 얼마를 냈고, 그중 다시 보내기 아까웠던 컨텍스트는 얼마였습니까?** 답장 상자는 그 페이지에 있습니다. 이 페이지에는 없습니다.

## 수치 먼저

아래 줄들은 **영어 원문 그대로**이며 번역하지 않았습니다. 수치는 원래 문장에서 떼어내면 검증할 수 없기 때문입니다 —— `$1.43`이 100만 토큰당인지, 월 요금인지, 좌석당인지는 그 문장에만 적혀 있습니다.

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

[999개 전체](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

`published`는 그 기록을 게시한 날이지 **그 가격이 유효하던 날이 아닙니다**. 가격은 계속 바뀌므로 각 줄은 그 줄 자신의 날짜 기준으로 읽으십시오.

## 본문

본문은 **영어**이며 여기 있습니다: https://spectracodeai.com/ —— 수치 표, 주제별 페이지, 업체별 페이지가 있습니다. 수치만 필요하다면 위의 `curl` 두 줄이면 충분합니다.

## 한마디

- **이 저장소에 별을** 누르면 갱신을 따라갈 수 있습니다. 데이터는 CC BY라서 별과 무관하게 무엇이든 하실 수 있습니다. 별이 바꾸는 것은 **다음 사람이 이 숫자를 찾을 수 있는지**입니다. GitHub은 검색 순위에도, 비슷한 저장소 추천에도 별 개수를 반영합니다.
- **수치가 틀렸나요?** 가격이 바뀌었거나 직접 재보니 다른 값이 나왔다면 issue를 열어 주십시오. 이 저장소는 그러라고 있습니다. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **원하는 수치가 없나요?** 어떤 지표를, 어느 업체의, 어떤 단위로 —— 한 줄이면 됩니다. 필수 항목은 하나뿐이고, 들어온 요청은 새 줄이 됩니다. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: 복제, 재게시, 가공, 판매 모두 자유입니다. 조건은 하나, 출처를 밝히는 것 —— https://spectracodeai.com/ 링크면 됩니다.
