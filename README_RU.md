# Сколько на самом деле стоят ИИ-агенты для кода: 790 цифр, каждая со своей фразой и датой

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · **Русский** · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Открытый набор данных. Каждая цифра из 71 полевых заметок — цены, проценты, кратности, количество токенов и длительности — вынесена в отдельную строку, **вместе с полной фразой, откуда она взята, и датой публикации**.

## Сколько сегодня стоят модели для агентов

90 моделей, занявших место в одной из категорий *agents* на Design Arena, с **прейскурантной ценой** за миллион токенов — это не ваш счёт: кэш, пакетный режим и каждый провайдер считают по-своему. Из открытого каталога OpenRouter, последнее чтение 2026-11-14. Три самые дешёвые:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.007 | $6.80 | GLM 5.2 | #9 agenticgamedev |
| $0.038 | $0.50 | DeepSeek V4.1 Flash 1017 | #8 spreadsheet |
| $0.05 | $0.15 | DeepSeek V4.1 Flash 1017 `batch` | #8 spreadsheet |

[Все 90 моделей](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Одно число — два противоположных ответа.** Google и xAI переходят на дорогой тариф на 200,000 входных токенах, но запрос ровно в 200,000 токенов у Google считается по дешёвому тарифу, а у xAI — по дорогому. Остальные таблицы печатают это число и на этом останавливаются. Кто на какой стороне — с цитатой со страницы самого поставщика и датой проверки: [same number, opposite answer](prices.md#same-number-opposite-answer) (на английском).

**Таблица выше — это прейскурант. Ни один счёт с ним не совпадает.** Число двигают попадания в кэш, повторы и контекст, за отправку которого платят дважды, — ничего из этого каталог показать не может. Одна заметка пошла именно за этой разницей: [куда на самом деле уходит счёт за токены](https://github.com/xyzs996/llm-api-pricing/discussions/37). Она заканчивается единственным вопросом, на который таблица ответить не может: **сколько вы заплатили в прошлом месяце и какая часть этой суммы — контекст, который было жалко отправлять заново?** На той странице есть поле для ответа; на этой — нет.

## Сначала цифры

Строки ниже приведены **дословно по-английски**, без перевода: цифра в отрыве от своей фразы непроверяема — `$1.43` может быть за миллион токенов, за месяц или за одно рабочее место.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `60%` | For rider recruitment, this meant focusing on repetitive actions like resume browsing and initial outreach, which is where the team, using Codex, developed a tool that iterated 28 times before it was able to achieve a 60% efficiency increase in public domain recruitment tasks — the same repetitive work of resume browsing and initial outreach that had been the focus from the start. | [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](articles/the-hidden-cost-of-ai-automation-turning-human-instincts.md) |
| `$17` | Refero's Pro subscription is $17/month or $120/year, with commercial documents at $0.001 per request and a $2,000 minimum commitment. | [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) |
| `$80` | In one documented case, a developer spent roughly 4 hours of total human time over 5 days — reviewing, pivoting, and debugging — while an AI agent built the SaaS product, with API token costs for the entire build coming in at $80–120. <!-- [doc_78142061038fcf3b0dc3bc6300aa637e] --> For solo devs with coding experience, this compression of timeline scales even further for focused tools: a 4-year veteran developer used OpenCode (powered by Claude Sonnet 4.5) and 7 custom sub-agents to launch a code snippet sharing tool called CodeClip entirely from zero to production in approximately 4 hours, skipping weeks of setup, scaffolding, and initial feature drafting that would have been standard pre-AI. <!-- [doc_cc86eaf999acb3e8d528d41b7a56f392] --> This kind of speed shift creates entirely new testing ground for product ideas, allowing devs to validate a niche use case in a single weekend instead of burning through months of savings on a half-baked build. | [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md) |
| `$30` | It started as $30 a month, was raised to $60 in "Phase 2", and was kept long-term. <!-- [doc_aca61ff73451846f75e14d9e94317695] --> But dollars of quota are not tokens. | [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1 <!-- [doc_41a4c25e26655d9dc1ddafedda28748b] -->. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |
| `$7,600` | An AI crypto trading bot reportedly made $7,600 in a week.” That line gets clicks. | [How a Multi-Agent AI System Made $7,600 in 7 Days for Under $100 in API Costs](articles/how-a-multi-agent-ai-system-made-7-600-in-7-days-for-under.md) |
| `$5` | The tool runs on a $5/month VPS using Docker. | [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](articles/how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md) |
| `$0.028` | With DeepSeek V4 Flash priced at just $0.028 per million tokens, developers can assign lightweight tasks like boilerplate generation or syntax checking to this model, reserving higher-cost models for nuanced logic or debugging. | [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md) |
| `40%` | 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. | [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md) |
| `$1.43` | The price spread is wide even among the Western flagships, which becomes obvious on ReactBench, where one run with GPT 5.6 Sol costs about $1.43 while one run with Fable 5 costs $9.05, which means that a single Fable 5 run comes to a bit more than six times as much as the GPT 5.6 Sol run does. | [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) |

[Все 790 строк](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Поле `published` — это день выхода заметки, **а не день, когда эта цена действовала**. Цены меняются: читайте каждую строку на её собственную дату.

## Тексты

Тексты **на английском**, здесь: https://spectracodeai.com/ — с таблицей цифр, страницами по темам и по поставщикам. Если нужны только данные, хватит двух `curl` выше.

## Скажите своё

- **Поставьте звезду репозиторию**, чтобы следить за обновлениями. Данные под CC BY: звезда ничего не меняет в том, что вы можете с ними делать. Она меняет другое — **найдёт ли эти цифры следующий человек**, который будет их искать: GitHub учитывает число звёзд и в выдаче поиска, и в списке похожих репозиториев.
- **Цифра неверна?** Если цена изменилась или вы измерили сами и получили другое — откройте issue. Этот репозиторий ровно для этого. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Нужной цифры нет?** Напишите, какая метрика, какой поставщик, в каких единицах — одной строкой. В форме одно обязательное поле, а запросы становятся новыми строками. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: копируйте, перепубликуйте, перерабатывайте, продавайте. Единственное условие — указать источник, достаточно ссылки на https://spectracodeai.com/.
