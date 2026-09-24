# Was KI-Coding-Agenten wirklich kosten: 565 Zahlen, jede mit ihrem Satz und ihrem Datum

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · **Deutsch** · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Ein offener Datensatz. Jede Zahl aus 62 Praxisnotizen — Preise, Prozentsätze, Vielfache, Token-Zahlen und Laufzeiten — als eigene Zeile, **mit dem vollständigen Satz, aus dem sie stammt, und dem Veröffentlichungsdatum**.

## Was Agent-Modelle heute kosten

65 Modelle, die in einer *agents*-Kategorie der Design Arena platziert sind, mit ihrem **Listenpreis** pro Million Token — nicht Ihre Rechnung: Cache, Batch und jeder Anbieter rechnen anders ab. Aus dem öffentlichen Katalog von OpenRouter, zuletzt gelesen am 2026-09-24. Die drei günstigsten:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.09 | $0.36 | Solar Pro 4 | #34 webapps |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #8 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #11 htmlslides |

[Alle 65 Modelle](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Eine Zahl, zwei Antworten.** Google und xAI wechseln beide bei 200,000 Eingabe-Tokens in den teureren Tarif — ein Prompt von genau 200,000 wird bei Google jedoch zum günstigen und bei xAI zum teuren Tarif abgerechnet. Andere Tabellen drucken die Zahl und hören dort auf. Wer auf welcher Seite abrechnet, im Originalzitat von der Herstellerseite mit Prüfdatum: [same number, opposite answer](prices.md#same-number-opposite-answer) (englisch).

**Die Tabelle oben ist ein Listenpreis. Keine Rechnung stimmt damit überein.** Was die Zahl bewegt, sind Cache-Treffer, Wiederholungen und Kontext, den man zweimal bezahlt — nichts davon kann ein Katalog zeigen. Ein Beitrag ist genau dieser Lücke nachgegangen: [wohin die Token-Rechnung wirklich geht](https://github.com/xyzs996/llm-api-pricing/discussions/37). Er endet mit der einen Frage, die die Tabelle nicht beantworten kann: **Was haben Sie letzten Monat bezahlt, und wie viel davon war Kontext, den erneut zu senden Sie geärgert hat?** Diese Seite hat ein Antwortfeld; diese hier nicht.

## Zuerst die Zahlen

Die folgenden Zeilen stehen **wörtlich auf Englisch** und sind nicht übersetzt: Eine Zahl ohne ihren Satz ist nicht überprüfbar — `$1.43` kann pro Million Token, pro Monat oder pro Platz bedeuten.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | I’d argue that building these decoupling layers is the only way to survive the shift toward platforms like ChatGPT Work, where non-programming users are expected to jump from 20% to 60% of the total user base within a year. | [Four Circuit Breakers Every Unattended AI Pipeline Needs (Learned the Expensive Way)](articles/four-circuit-breakers-every-unattended-ai-pipeline-needs.md) |
| `54%` | Through its internal multi-agent system, Sol achieves 54% higher token efficiency on agentic coding tasks compared to peer models, showing how strategic design choices can transform from a development challenge into a cost-saving advantage. | [The Hidden Costs of Over-Prompting in AI Coding: Lessons from Claude Code's Optimization](articles/the-hidden-costs-of-over-prompting-in-ai-coding-lessons.md) |
| `$10` | An AI image generation tool used Google Ads to boost its monthly paying subscribers from approximately 80 to over 500, maintaining a customer acquisition cost of around $10 per paying user. | [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md) |
| `$1.43` | One GPT-5.6 Sol run might cost $1.43, while other models could cost upwards of $9.00 for the same task. | [Claude Code Can Model a Flange but Not a Freeform Surface: A Six-Step Handoff Checklist for Non-Code Agent Output](articles/claude-code-can-model-a-flange-but-not-a-freeform-surface-a.md) |
| `70%` | In that WeChat publication, 70% of the solo workflow was repetitive: organizing source material, checking drafts for AI-sounding prose, making covers, converting to HTML layout and publishing. | [How to Turn the Workflows You Won't Document Into Agent Skills](articles/how-to-turn-the-workflows-you-won-t-document-into-agent.md) |
| `72%` | Mobile developers report 72% of AI-generated code fails initial verification on real devices, and frontend developers waste 45% of their time debugging visual inconsistencies that only appear in production. | [The Real Pitfalls of AI Agent Development: From Code Generation to Functional Verification](articles/the-real-pitfalls-of-ai-agent-development-from-code.md) |
| `60%` | The recruitment automation tool hit a 60% efficiency gain after 28 rounds of iteration, but I’d argue that figure glosses over the real cost: dynamic page elements like shifting button positions and pop-ups demanded extra layers for state recognition and result verification. | [The AI Automation Ceiling: Why 60% Efficiency Doesn't Equal 20% Conversion](articles/the-ai-automation-ceiling-why-60-efficiency-doesn-t-equal.md) |
| `$35M` | Respond.io crossed $35M in annual recurring revenue last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to per-customer billing — made the difference between flat growth and explosive scale. | [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md) |
| `$0.81` | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. | [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) |
| `$63,000` | Jordan's success with Resellbot, a Micro-SaaS that automates Poshmark sharing, is a notable example: he earns $63,000 a month with just 30 lines of JavaScript. | [Automating Short Video Marketing with AI: A Low-Cost Growth Strategy for Developers](articles/automating-short-video-marketing-with-ai-a-low-cost-growth.md) |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `$22,000` | The organic channel that produced $22,000 a month is running at roughly half the traffic a million-dollar year would need, and it took three months to get there. | [The $22K-a-Month AI Tool That Never Bought a Single Ad](articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.md) |

[Alle 565 Zeilen](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Das Feld `published` ist der Tag, an dem die Notiz erschien, **nicht der Tag, an dem dieser Preis galt**. Preise ändern sich — lesen Sie jede Zeile zu ihrem eigenen Datum.

## Die Texte

Die Texte sind **auf Englisch**, hier: https://xyzs996.github.io/llm-api-pricing/ — mit der Zahlentabelle, den Themenseiten und den Anbieterseiten. Wenn Sie nur die Daten wollen, genügen die beiden `curl` oben.

## Sagen Sie etwas

- **Markieren Sie das Repository mit einem Stern**, um Aktualisierungen zu folgen. Die Daten stehen unter CC BY: Der Stern ändert nichts daran, was Sie damit tun dürfen. Er ändert, ob **die nächste Person, die diese Zahlen sucht**, sie findet: GitHub gewichtet die Sternzahl in den Suchtreffern und in den Repositories, die es daneben vorschlägt.
- **Eine Zahl stimmt nicht?** Wenn ein Preis sich geändert hat oder Ihre eigene Messung etwas anderes ergibt — öffnen Sie ein Issue. Genau dafür ist dieses Repository da. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Eine Zahl fehlt?** Sagen Sie, welche Kennzahl, welcher Anbieter, welche Einheit — in einer Zeile. Das Formular hat genau ein Pflichtfeld; Anfragen werden zu neuen Zeilen. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: kopieren, weiterveröffentlichen, bearbeiten, verkaufen. Eine Bedingung: Sagen Sie, woher es stammt — ein Link auf https://xyzs996.github.io/llm-api-pricing/ genügt.
