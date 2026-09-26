# Cuánto cuestan de verdad los agentes de código con IA: 622 cifras, cada una con su frase y su fecha

[English](./README.md) · [中文](./README_CN.md) · **Español** · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Un conjunto de datos abierto. Cada cifra publicada en 67 notas de campo — precios, porcentajes, múltiplos, recuentos de tokens y duraciones — extraída a una fila, **con la frase completa de la que salió y la fecha de publicación**.

## Lo que cuestan hoy los modelos de agente

65 modelos clasificados en alguna categoría *agents* de la Design Arena, con su **precio de lista** por millón de tokens — no es tu factura: la caché, los lotes y cada proveedor cobran distinto. Del catálogo público de OpenRouter, leído por última vez el 2026-09-26. Los tres más baratos:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.09 | $0.36 | Solar Pro 4 | #34 webapps |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #8 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #12 htmlslides |

[Los 65 modelos](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Un número, dos respuestas.** Google y xAI pasan a la tarifa alta a los 200,000 tokens de entrada, pero un prompt de exactamente 200,000 se cobra a la tarifa barata en Google y a la cara en xAI. Las demás tablas imprimen el número y ahí lo dejan. Qué lado aplica cada proveedor, citado de su propia página y con la fecha de consulta: [same number, opposite answer](prices.md#same-number-opposite-answer) (en inglés).

**La tabla de arriba es precio de lista. Ninguna factura coincide con ella.** Lo que mueve la cifra son los aciertos de caché, los reintentos y el contexto que pagas por enviar dos veces — nada de eso lo puede mostrar un catálogo. Un artículo fue a buscar esa diferencia: [adónde va de verdad la factura de tokens](https://github.com/xyzs996/llm-api-pricing/discussions/37). Termina con la única pregunta que la tabla no puede responder: **¿cuánto pagaste el mes pasado y qué parte era contexto que te dolió reenviar?** Esa página tiene caja de respuesta; esta no.

## Las cifras primero

Las líneas siguientes están **en inglés, copiadas tal cual**, sin traducir: una cifra sin su frase no se puede verificar — `$1.43` podría ser por millón de tokens, por mes o por puesto.

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

[Las 622 filas](figures.md)

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
