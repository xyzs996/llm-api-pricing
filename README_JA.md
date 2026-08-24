# AI コーディングエージェントの実際の料金:429 行、どの行にも出典の一文と日付つき

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · **日本語** · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

オープンなデータセットです。52 本の実測ノートに出てきた数字 —— 料金、割合、倍率、トークン数、所要時間 —— をすべて 1 行ずつに抜き出し、**元の一文と公開日を必ず添えて**あります。

## エージェント向けモデルの今日の値段

Design Arena の *agents* 部門で順位のついた 60 モデルの、100 万トークンあたりの**定価**です。請求額ではありません — キャッシュ、バッチ、提供元ごとに価格は違います。OpenRouter の公開カタログより、最終取得日 2026-08-23。安い順に 3 つ:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #2 agenticgamedev |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[60 モデル全部](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**同じ数字、逆の答え。** Google と xAI はどちらも入力 200,000 トークンで高い方の料金に切り替わります。ただし**ちょうど** 200,000 のとき、Google は安い方、xAI は高い方で課金されます。ほかの価格表は境界の数字を載せてそこで終わりです。どちらに入るかを、各社の公式ページの原文と確認日つきで: [same number, opposite answer](prices.md#same-number-opposite-answer)(英語)。

**上の表は定価であって、これと一致する請求書は一つもありません。**数字を動かすのはキャッシュヒット、リトライ、そして二度払って送り直すコンテキストで、そのどれもカタログには写りません。その差を追いかけた記事があります:[トークン代は実際どこへ消えるのか](https://github.com/xyzs996/llm-api-pricing/discussions/37)。最後に、この表では答えられない問いが一つ残ります — **先月あなたはいくら払い、そのうち送り直しに費やしたコンテキストはどれだけでしたか?** 返信欄はあちらのページにあります。ここにはありません。

## まず数字から

以下の行は**英語の原文そのまま**で、翻訳していません。数字は元の一文から切り離すと検証できないからです —— `$1.43` が 100 万トークンあたりなのか、月額なのか、1 席あたりなのかは、その一文にしか書かれていません。

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
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
| `90%` | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. | [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md) |
| `80%` | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. | [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) |

[全 429 行](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

`published` はそのノートを公開した日で、**その料金が有効だった日ではありません**。料金は動きます。各行はその行自身の日付で読んでください。

## 本文

本文は**英語**です:https://xyzs996.github.io/llm-api-pricing/ —— 数値表、トピック別ページ、ベンダー別ページがあります。数字だけでよければ、上の `curl` 二本で足ります。

## ひとこと

- **このリポジトリにスターを**付けると更新を追えます。データは CC BY なので、スターの有無でできることは変わりません。変わるのは、**次の人がこの数字にたどり着ける**かどうかです。GitHub は検索順位にも、関連リポジトリの表示にも、スター数を使っています。
- **数字が違う?** 料金が変わった、自分で測ったら別の数字になった —— issue を立ててください。このリポジトリはそのためにあります。 ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **欲しい数字がない?** どの指標を、どのベンダーの、どの単位で —— 一行で結構です。必須項目は一つだけ、届いたものは新しい行になります。 ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0:複製・再公開・加工・販売、自由です。条件は一つだけ、出典を示すこと。https://xyzs996.github.io/llm-api-pricing/ へのリンクで十分です。
