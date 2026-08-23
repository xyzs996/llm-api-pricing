# Ce que coûtent réellement les agents de code IA : 341 chiffres, chacun avec sa phrase et sa date

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · **Français** · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un jeu de données ouvert. Chaque chiffre publié dans 35 notes de terrain — prix, pourcentages, multiples, nombres de tokens et durées — extrait en une ligne, **avec la phrase entière dont il provient et sa date de publication**.

## Ce que coûtent aujourd'hui les modèles d'agent

60 modèles classés dans une catégorie *agents* de la Design Arena, avec leur **prix affiché** par million de jetons — ce n'est pas votre facture : le cache, les lots et chaque fournisseur facturent différemment. Depuis le catalogue public de OpenRouter, relu le 2026-08-22. Les trois moins chers :

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #3 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Les 60 modèles](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un seul nombre, deux réponses.** Google et xAI passent tous deux au tarif élevé à 200,000 tokens d'entrée, mais un prompt d'exactement 200,000 est facturé au tarif bas chez Google et au tarif élevé chez xAI. Les autres tableaux impriment le nombre et s'arrêtent là. De quel côté chacun facture, cité de sa propre page avec la date de consultation : [same number, opposite answer](prices.md#same-number-opposite-answer) (en anglais).

**Le tableau ci-dessus est un prix catalogue. Aucune facture n'y correspond.** Ce qui déplace le chiffre, ce sont les caches touchés, les reprises et le contexte payé deux fois — rien de tout cela n'apparaît dans un catalogue. Un article est allé chercher cet écart : [où part vraiment la facture de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Il se termine sur la seule question à laquelle le tableau ne peut pas répondre : **combien avez-vous payé le mois dernier, et quelle part était du contexte que cela vous a coûté de renvoyer ?** Cette page-là a un champ de réponse ; celle-ci non.

## Les chiffres d'abord

Les lignes ci-dessous sont **en anglais, recopiées telles quelles**, sans traduction : un chiffre séparé de sa phrase n'est pas vérifiable — `$1.43` peut être par million de tokens, par mois ou par utilisateur.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Office Automation with Claude Code and Codex](articles/office-automation-with-claude-code-and-codex.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |
| `90%` | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. | [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md) |
| `80%` | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. | [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) |
| `$30` | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. | [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.md) |
| `$1,000` | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. | [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](articles/how-indie-developers-are-building-ai-powered-digital.md) |
| `40-second` | When an independent developer uses Agency Agents to set up a 40-second response cycle for e-commerce listings, they are building a feedback loop that reads market conditions and adjusts, which is what separates a timed automation from a script on a timer. | [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.md) |
| `9.1%` | One reported case moved entry-group conversion from 9.1% to 55.1% by rebuilding an automated onboarding flow around what the funnel data actually showed, rather than around what the team assumed users were doing. | [Boosting AI Bot Conversion: A Deep Dive into Funnel Data](articles/boosting-ai-bot-conversion-a-deep-dive-into-funnel-data.md) |
| `$1.25` | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. | [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.md) |

[Les 341 lignes](figures.md)

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
