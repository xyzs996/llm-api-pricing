# Сколько на самом деле стоят ИИ-агенты для кода: 901 цифр, каждая со своей фразой и датой

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · **Русский** · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Открытый набор данных. Каждая цифра из 76 полевых заметок — цены, проценты, кратности, количество токенов и длительности — вынесена в отдельную строку, **вместе с полной фразой, откуда она взята, и датой публикации**.

## Сколько сегодня стоят модели для агентов

110 моделей, занявших место в одной из категорий *agents* на Design Arena, с **прейскурантной ценой** за миллион токенов — это не ваш счёт: кэш, пакетный режим и каждый провайдер считают по-своему. Из открытого каталога OpenRouter, последнее чтение 2026-11-22. Три самые дешёвые:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #21 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #46 pdf |

[Все 110 моделей](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Одно число — два противоположных ответа.** Google и xAI переходят на дорогой тариф на 200,000 входных токенах, но запрос ровно в 200,000 токенов у Google считается по дешёвому тарифу, а у xAI — по дорогому. Остальные таблицы печатают это число и на этом останавливаются. Кто на какой стороне — с цитатой со страницы самого поставщика и датой проверки: [same number, opposite answer](prices.md#same-number-opposite-answer) (на английском).

**Таблица выше — это прейскурант. Ни один счёт с ним не совпадает.** Число двигают попадания в кэш, повторы и контекст, за отправку которого платят дважды, — ничего из этого каталог показать не может. Одна заметка пошла именно за этой разницей: [куда на самом деле уходит счёт за токены](https://github.com/xyzs996/llm-api-pricing/discussions/37). Она заканчивается единственным вопросом, на который таблица ответить не может: **сколько вы заплатили в прошлом месяце и какая часть этой суммы — контекст, который было жалко отправлять заново?** На той странице есть поле для ответа; на этой — нет.

## Сначала цифры

Строки ниже приведены **дословно по-английски**, без перевода: цифра в отрыве от своей фразы непроверяема — `$1.43` может быть за миллион токенов, за месяц или за одно рабочее место.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$3` | One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day. | [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md) |
| `$7` | One developer launched a SaaS and waited 2.5 months for the first paying customer, a $7 sale, and reported that the customer found the product through Google organic search. | [Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else](articles/your-channel-report-is-lying-1-215-of-1-463-branded-search.md) |
| `$3` | Another framing: Kimi K3 at $3/$15 per million tokens against Fable 5 at $10/$50, with intelligence index scores of 59.7 and 62.1. | [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md) |
| `$0.181` | Sources are already presenting $0.181 per successful task next to a coding score of 96.0, side by side, which is the shape the conversation is heading toward. | [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md) |
| `$3` | For scale on what a real month looks like: three agents doing email, calendar, and research ran about $3–5 per month on DeepSeek V4 Flash against $200–260 on Opus 4.7, with what the user described as a small quality gap. | [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md) |
| `60%` | For rider recruitment, this meant focusing on repetitive actions like resume browsing and initial outreach, which is where the team, using Codex, developed a tool that iterated 28 times before it was able to achieve a 60% efficiency increase in public domain recruitment tasks — the same repetitive work of resume browsing and initial outreach that had been the focus from the start. | [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](articles/the-hidden-cost-of-ai-automation-turning-human-instincts.md) |
| `$10` | OpenCode Go users pay $10/month and receive $60 of DeepSeek V4.1 Flash usage credit that never expires — up from the original $30/month allotment, upgraded in Phase 2 to $60 and kept long-term. | [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) |
| `$80` | In one documented case, a developer spent roughly 4 hours of total human time over 5 days — reviewing, pivoting, and debugging — while an AI agent built the SaaS product, with API token costs for the entire build coming in at $80–120. | [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md) |
| `$3` | The Reddit forecast was $3-5 a month for three light agents, and GLM-4-Flash's 20M free tokens don't expire, while DeepSeek's sign-up grant of 10M tokens (2026-05-02 article) was valid for only 30 days. | [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |

[Все 901 строк](figures.md)

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
