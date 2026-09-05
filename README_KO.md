# AI 코딩 에이전트의 실제 비용: 507개 수치, 모두 출처 문장과 날짜 포함

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · **한국어** · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

공개 데이터셋입니다. 56편의 현장 기록에 나온 모든 수치 —— 가격, 비율, 배수, 토큰 수, 소요 시간 —— 를 한 줄씩 뽑아내고 **원래 문장 전체와 게시 날짜를 함께** 실었습니다.

## 에이전트 모델의 오늘 가격

Design Arena의 *agents* 부문에 순위가 있는 59개 모델의 100만 토큰당 **정가**입니다. 청구서가 아닙니다 — 캐시, 배치, 제공자마다 가격이 다릅니다. OpenRouter의 공개 카탈로그에서 2026-09-05에 마지막으로 읽었습니다. 가장 싼 3개:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |
| $0.30 | $1.20 | MiniMax M3 `batch` | #10 python-pptxslides |

[59개 전체](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**같은 숫자, 반대의 답.** Google 와 xAI 모두 입력 200,000 토큰에서 비싼 요금으로 넘어갑니다. 그런데 **정확히** 200,000 인 요청은 Google 에서는 싼 쪽, xAI 에서는 비싼 쪽으로 청구됩니다. 다른 가격표는 경계 숫자만 적고 끝납니다. 어느 쪽인지를 각 업체 공식 페이지의 원문과 확인 날짜와 함께: [same number, opposite answer](prices.md#same-number-opposite-answer) (영문).

**위 표는 정가일 뿐, 이와 일치하는 청구서는 없습니다.** 숫자를 움직이는 것은 캐시 적중, 재시도, 그리고 두 번 값을 치르고 다시 보내는 컨텍스트인데 카탈로그는 그 어느 것도 보여주지 못합니다. 그 간극을 따라간 글이 하나 있습니다: [토큰 요금은 실제로 어디로 가는가](https://github.com/xyzs996/llm-api-pricing/discussions/37). 이 표가 답할 수 없는 질문 하나로 끝납니다 — **지난달에 얼마를 냈고, 그중 다시 보내기 아까웠던 컨텍스트는 얼마였습니까?** 답장 상자는 그 페이지에 있습니다. 이 페이지에는 없습니다.

## 수치 먼저

아래 줄들은 **영어 원문 그대로**이며 번역하지 않았습니다. 수치는 원래 문장에서 떼어내면 검증할 수 없기 때문입니다 —— `$1.43`이 100만 토큰당인지, 월 요금인지, 좌석당인지는 그 문장에만 적혀 있습니다.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `72%` | Mobile developers report 72% of AI-generated code fails initial verification on real devices, and frontend developers waste 45% of their time debugging visual inconsistencies that only appear in production. | [The Real Pitfalls of AI Agent Development: From Code Generation to Functional Verification](articles/the-real-pitfalls-of-ai-agent-development-from-code.md) |
| `60%` | The recruitment automation tool hit a 60% efficiency gain after 28 rounds of iteration, but I’d argue that figure glosses over the real cost: dynamic page elements like shifting button positions and pop-ups demanded extra layers for state recognition and result verification. | [The AI Automation Ceiling: Why 60% Efficiency Doesn't Equal 20% Conversion](articles/the-ai-automation-ceiling-why-60-efficiency-doesn-t-equal.md) |
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

[507개 전체](figures.md)

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
