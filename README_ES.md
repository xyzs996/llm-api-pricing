# Cuánto cuestan de verdad los agentes de código con IA: 396 cifras, cada una con su frase y su fecha

[English](./README.md) · [中文](./README_CN.md) · **Español** · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un conjunto de datos abierto. Cada cifra publicada en 43 notas de campo — precios, porcentajes, múltiplos, recuentos de tokens y duraciones — extraída a una fila, **con la frase completa de la que salió y la fecha de publicación**.

## Lo que cuestan hoy los modelos de agente

60 modelos clasificados en alguna categoría *agents* de la Design Arena, con su **precio de lista** por millón de tokens — no es tu factura: la caché, los lotes y cada proveedor cobran distinto. Del catálogo público de OpenRouter, leído por última vez el 2026-08-22. Los tres más baratos:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #3 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Los 60 modelos](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un número, dos respuestas.** Google y xAI pasan a la tarifa alta a los 200,000 tokens de entrada, pero un prompt de exactamente 200,000 se cobra a la tarifa barata en Google y a la cara en xAI. Las demás tablas imprimen el número y ahí lo dejan. Qué lado aplica cada proveedor, citado de su propia página y con la fecha de consulta: [same number, opposite answer](prices.md#same-number-opposite-answer) (en inglés).

**La tabla de arriba es precio de lista. Ninguna factura coincide con ella.** Lo que mueve la cifra son los aciertos de caché, los reintentos y el contexto que pagas por enviar dos veces — nada de eso lo puede mostrar un catálogo. Un artículo fue a buscar esa diferencia: [adónde va de verdad la factura de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Termina con la única pregunta que la tabla no puede responder: **¿cuánto pagaste el mes pasado y qué parte era contexto que te dolió reenviar?** Esa página tiene caja de respuesta; esta no.

## Las cifras primero

Las líneas siguientes están **en inglés, copiadas tal cual**, sin traducir: una cifra sin su frase no se puede verificar — `$1.43` podría ser por millón de tokens, por mes o por puesto.

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

[Las 396 filas](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

El campo `published` es el día en que salió esa nota, **no el día en que ese precio estaba vigente**. Los precios cambian: lea cada fila según su propia fecha.

## Los textos

Los textos están **en inglés**, aquí: https://xyzs996.github.io/llm-api-pricing/ — con la tabla de cifras, las páginas por tema y las páginas por proveedor. Si solo quiere los datos, los dos `curl` de arriba bastan.

## Diga algo

- **Marque el repositorio con una estrella** para seguir las actualizaciones. Los datos son CC BY: la estrella no cambia nada de lo que puede hacer con ellos. Lo que sí cambia es si **la próxima persona que busque estas cifras** las encuentra: GitHub cuenta las estrellas al ordenar los resultados de búsqueda y al sugerir repositorios parecidos.
- **¿Una cifra está mal?** Si un precio cambió o usted midió otra cosa, abra un issue. Para eso existe este repositorio. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **¿Falta una cifra?** Diga qué métrica, qué proveedor y en qué unidad, en una línea — el formulario tiene un solo campo obligatorio y las peticiones se convierten en filas. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: copie, republique, derive o venda. Una sola condición: diga de dónde salió, con un enlace a https://xyzs996.github.io/llm-api-pricing/.
