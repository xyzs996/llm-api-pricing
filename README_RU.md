# Сколько на самом деле стоят ИИ-агенты для кода: 405 цифр, каждая со своей фразой и датой

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · **Русский** · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Открытый набор данных. Каждая цифра из 49 полевых заметок — цены, проценты, кратности, количество токенов и длительности — вынесена в отдельную строку, **вместе с полной фразой, откуда она взята, и датой публикации**.

## Сколько сегодня стоят модели для агентов

60 моделей, занявших место в одной из категорий *agents* на Design Arena, с **прейскурантной ценой** за миллион токенов — это не ваш счёт: кэш, пакетный режим и каждый провайдер считают по-своему. Из открытого каталога OpenRouter, последнее чтение 2026-08-22. Три самые дешёвые:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #3 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Все 60 моделей](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Одно число — два противоположных ответа.** Google и xAI переходят на дорогой тариф на 200,000 входных токенах, но запрос ровно в 200,000 токенов у Google считается по дешёвому тарифу, а у xAI — по дорогому. Остальные таблицы печатают это число и на этом останавливаются. Кто на какой стороне — с цитатой со страницы самого поставщика и датой проверки: [same number, opposite answer](prices.md#same-number-opposite-answer) (на английском).

**Таблица выше — это прейскурант. Ни один счёт с ним не совпадает.** Число двигают попадания в кэш, повторы и контекст, за отправку которого платят дважды, — ничего из этого каталог показать не может. Одна заметка пошла именно за этой разницей: [куда на самом деле уходит счёт за токены](https://github.com/xyzs996/llm-api-pricing/discussions/37). Она заканчивается единственным вопросом, на который таблица ответить не может: **сколько вы заплатили в прошлом месяце и какая часть этой суммы — контекст, который было жалко отправлять заново?** На той странице есть поле для ответа; на этой — нет.

## Сначала цифры

Строки ниже приведены **дословно по-английски**, без перевода: цифра в отрыве от своей фразы непроверяема — `$1.43` может быть за миллион токенов, за месяц или за одно рабочее место.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `20%` | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. | [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md) |
| `$22,000` | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. | [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Office Automation with Claude Code and Codex](articles/office-automation-with-claude-code-and-codex.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |
| `90%` | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. | [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md) |
| `80%` | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. | [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) |
| `$30` | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. | [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.md) |
| `$1,000` | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. | [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](articles/how-indie-developers-are-building-ai-powered-digital.md) |
| `40-second` | When an independent developer uses Agency Agents to set up a 40-second response cycle for e-commerce listings, they are building a feedback loop that reads market conditions and adjusts, which is what separates a timed automation from a script on a timer. | [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.md) |

[Все 405 строк](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Поле `published` — это день выхода заметки, **а не день, когда эта цена действовала**. Цены меняются: читайте каждую строку на её собственную дату.

## Тексты

Тексты **на английском**, здесь: https://xyzs996.github.io/llm-api-pricing/ — с таблицей цифр, страницами по темам и по поставщикам. Если нужны только данные, хватит двух `curl` выше.

## Скажите своё

- **Поставьте звезду репозиторию**, чтобы следить за обновлениями. Данные под CC BY: звезда ничего не меняет в том, что вы можете с ними делать. Она меняет другое — **найдёт ли эти цифры следующий человек**, который будет их искать: GitHub учитывает число звёзд и в выдаче поиска, и в списке похожих репозиториев.
- **Цифра неверна?** Если цена изменилась или вы измерили сами и получили другое — откройте issue. Этот репозиторий ровно для этого. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Нужной цифры нет?** Напишите, какая метрика, какой поставщик, в каких единицах — одной строкой. В форме одно обязательное поле, а запросы становятся новыми строками. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: копируйте, перепубликуйте, перерабатывайте, продавайте. Единственное условие — указать источник, достаточно ссылки на https://xyzs996.github.io/llm-api-pricing/.
