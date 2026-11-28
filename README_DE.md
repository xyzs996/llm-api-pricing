# Was KI-Coding-Agenten wirklich kosten: 999 Zahlen, jede mit ihrem Satz und ihrem Datum

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · **Deutsch** · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Ein offener Datensatz. Jede Zahl aus 81 Praxisnotizen — Preise, Prozentsätze, Vielfache, Token-Zahlen und Laufzeiten — als eigene Zeile, **mit dem vollständigen Satz, aus dem sie stammt, und dem Veröffentlichungsdatum**.

## Was Agent-Modelle heute kosten

110 Modelle, die in einer *agents*-Kategorie der Design Arena platziert sind, mit ihrem **Listenpreis** pro Million Token — nicht Ihre Rechnung: Cache, Batch und jeder Anbieter rechnen anders ab. Aus dem öffentlichen Katalog von OpenRouter, zuletzt gelesen am 2026-11-28. Die drei günstigsten:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #18 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #45 pdf |

[Alle 110 Modelle](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Eine Zahl, zwei Antworten.** Google und xAI wechseln beide bei 200,000 Eingabe-Tokens in den teureren Tarif — ein Prompt von genau 200,000 wird bei Google jedoch zum günstigen und bei xAI zum teuren Tarif abgerechnet. Andere Tabellen drucken die Zahl und hören dort auf. Wer auf welcher Seite abrechnet, im Originalzitat von der Herstellerseite mit Prüfdatum: [same number, opposite answer](prices.md#same-number-opposite-answer) (englisch).

**Die Tabelle oben ist ein Listenpreis. Keine Rechnung stimmt damit überein.** Was die Zahl bewegt, sind Cache-Treffer, Wiederholungen und Kontext, den man zweimal bezahlt — nichts davon kann ein Katalog zeigen. Ein Beitrag ist genau dieser Lücke nachgegangen: [wohin die Token-Rechnung wirklich geht](https://github.com/xyzs996/llm-api-pricing/discussions/37). Er endet mit der einen Frage, die die Tabelle nicht beantworten kann: **Was haben Sie letzten Monat bezahlt, und wie viel davon war Kontext, den erneut zu senden Sie geärgert hat?** Diese Seite hat ein Antwortfeld; diese hier nicht.

## Zuerst die Zahlen

Die folgenden Zeilen stehen **wörtlich auf Englisch** und sind nicht übersetzt: Eine Zahl ohne ihren Satz ist nicht überprüfbar — `$1.43` kann pro Million Token, pro Monat oder pro Platz bedeuten.

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

[Alle 999 Zeilen](figures.md)

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
