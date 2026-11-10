# AI コーディングエージェントの実際の料金:731 行、どの行にも出典の一文と日付つき

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · **日本語** · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

オープンなデータセットです。68 本の実測ノートに出てきた数字 —— 料金、割合、倍率、トークン数、所要時間 —— をすべて 1 行ずつに抜き出し、**元の一文と公開日を必ず添えて**あります。

## エージェント向けモデルの今日の値段

Design Arena の *agents* 部門で順位のついた 83 モデルの、100 万トークンあたりの**定価**です。請求額ではありません — キャッシュ、バッチ、提供元ごとに価格は違います。OpenRouter の公開カタログより、最終取得日 2026-11-10。安い順に 3 つ:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.006 | $0.50 | DeepSeek V4.1 Flash 1017 | #4 spreadsheet |
| $0.01 | $6.80 | GLM 5.2 | #6 pdf |
| $0.011 | $0.20 | DeepSeek V4.1 Flash 1017 `batch` | #4 spreadsheet |

[83 モデル全部](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**同じ数字、逆の答え。** Google と xAI はどちらも入力 200,000 トークンで高い方の料金に切り替わります。ただし**ちょうど** 200,000 のとき、Google は安い方、xAI は高い方で課金されます。ほかの価格表は境界の数字を載せてそこで終わりです。どちらに入るかを、各社の公式ページの原文と確認日つきで: [same number, opposite answer](prices.md#same-number-opposite-answer)(英語)。

**上の表は定価であって、これと一致する請求書は一つもありません。**数字を動かすのはキャッシュヒット、リトライ、そして二度払って送り直すコンテキストで、そのどれもカタログには写りません。その差を追いかけた記事があります:[トークン代は実際どこへ消えるのか](https://github.com/xyzs996/llm-api-pricing/discussions/37)。最後に、この表では答えられない問いが一つ残ります — **先月あなたはいくら払い、そのうち送り直しに費やしたコンテキストはどれだけでしたか?** 返信欄はあちらのページにあります。ここにはありません。

## まず数字から

以下の行は**英語の原文そのまま**で、翻訳していません。数字は元の一文から切り離すと検証できないからです —— `$1.43` が 100 万トークンあたりなのか、月額なのか、1 席あたりなのかは、その一文にしか書かれていません。

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$30` | It started as $30 a month, was raised to $60 in "Phase 2", and was kept long-term. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> But dollars of quota are not tokens. | [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1 <!-- [doc_41a4c25e26655d9dc1ddafedda28748b] -->. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |
| `$7,600` | An AI crypto trading bot reportedly made $7,600 in a week.” That line gets clicks. | [How a Multi-Agent AI System Made $7,600 in 7 Days for Under $100 in API Costs](articles/how-a-multi-agent-ai-system-made-7-600-in-7-days-for-under.md) |
| `$5` | The tool runs on a $5/month VPS using Docker. | [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](articles/how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md) |
| `$0.028` | With DeepSeek V4 Flash priced at just $0.028 per million tokens, developers can assign lightweight tasks like boilerplate generation or syntax checking to this model, reserving higher-cost models for nuanced logic or debugging. | [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md) |
| `40%` | 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. | [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md) |
| `$1.43` | The price spread is wide even among the Western flagships, which becomes obvious on ReactBench, where one run with GPT 5.6 Sol costs about $1.43 while one run with Fable 5 costs $9.05, which means that a single Fable 5 run comes to a bit more than six times as much as the GPT 5.6 Sol run does. | [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) |
| `20%` | I’d argue that building these decoupling layers is the only way to survive the shift toward platforms like ChatGPT Work, where non-programming users are expected to jump from 20% to 60% of the total user base within a year. | [Four Circuit Breakers Every Unattended AI Pipeline Needs (Learned the Expensive Way)](articles/four-circuit-breakers-every-unattended-ai-pipeline-needs.md) |
| `$170,000` | In contrast to one-off projects, micro-automation tools excel at addressing single, high-frequency pain points A former Alibaba P8, after facing three months of unsuccessful job applications, pivoted to building AI software that has five core features—including scheduled automation and skill packages—to generate $170,000 in monthly revenue The data from these 27 successful cases reveals that the most effective tools prioritize "scheduled automation," which can reduce manual task time from several hours each day to zero minutes. | [Stop Building Custom AI Agents: How to Earn $63K/Month with Micro-Automation](articles/stop-building-custom-ai-agents-how-to-earn-63k-month-with.md) |
| `80%` | The machine runs for about 11 minutes, and human review takes 10–20 minutes, leading to a total time reduction of ~80%–90%. | [I built a WeChat Official Account writing Agent that cuts work time by 80% — here’s the workflow filter and tool combo I used](articles/i-built-a-wechat-official-account-writing-agent-that-cuts.md) |

[全 731 行](figures.md)

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
