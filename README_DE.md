# Was KI-Coding-Agenten wirklich kosten: 478 Zahlen, jede mit ihrem Satz und ihrem Datum

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · **Deutsch** · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Ein offener Datensatz. Jede Zahl aus 53 Praxisnotizen — Preise, Prozentsätze, Vielfache, Token-Zahlen und Laufzeiten — als eigene Zeile, **mit dem vollständigen Satz, aus dem sie stammt, und dem Veröffentlichungsdatum**.

## Was Agent-Modelle heute kosten

60 Modelle, die in einer *agents*-Kategorie der Design Arena platziert sind, mit ihrem **Listenpreis** pro Million Token — nicht Ihre Rechnung: Cache, Batch und jeder Anbieter rechnen anders ab. Aus dem öffentlichen Katalog von OpenRouter, zuletzt gelesen am 2026-08-23. Die drei günstigsten:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #2 agenticgamedev |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Alle 60 Modelle](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Eine Zahl, zwei Antworten.** Google und xAI wechseln beide bei 200,000 Eingabe-Tokens in den teureren Tarif — ein Prompt von genau 200,000 wird bei Google jedoch zum günstigen und bei xAI zum teuren Tarif abgerechnet. Andere Tabellen drucken die Zahl und hören dort auf. Wer auf welcher Seite abrechnet, im Originalzitat von der Herstellerseite mit Prüfdatum: [same number, opposite answer](prices.md#same-number-opposite-answer) (englisch).

**Die Tabelle oben ist ein Listenpreis. Keine Rechnung stimmt damit überein.** Was die Zahl bewegt, sind Cache-Treffer, Wiederholungen und Kontext, den man zweimal bezahlt — nichts davon kann ein Katalog zeigen. Ein Beitrag ist genau dieser Lücke nachgegangen: [wohin die Token-Rechnung wirklich geht](https://github.com/xyzs996/llm-api-pricing/discussions/37). Er endet mit der einen Frage, die die Tabelle nicht beantworten kann: **Was haben Sie letzten Monat bezahlt, und wie viel davon war Kontext, den erneut zu senden Sie geärgert hat?** Diese Seite hat ein Antwortfeld; diese hier nicht.

## Zuerst die Zahlen

Die folgenden Zeilen stehen **wörtlich auf Englisch** und sind nicht übersetzt: Eine Zahl ohne ihren Satz ist nicht überprüfbar — `$1.43` kann pro Million Token, pro Monat oder pro Platz bedeuten.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$0.81` | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. | [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) |
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

[Alle 478 Zeilen](figures.md)

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
