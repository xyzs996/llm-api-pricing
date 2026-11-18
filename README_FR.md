# Ce que coûtent réellement les agents de code IA : 828 chiffres, chacun avec sa phrase et sa date

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · **Français** · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un jeu de données ouvert. Chaque chiffre publié dans 73 notes de terrain — prix, pourcentages, multiples, nombres de tokens et durées — extrait en une ligne, **avec la phrase entière dont il provient et sa date de publication**.

## Ce que coûtent aujourd'hui les modèles d'agent

103 modèles classés dans une catégorie *agents* de la Design Arena, avec leur **prix affiché** par million de jetons — ce n'est pas votre facture : le cache, les lots et chaque fournisseur facturent différemment. Depuis le catalogue public de OpenRouter, relu le 2026-11-18. Les trois moins chers :

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.007 | $6.80 | GLM 5.2 | #9 agenticgamedev |
| $0.036 | $0.15 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.036 | $0.50 | DeepSeek V4.1 Flash 1017 | #9 spreadsheet |

[Les 103 modèles](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un seul nombre, deux réponses.** Google et xAI passent tous deux au tarif élevé à 200,000 tokens d'entrée, mais un prompt d'exactement 200,000 est facturé au tarif bas chez Google et au tarif élevé chez xAI. Les autres tableaux impriment le nombre et s'arrêtent là. De quel côté chacun facture, cité de sa propre page avec la date de consultation : [same number, opposite answer](prices.md#same-number-opposite-answer) (en anglais).

**Le tableau ci-dessus est un prix catalogue. Aucune facture n'y correspond.** Ce qui déplace le chiffre, ce sont les caches touchés, les reprises et le contexte payé deux fois — rien de tout cela n'apparaît dans un catalogue. Un article est allé chercher cet écart : [où part vraiment la facture de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Il se termine sur la seule question à laquelle le tableau ne peut pas répondre : **combien avez-vous payé le mois dernier, et quelle part était du contexte que cela vous a coûté de renvoyer ?** Cette page-là a un champ de réponse ; celle-ci non.

## Les chiffres d'abord

Les lignes ci-dessous sont **en anglais, recopiées telles quelles**, sans traduction : un chiffre séparé de sa phrase n'est pas vérifiable — `$1.43` peut être par million de tokens, par mois ou par utilisateur.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$0.181` | Sources are already presenting $0.181 per successful task next to a coding score of 96.0, side by side, which is the shape the conversation is heading toward. | [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md) |
| `$3` | For scale on what a real month looks like: three agents doing email, calendar, and research ran about $3–5 per month on DeepSeek V4 Flash against $200–260 on Opus 4.7, with what the user described as a small quality gap. | [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md) |
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

[Les 828 lignes](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Le champ `published` est le jour où cette note est parue, **pas le jour où ce prix était en vigueur**. Les prix bougent : lisez chaque ligne à sa propre date.

## Les textes

Les textes sont **en anglais**, ici : https://spectracodeai.com/ — avec le tableau des chiffres, les pages par thème et les pages par fournisseur. Si vous ne voulez que les données, les deux `curl` ci-dessus suffisent.

## Dites quelque chose

- **Mettez une étoile** pour suivre les mises à jour. Les données sont en CC BY : l'étoile ne change rien à ce que vous pouvez en faire. Ce qu'elle change, c'est si **la prochaine personne qui cherche ces chiffres** les trouve : GitHub tient compte du nombre d'étoiles dans le classement des résultats et dans les dépôts qu'il suggère à côté.
- **Un chiffre est faux ?** Si un prix a changé, ou si votre propre mesure donne autre chose — ouvrez un issue. Ce dépôt est fait pour ça. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Un chiffre manque ?** Dites quelle métrique, quel fournisseur, quelle unité — en une ligne. Le formulaire a un seul champ obligatoire ; les demandes deviennent des lignes. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0 : copiez, republiez, dérivez, vendez. Une seule condition : dire d'où cela vient, un lien vers https://spectracodeai.com/ suffit.
