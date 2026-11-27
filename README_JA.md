# AI コーディングエージェントの実際の料金:978 行、どの行にも出典の一文と日付つき

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · **日本語** · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

オープンなデータセットです。80 本の実測ノートに出てきた数字 —— 料金、割合、倍率、トークン数、所要時間 —— をすべて 1 行ずつに抜き出し、**元の一文と公開日を必ず添えて**あります。

## エージェント向けモデルの今日の値段

Design Arena の *agents* 部門で順位のついた 110 モデルの、100 万トークンあたりの**定価**です。請求額ではありません — キャッシュ、バッチ、提供元ごとに価格は違います。OpenRouter の公開カタログより、最終取得日 2026-11-27。安い順に 3 つ:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #23 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #45 pdf |

[110 モデル全部](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**同じ数字、逆の答え。** Google と xAI はどちらも入力 200,000 トークンで高い方の料金に切り替わります。ただし**ちょうど** 200,000 のとき、Google は安い方、xAI は高い方で課金されます。ほかの価格表は境界の数字を載せてそこで終わりです。どちらに入るかを、各社の公式ページの原文と確認日つきで: [same number, opposite answer](prices.md#same-number-opposite-answer)(英語)。

**上の表は定価であって、これと一致する請求書は一つもありません。**数字を動かすのはキャッシュヒット、リトライ、そして二度払って送り直すコンテキストで、そのどれもカタログには写りません。その差を追いかけた記事があります:[トークン代は実際どこへ消えるのか](https://github.com/xyzs996/llm-api-pricing/discussions/37)。最後に、この表では答えられない問いが一つ残ります — **先月あなたはいくら払い、そのうち送り直しに費やしたコンテキストはどれだけでしたか?** 返信欄はあちらのページにあります。ここにはありません。

## まず数字から

以下の行は**英語の原文そのまま**で、翻訳していません。数字は元の一文から切り離すと検証できないからです —— `$1.43` が 100 万トークンあたりなのか、月額なのか、1 席あたりなのかは、その一文にしか書かれていません。

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
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
| `$80` | In one documented case, a developer spent roughly 4 hours of total human time over 5 days — reviewing, pivoting, and debugging — while an AI agent built the SaaS product, with API token costs for the entire build coming in at $80–120. | [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md) |

[全 978 行](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

`published` はそのノートを公開した日で、**その料金が有効だった日ではありません**。料金は動きます。各行はその行自身の日付で読んでください。

## 本文

本文は**英語**です:https://spectracodeai.com/ —— 数値表、トピック別ページ、ベンダー別ページがあります。数字だけでよければ、上の `curl` 二本で足ります。

## ひとこと

- **このリポジトリにスターを**付けると更新を追えます。データは CC BY なので、スターの有無でできることは変わりません。変わるのは、**次の人がこの数字にたどり着ける**かどうかです。GitHub は検索順位にも、関連リポジトリの表示にも、スター数を使っています。
- **数字が違う?** 料金が変わった、自分で測ったら別の数字になった —— issue を立ててください。このリポジトリはそのためにあります。 ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **欲しい数字がない?** どの指標を、どのベンダーの、どの単位で —— 一行で結構です。必須項目は一つだけ、届いたものは新しい行になります。 ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0:複製・再公開・加工・販売、自由です。条件は一つだけ、出典を示すこと。https://spectracodeai.com/ へのリンクで十分です。
