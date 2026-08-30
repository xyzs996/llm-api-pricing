# Ce que coûtent réellement les agents de code IA : 500 chiffres, chacun avec sa phrase et sa date

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · **Français** · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un jeu de données ouvert. Chaque chiffre publié dans 54 notes de terrain — prix, pourcentages, multiples, nombres de tokens et durées — extrait en une ligne, **avec la phrase entière dont il provient et sa date de publication**.

## Ce que coûtent aujourd'hui les modèles d'agent

56 modèles classés dans une catégorie *agents* de la Design Arena, avec leur **prix affiché** par million de jetons — ce n'est pas votre facture : le cache, les lots et chaque fournisseur facturent différemment. Depuis le catalogue public de OpenRouter, relu le 2026-08-30. Les trois moins chers :

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #4 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Les 56 modèles](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un seul nombre, deux réponses.** Google et xAI passent tous deux au tarif élevé à 200,000 tokens d'entrée, mais un prompt d'exactement 200,000 est facturé au tarif bas chez Google et au tarif élevé chez xAI. Les autres tableaux impriment le nombre et s'arrêtent là. De quel côté chacun facture, cité de sa propre page avec la date de consultation : [same number, opposite answer](prices.md#same-number-opposite-answer) (en anglais).

**Le tableau ci-dessus est un prix catalogue. Aucune facture n'y correspond.** Ce qui déplace le chiffre, ce sont les caches touchés, les reprises et le contexte payé deux fois — rien de tout cela n'apparaît dans un catalogue. Un article est allé chercher cet écart : [où part vraiment la facture de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Il se termine sur la seule question à laquelle le tableau ne peut pas répondre : **combien avez-vous payé le mois dernier, et quelle part était du contexte que cela vous a coûté de renvoyer ?** Cette page-là a un champ de réponse ; celle-ci non.

## Les chiffres d'abord

Les lignes ci-dessous sont **en anglais, recopiées telles quelles**, sans traduction : un chiffre séparé de sa phrase n'est pas vérifiable — `$1.43` peut être par million de tokens, par mois ou par utilisateur.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$35M` | Respond.io crossed $35M in annual recurring revenue last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to per-customer billing — made the difference between flat growth and explosive scale. | [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md) |
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

[Les 500 lignes](figures.md)

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
