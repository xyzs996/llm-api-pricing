# Was KI-Coding-Agenten wirklich kosten: 792 Zahlen, jede mit ihrem Satz und ihrem Datum

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · **Deutsch** · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Ein offener Datensatz. Jede Zahl aus 71 Praxisnotizen — Preise, Prozentsätze, Vielfache, Token-Zahlen und Laufzeiten — als eigene Zeile, **mit dem vollständigen Satz, aus dem sie stammt, und dem Veröffentlichungsdatum**.

## Was Agent-Modelle heute kosten

90 Modelle, die in einer *agents*-Kategorie der Design Arena platziert sind, mit ihrem **Listenpreis** pro Million Token — nicht Ihre Rechnung: Cache, Batch und jeder Anbieter rechnen anders ab. Aus dem öffentlichen Katalog von OpenRouter, zuletzt gelesen am 2026-11-14. Die drei günstigsten:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.007 | $6.80 | GLM 5.2 | #9 agenticgamedev |
| $0.038 | $0.50 | DeepSeek V4.1 Flash 1017 | #8 spreadsheet |
| $0.05 | $0.15 | DeepSeek V4.1 Flash 1017 `batch` | #8 spreadsheet |

[Alle 90 Modelle](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Eine Zahl, zwei Antworten.** Google und xAI wechseln beide bei 200,000 Eingabe-Tokens in den teureren Tarif — ein Prompt von genau 200,000 wird bei Google jedoch zum günstigen und bei xAI zum teuren Tarif abgerechnet. Andere Tabellen drucken die Zahl und hören dort auf. Wer auf welcher Seite abrechnet, im Originalzitat von der Herstellerseite mit Prüfdatum: [same number, opposite answer](prices.md#same-number-opposite-answer) (englisch).

**Die Tabelle oben ist ein Listenpreis. Keine Rechnung stimmt damit überein.** Was die Zahl bewegt, sind Cache-Treffer, Wiederholungen und Kontext, den man zweimal bezahlt — nichts davon kann ein Katalog zeigen. Ein Beitrag ist genau dieser Lücke nachgegangen: [wohin die Token-Rechnung wirklich geht](https://github.com/xyzs996/llm-api-pricing/discussions/37). Er endet mit der einen Frage, die die Tabelle nicht beantworten kann: **Was haben Sie letzten Monat bezahlt, und wie viel davon war Kontext, den erneut zu senden Sie geärgert hat?** Diese Seite hat ein Antwortfeld; diese hier nicht.

## Zuerst die Zahlen

Die folgenden Zeilen stehen **wörtlich auf Englisch** und sind nicht übersetzt: Eine Zahl ohne ihren Satz ist nicht überprüfbar — `$1.43` kann pro Million Token, pro Monat oder pro Platz bedeuten.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `60%` | For rider recruitment, this meant focusing on repetitive actions like resume browsing and initial outreach, which is where the team, using Codex, developed a tool that iterated 28 times before it was able to achieve a 60% efficiency increase in public domain recruitment tasks — the same repetitive work of resume browsing and initial outreach that had been the focus from the start. | [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](articles/the-hidden-cost-of-ai-automation-turning-human-instincts.md) |
| `$10` | OpenCode Go users pay $10/month and receive $60 of DeepSeek V4.1 Flash usage credit that never expires — up from the original $30/month allotment, upgraded in Phase 2 to $60 and kept long-term. | [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) |
| `$80` | In one documented case, a developer spent roughly 4 hours of total human time over 5 days — reviewing, pivoting, and debugging — while an AI agent built the SaaS product, with API token costs for the entire build coming in at $80–120. | [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md) |
| `$3` | The Reddit forecast was $3-5 a month for three light agents, and GLM-4-Flash's 20M free tokens don't expire, while DeepSeek's sign-up grant of 10M tokens (2026-05-02 article) was valid for only 30 days. | [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |
| `$7,600` | An AI crypto trading bot reportedly made $7,600 in a week.” That line gets clicks. | [How a Multi-Agent AI System Made $7,600 in 7 Days for Under $100 in API Costs](articles/how-a-multi-agent-ai-system-made-7-600-in-7-days-for-under.md) |
| `$5` | The tool runs on a $5/month VPS using Docker. | [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](articles/how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md) |
| `$0.028` | With DeepSeek V4 Flash priced at just $0.028 per million tokens, developers can assign lightweight tasks like boilerplate generation or syntax checking to this model, reserving higher-cost models for nuanced logic or debugging. | [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md) |
| `40%` | 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. | [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md) |
| `$1.43` | The price spread is wide even among the Western flagships, which becomes obvious on ReactBench, where one run with GPT 5.6 Sol costs about $1.43 while one run with Fable 5 costs $9.05, which means that a single Fable 5 run comes to a bit more than six times as much as the GPT 5.6 Sol run does. | [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) |

[Alle 792 Zeilen](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Das Feld `published` ist der Tag, an dem die Notiz erschien, **nicht der Tag, an dem dieser Preis galt**. Preise ändern sich — lesen Sie jede Zeile zu ihrem eigenen Datum.

## Die Texte

Die Texte sind **auf Englisch**, hier: https://spectracodeai.com/ — mit der Zahlentabelle, den Themenseiten und den Anbieterseiten. Wenn Sie nur die Daten wollen, genügen die beiden `curl` oben.

## Sagen Sie etwas

- **Markieren Sie das Repository mit einem Stern**, um Aktualisierungen zu folgen. Die Daten stehen unter CC BY: Der Stern ändert nichts daran, was Sie damit tun dürfen. Er ändert, ob **die nächste Person, die diese Zahlen sucht**, sie findet: GitHub gewichtet die Sternzahl in den Suchtreffern und in den Repositories, die es daneben vorschlägt.
- **Eine Zahl stimmt nicht?** Wenn ein Preis sich geändert hat oder Ihre eigene Messung etwas anderes ergibt — öffnen Sie ein Issue. Genau dafür ist dieses Repository da. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Eine Zahl fehlt?** Sagen Sie, welche Kennzahl, welcher Anbieter, welche Einheit — in einer Zeile. Das Formular hat genau ein Pflichtfeld; Anfragen werden zu neuen Zeilen. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: kopieren, weiterveröffentlichen, bearbeiten, verkaufen. Eine Bedingung: Sagen Sie, woher es stammt — ein Link auf https://spectracodeai.com/ genügt.
