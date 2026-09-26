# Ce que coûtent réellement les agents de code IA : 622 chiffres, chacun avec sa phrase et sa date

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · **Français** · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un jeu de données ouvert. Chaque chiffre publié dans 67 notes de terrain — prix, pourcentages, multiples, nombres de tokens et durées — extrait en une ligne, **avec la phrase entière dont il provient et sa date de publication**.

## Ce que coûtent aujourd'hui les modèles d'agent

65 modèles classés dans une catégorie *agents* de la Design Arena, avec leur **prix affiché** par million de jetons — ce n'est pas votre facture : le cache, les lots et chaque fournisseur facturent différemment. Depuis le catalogue public de OpenRouter, relu le 2026-09-26. Les trois moins chers :

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.09 | $0.36 | Solar Pro 4 | #34 webapps |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #8 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #12 htmlslides |

[Les 65 modèles](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un seul nombre, deux réponses.** Google et xAI passent tous deux au tarif élevé à 200,000 tokens d'entrée, mais un prompt d'exactement 200,000 est facturé au tarif bas chez Google et au tarif élevé chez xAI. Les autres tableaux impriment le nombre et s'arrêtent là. De quel côté chacun facture, cité de sa propre page avec la date de consultation : [same number, opposite answer](prices.md#same-number-opposite-answer) (en anglais).

**Le tableau ci-dessus est un prix catalogue. Aucune facture n'y correspond.** Ce qui déplace le chiffre, ce sont les caches touchés, les reprises et le contexte payé deux fois — rien de tout cela n'apparaît dans un catalogue. Un article est allé chercher cet écart : [où part vraiment la facture de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Il se termine sur la seule question à laquelle le tableau ne peut pas répondre : **combien avez-vous payé le mois dernier, et quelle part était du contexte que cela vous a coûté de renvoyer ?** Cette page-là a un champ de réponse ; celle-ci non.

## Les chiffres d'abord

Les lignes ci-dessous sont **en anglais, recopiées telles quelles**, sans traduction : un chiffre séparé de sa phrase n'est pas vérifiable — `$1.43` peut être par million de tokens, par mois ou par utilisateur.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `40%` | 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. | [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md) |
| `$1.43` | The price spread is wide even among the Western flagships, which becomes obvious on ReactBench, where one run with GPT 5.6 Sol costs about $1.43 while one run with Fable 5 costs $9.05, which means that a single Fable 5 run comes to a bit more than six times as much as the GPT 5.6 Sol run does. | [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) |
| `20%` | I’d argue that building these decoupling layers is the only way to survive the shift toward platforms like ChatGPT Work, where non-programming users are expected to jump from 20% to 60% of the total user base within a year. | [Four Circuit Breakers Every Unattended AI Pipeline Needs (Learned the Expensive Way)](articles/four-circuit-breakers-every-unattended-ai-pipeline-needs.md) |
| `$170,000` | In contrast to one-off projects, micro-automation tools excel at addressing single, high-frequency pain points A former Alibaba P8, after facing three months of unsuccessful job applications, pivoted to building AI software that has five core features—including scheduled automation and skill packages—to generate $170,000 in monthly revenue The data from these 27 successful cases reveals that the most effective tools prioritize "scheduled automation," which can reduce manual task time from several hours each day to zero minutes. | [Stop Building Custom AI Agents: How to Earn $63K/Month with Micro-Automation](articles/stop-building-custom-ai-agents-how-to-earn-63k-month-with.md) |
| `80%` | The machine runs for about 11 minutes, and human review takes 10–20 minutes, leading to a total time reduction of ~80%–90%. | [I built a WeChat Official Account writing Agent that cuts work time by 80% — here’s the workflow filter and tool combo I used](articles/i-built-a-wechat-official-account-writing-agent-that-cuts.md) |
| `54%` | Through its internal multi-agent system, Sol achieves 54% higher token efficiency on agentic coding tasks compared to peer models, showing how strategic design choices can transform from a development challenge into a cost-saving advantage. | [The Hidden Costs of Over-Prompting in AI Coding: Lessons from Claude Code's Optimization](articles/the-hidden-costs-of-over-prompting-in-ai-coding-lessons.md) |
| `$10` | An AI image generation tool used Google Ads to boost its monthly paying subscribers from approximately 80 to over 500, maintaining a customer acquisition cost of around $10 per paying user. | [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md) |
| `$1.43` | One GPT-5.6 Sol run might cost $1.43, while other models could cost upwards of $9.00 for the same task. | [Claude Code Can Model a Flange but Not a Freeform Surface: A Six-Step Handoff Checklist for Non-Code Agent Output](articles/claude-code-can-model-a-flange-but-not-a-freeform-surface-a.md) |
| `$63,000,` | Consider Jordan, who noticed his partner spending hours manually sharing items on Poshmark, and by developing a simple 30-line JavaScript automation script to solve this pain point, he created Resellbot, which eventually scaled to a monthly revenue of $63,000, while this progression highlights how identifying such tedious manual tasks can serve as a potent foundation for building highly profitable and scalable software solutions. | [Building High-Income Single-Page Tool Sites via SEO](articles/building-high-income-single-page-tool-sites-via-seo.md) |
| `70%` | In that WeChat publication, 70% of the solo workflow was repetitive: organizing source material, checking drafts for AI-sounding prose, making covers, converting to HTML layout and publishing. | [How to Turn the Workflows You Won't Document Into Agent Skills](articles/how-to-turn-the-workflows-you-won-t-document-into-agent.md) |
| `72%` | Mobile developers report 72% of AI-generated code fails initial verification on real devices, and frontend developers waste 45% of their time debugging visual inconsistencies that only appear in production. | [The Real Pitfalls of AI Agent Development: From Code Generation to Functional Verification](articles/the-real-pitfalls-of-ai-agent-development-from-code.md) |
| `60%` | The recruitment automation tool hit a 60% efficiency gain after 28 rounds of iteration, but I’d argue that figure glosses over the real cost: dynamic page elements like shifting button positions and pop-ups demanded extra layers for state recognition and result verification. | [The AI Automation Ceiling: Why 60% Efficiency Doesn't Equal 20% Conversion](articles/the-ai-automation-ceiling-why-60-efficiency-doesn-t-equal.md) |

[Les 622 lignes](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Le champ `published` est le jour où cette note est parue, **pas le jour où ce prix était en vigueur**. Les prix bougent : lisez chaque ligne à sa propre date.

## Les textes

Les textes sont **en anglais**, ici : https://xyzs996.github.io/llm-api-pricing/ — avec le tableau des chiffres, les pages par thème et les pages par fournisseur. Si vous ne voulez que les données, les deux `curl` ci-dessus suffisent.

## Dites quelque chose

- **Mettez une étoile** pour suivre les mises à jour. Les données sont en CC BY : l'étoile ne change rien à ce que vous pouvez en faire. Ce qu'elle change, c'est si **la prochaine personne qui cherche ces chiffres** les trouve : GitHub tient compte du nombre d'étoiles dans le classement des résultats et dans les dépôts qu'il suggère à côté.
- **Un chiffre est faux ?** Si un prix a changé, ou si votre propre mesure donne autre chose — ouvrez un issue. Ce dépôt est fait pour ça. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Un chiffre manque ?** Dites quelle métrique, quel fournisseur, quelle unité — en une ligne. Le formulaire a un seul champ obligatoire ; les demandes deviennent des lignes. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0 : copiez, republiez, dérivez, vendez. Une seule condition : dire d'où cela vient, un lien vers https://xyzs996.github.io/llm-api-pricing/ suffit.
