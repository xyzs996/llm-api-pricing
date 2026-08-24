# Every figure we published, with the sentence it came from

479 figures pulled out of 53 write-ups in
[llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — prices, percentages, multiples, token counts and durations, each
with the full sentence it appeared in and a link to the piece.

**Why the sentence is in the table.** A number on its own is not
checkable. `$1.43` could be per million tokens, per month, or per
seat. The sentence is quoted verbatim from the published piece, not
summarised, so you can judge it without taking our word for it.

**What `unit` means.** Prices are the one kind whose unit does not
live inside the figure — `60%` and `18 months` carry their own, `$20`
does not. Where the sentence states the unit right after the amount
(`$20/month`, `$0.19 per million tokens`) we lift those words out
verbatim into `unit`. A sentence that states the unit once and then
puts a second amount up against it (`$1.43 per run against $9.05`)
states it for both, so both rows carry it. We never infer one: if the
sentence does not say it, the field is empty. Empty means the piece
did not state a unit, not that we failed to record it.

**Machine-readable.**

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Fields: `value`, `kind` (`price` / `percent` / `multiple` / `tokens` / `duration`), `unit`, `context`, `article`, `published`, `url` (the copy on this site — no reply box), `medium` (published there first, empty if it never was), `thread` (same piece as a GitHub discussion, with a reply box).

**What `published` means.** It is the day the write-up carrying that
sentence went out — not the day the price or the percentage was in
force. We do not know the latter: the piece states a figure, it does
not date it. Model prices move fast, so read every row as of its own
date, and treat a two-month-old price as a lead rather than a quote.

**What `medium` means.** Some of these write-ups were published on
Medium first; for those rows this column holds the original, and the
headings below link to it. An empty cell means that piece was never
on Medium, not that we failed to look.

Served over jsDelivr, which caches `@main` for up to 12 hours —
the table is rebuilt at most once a day, so that is close enough.
Uncached origin: `https://xyzs996.github.io/llm-api-pricing/data/figures.json`.

**Want a figure that is not in here yet?** Say which metric,
which provider, which unit [in one line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=figures.md) —
one required field, and requests get turned into rows.

**Found one that is wrong or stale?** That is the point —
[open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new).

If this table saved you an afternoon,
[a star](https://github.com/xyzs996/llm-api-pricing) helps the next person
find it — the rows are CC BY and do not require one.

## [How Chinese AI Agent Tools Leverage 1.6 Billion Free Tokens](https://markyanai.medium.com/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens-69b483c4eb6a)

Published 2026-08-07. Originally published on Medium; [the copy here](https://xyzs996.github.io/llm-api-pricing/articles/how-chinese-ai-agent-tools-leverage-1-6-billion-free-tokens.html) carries the same sentences.

| Figure | Kind | In context |
| --- | --- | --- |
| `10,000 tokens` | tokens | This strategy revolves around using tools like OmniRoute, which aggregates 237 providers, compressing 10,000 tokens to 1080 through RTK+Caveman technology. |
| `$0.19` per million tokens | price | Chinese AI models provide a cost-effective alternative to their American counterparts, with input costs as low as $0.19 per million tokens, compared to OpenAI's $5-12. |
| `$5` per million tokens | price | Chinese AI models provide a cost-effective alternative to their American counterparts, with input costs as low as $0.19 per million tokens, compared to OpenAI's $5-12. |
| `$1` per million tokens | price | They are priced at $1 per million tokens, with a gross profit margin of 10% - 20%. |
| `10%` | percent | They are priced at $1 per million tokens, with a gross profit margin of 10% - 20%. |
| `20%` | percent | They are priced at $1 per million tokens, with a gross profit margin of 10% - 20%. |
| `10%` | percent | In contrast, top-tier American models only have a gross profit margin of 10% - 25% of that of these Chinese models, yet they still manage to maintain a positive gross profit. |
| `25%` | percent | In contrast, top-tier American models only have a gross profit margin of 10% - 25% of that of these Chinese models, yet they still manage to maintain a positive gross profit. |
| `$0.06` per million tokens | price | It offers a price range of $0.06-0.2 per million tokens, targeting global small and medium-sized enterprises and individual users. |
| `60%` | percent | An impressive 60% - 70% of its revenue comes from overseas, and the peak-time pricing mechanism boosts revenue further. |
| `70%` | percent | An impressive 60% - 70% of its revenue comes from overseas, and the peak-time pricing mechanism boosts revenue further. |
| `400-token` | tokens | Anthropic's 400-token SKILL.md file, through its "two-pass workflow" and specific aesthetic guidance, has achieved over 1 million installations, proving that aesthetic direction is more useful than mere tool innovation. |
| `80%` | percent | Claude Code's team discovered that removing 80% of system prompts actually improved programming performance, revealing how excessive model constraints can hinder rather than help AI effectiveness. |
| `20%` | percent | ChatGPT Work's user profile is projected to shift from 20% non-programmers to 60% within 12 months, showing its growing appeal across different professional backgrounds. |
| `60%` | percent | ChatGPT Work's user profile is projected to shift from 20% non-programmers to 60% within 12 months, showing its growing appeal across different professional backgrounds. |
| `12 months` | duration | ChatGPT Work's user profile is projected to shift from 20% non-programmers to 60% within 12 months, showing its growing appeal across different professional backgrounds. |
| `35%` | percent | The GNM Head tool, with its 636 adjustable parameters, enables real-time expression and posture control via MediaPipe, resulting in a 35% increase in user retention. |
| `5 minutes` | duration | The combination of WorkBuddy and BrowserAct allows developers to generate competitor price lists in just 5 minutes, proving useful for individual sellers and product selectors. |
| `35%` | percent | The ATOM camera system, tracking 34 key points and analyzing joint angles, provides more specific fitness feedback than existing applications, leading to a 35% increase in user retention. |

## [The Cost-Effective Guide to Using Open Code Review for AI Programming Tools](https://markyanai.medium.com/the-cost-effective-guide-to-using-open-code-review-for-ai-programming-tools-d144b9bb5b46)

Published 2026-08-10. Originally published on Medium; [the copy here](https://xyzs996.github.io/llm-api-pricing/articles/the-cost-effective-guide-to-using-open-code-review-for-ai.html) carries the same sentences.

| Figure | Kind | In context |
| --- | --- | --- |
| `95%` | percent | That 95% export-issue figure gets quoted everywhere. |
| `60%` | percent | It integrates with GitHub Actions and CircleCI, and its structured review comments cut false positives by 60% — which is the number I'd actually optimize for, because a review tool that cries wolf gets muted inside a week, and a muted tool reviews nothing at all while still showing green on every dashboard I own. |

## [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](https://xyzs996.github.io/llm-api-pricing/articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.html)

Published 2026-08-19.

| Figure | Kind | In context |
| --- | --- | --- |
| `10,000 tokens` | tokens | OmniRoute aggregates 237 providers and advertises roughly 1.6 billion free tokens a month, and that figure is arithmetic rather than a promotion, because the RTK+Caveman layer compresses 10,000 tokens down to 1,080, and a free quota multiplied by about 10 is exactly what a ratio like that buys you. |
| `54%` | percent | Sol is the heavy one, with a claimed 54% better token efficiency than models at the same level and an Ultra mode that runs 4 sub-agents in parallel. |
| `95%` | percent | Luna answers fastest, hits 95% accuracy on basic question answering, and costs the least per batch. |
| `$1.43` per run | price | One front-end benchmark put GPT-5.6 Sol at $1.43 per run against $9.05 for Fable 5. |
| `$9.05` per run | price | One front-end benchmark put GPT-5.6 Sol at $1.43 per run against $9.05 for Fable 5. |
| `6x` | multiple | A 6x spread on a single evaluation is the kind of gap that should decide your default long before a free quota does. |
| `2 hours 41 minutes 35 seconds` | duration | Sol's Ultra mode took 2 hours 41 minutes 35 seconds to build one detailed 3D scene, running its sub-agents in parallel the whole time, and a run of that length is not something a fallback can politely interrupt halfway through. |
| `24 hours` | duration | Sales staff using ChatGPT Work reportedly turned a CRM export into a technical proposal in 24 hours, work that had previously taken weeks, with something on the order of 70% of the time removed. |
| `70%` | percent | Sales staff using ChatGPT Work reportedly turned a CRM export into a technical proposal in 24 hours, work that had previously taken weeks, with something on the order of 70% of the time removed. |
| `20%` | percent | One projection has non-coding users going from 20% of that product's base to 60% within 12 months. |
| `60%` | percent | One projection has non-coding users going from 20% of that product's base to 60% within 12 months. |
| `12 months` | duration | One projection has non-coding users going from 20% of that product's base to 60% within 12 months. |
| `$1` per million tokens | price | Top-tier Chinese models such as GLM5.2 and DeepSeek V4 Pro sit near $1 per million tokens at inference gross margins of 10% to 20%. |
| `10%` | percent | Top-tier Chinese models such as GLM5.2 and DeepSeek V4 Pro sit near $1 per million tokens at inference gross margins of 10% to 20%. |
| `20%` | percent | Top-tier Chinese models such as GLM5.2 and DeepSeek V4 Pro sit near $1 per million tokens at inference gross margins of 10% to 20%. |
| `$0.06` per million | price | At the low end, MiniMax M3 runs $0.06 to $0.2 per million and draws 60% to 70% of its revenue from outside its home market. |
| `$0.2` per million | price | At the low end, MiniMax M3 runs $0.06 to $0.2 per million and draws 60% to 70% of its revenue from outside its home market. |
| `60%` | percent | At the low end, MiniMax M3 runs $0.06 to $0.2 per million and draws 60% to 70% of its revenue from outside its home market. |
| `70%` | percent | At the low end, MiniMax M3 runs $0.06 to $0.2 per million and draws 60% to 70% of its revenue from outside its home market. |
| `$0.06` per million | price | A spread from $0.06 to $1 per million is more than 16x, and peak pricing adds another factor of 2 on top, which means the decision of which tier to route to on a Tuesday afternoon moves your bill further than any free quota can. |
| `$1` per million | price | A spread from $0.06 to $1 per million is more than 16x, and peak pricing adds another factor of 2 on top, which means the decision of which tier to route to on a Tuesday afternoon moves your bill further than any free quota can. |
| `16x` | multiple | A spread from $0.06 to $1 per million is more than 16x, and peak pricing adds another factor of 2 on top, which means the decision of which tier to route to on a Tuesday afternoon moves your bill further than any free quota can. |
| `$1.25` per million | price | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. |
| `$4.25` per million | price | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. |
| `75%` | percent | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. |
| `83%` | percent | Meta priced Muse Spark 1.1 at $1.25 per million input and $4.25 per million output, roughly 75% and 83% below Anthropic's Opus, and the tradeoff is visible in the benchmarks, since it leads on MCP Atlas and JobBench while trailing on SWE-Bench Pro and DeepSWE 1.1. |
| `9x` | multiple | Nothing in a routing layer gets you a 9x reduction. |

## [58 Million Plays Started With One Account, Not Four](https://xyzs996.github.io/llm-api-pricing/articles/58-million-plays-started-with-one-account-not-four.html)

Published 2026-08-12.

| Figure | Kind | In context |
| --- | --- | --- |
| `95%` | percent | Across the 4 zero-budget cases in the source material, roughly 95% of users arrived through content rather than paid acquisition. |
| `15%` | percent | One published pipeline reports moving completion rates from a typical 15% to 20% band up past 60%, using competitor teardowns to set the target, a distilled voice to keep the output consistent, a de-AI pass on the fingerprints, and a quality gate that blocks anything below the bar from going out at all. |
| `20%` | percent | One published pipeline reports moving completion rates from a typical 15% to 20% band up past 60%, using competitor teardowns to set the target, a distilled voice to keep the output consistent, a de-AI pass on the fingerprints, and a quality gate that blocks anything below the bar from going out at all. |
| `60%` | percent | One published pipeline reports moving completion rates from a typical 15% to 20% band up past 60%, using competitor teardowns to set the target, a distilled voice to keep the output consistent, a de-AI pass on the fingerprints, and a quality gate that blocks anything below the bar from going out at all. |
| `3 months` | duration | StoryShort matched, in 3 months, the revenue that an established B2B tool took 2 years to build, with Stripe records showing about $22,000 a month and cumulative revenue approaching $500,000. |
| `2 years` | duration | StoryShort matched, in 3 months, the revenue that an established B2B tool took 2 years to build, with Stripe records showing about $22,000 a month and cumulative revenue approaching $500,000. |
| `$22,000` per month | price | StoryShort matched, in 3 months, the revenue that an established B2B tool took 2 years to build, with Stripe records showing about $22,000 a month and cumulative revenue approaching $500,000. |
| `$500,000` | price | StoryShort matched, in 3 months, the revenue that an established B2B tool took 2 years to build, with Stripe records showing about $22,000 a month and cumulative revenue approaching $500,000. |
| `$1.2 million` | price | It was later listed for sale at $1.2 million on a 4.4 times annual revenue multiple, after a 30-day stretch where revenue came in 11% below the previous 30 days. |
| `30-day` | duration | It was later listed for sale at $1.2 million on a 4.4 times annual revenue multiple, after a 30-day stretch where revenue came in 11% below the previous 30 days. |
| `11%` | percent | It was later listed for sale at $1.2 million on a 4.4 times annual revenue multiple, after a 30-day stretch where revenue came in 11% below the previous 30 days. |
| `30 days` | duration | It was later listed for sale at $1.2 million on a 4.4 times annual revenue multiple, after a 30-day stretch where revenue came in 11% below the previous 30 days. |
| `$63,000` per month | price | Jordan's Resellbot started as 30 lines of JavaScript written because his partner was manually reposting listings every day, and it now runs at roughly $63,000 a month, which probably says more about picking a visible problem than about any distribution tactic. |

## [A 30-Line Script, 200 Users, and a Niche Nobody Wanted](https://xyzs996.github.io/llm-api-pricing/articles/a-30-line-script-200-users-and-a-niche-nobody-wanted.html)

Published 2026-08-15.

| Figure | Kind | In context |
| --- | --- | --- |
| `$500` | price | Using AI tools to batch generate local SEO content reduces development costs for independent developers, accelerating website ranking on Google, after which the optimized site can be rented to local businesses for monthly revenue ranging from $500 to $3,000. |
| `$3,000` | price | Using AI tools to batch generate local SEO content reduces development costs for independent developers, accelerating website ranking on Google, after which the optimized site can be rented to local businesses for monthly revenue ranging from $500 to $3,000. |
| `5 minutes` | duration | WorkBuddy and BrowserAct combination allows sellers to generate a competitive pricing report in just 5 minutes. |
| `$10,000` | price | Sam Shore's experience with Typeshare, which shows how sharing equity with KOLs can accelerate growth, is a prime example; by granting three-fifths of his company's stock to two influential figures, he achieved a remarkable increase in monthly revenue, jumping from $10,000 to $15,000 in only 30 days. |
| `$15,000` | price | Sam Shore's experience with Typeshare, which shows how sharing equity with KOLs can accelerate growth, is a prime example; by granting three-fifths of his company's stock to two influential figures, he achieved a remarkable increase in monthly revenue, jumping from $10,000 to $15,000 in only 30 days. |
| `30 days` | duration | Sam Shore's experience with Typeshare, which shows how sharing equity with KOLs can accelerate growth, is a prime example; by granting three-fifths of his company's stock to two influential figures, he achieved a remarkable increase in monthly revenue, jumping from $10,000 to $15,000 in only 30 days. |
| `$150` | price | The math only works if you sell 18 products at $150 each, every day. |
| `$150` per product | price | Resellbot's pricing model at $150 per product aligns with industry benchmarks for automation tools, ensuring competitiveness in the Micro-SaaS market. |
| `$6.3K` per month | price | The $6.3K/month revenue shows that even with modest pricing, the tool captures meaningful demand in the Poshmark automation niche. |
| `18 months` | duration | Resellbot took 18 months to reach profitability. |
| `18-month` | duration | Sustainable growth in Micro-SaaS often requires patience and persistence, as seen with Resellbot's 18-month journey to profitability. |

## [AI Agent Loop Engineering: Karpathy's Method for 5x Productivity Gains](https://xyzs996.github.io/llm-api-pricing/articles/ai-agent-loop-engineering-karpathy-s-method-for-5x.html)

Published 2026-08-09.

| Figure | Kind | In context |
| --- | --- | --- |
| `5x` | multiple | A developer in China’s AI community achieved 5x productivity gains using loop engineering, reducing MVP development time from four prompt tuning sessions to a single command installation. |
| `74%` | percent | This method automates repetitive tasks and integrates complex workflows, as seen in Marvy 2.0’s 74% optimization efficiency improvement. |
| `5x` | multiple | Last week, a developer in the Chinese AI community shared groundbreaking results using "loop engineering" to boost AI agent efficiency by 5x. |
| `40 seconds` | duration | One implementation reduced average response times from hours to 40 seconds and increased transaction volumes by 50%, showing the tangible business benefits of loop engineering. |
| `50%` | percent | One implementation reduced average response times from hours to 40 seconds and increased transaction volumes by 50%, showing the tangible business benefits of loop engineering. |
| `74%` | percent | By consolidating market insight, media strategy, creative generation, smart deployment, and data analysis into a unified system, it achieved a 74% improvement in optimization efficiency and reduced manual labor by 89%. |
| `89%` | percent | By consolidating market insight, media strategy, creative generation, smart deployment, and data analysis into a unified system, it achieved a 74% improvement in optimization efficiency and reduced manual labor by 89%. |
| `89%` | percent | I don’t buy the 89% claim. |
| `8 hours` | duration | This system reduced manual processing time from 8 hours to minutes while improving content organization quality. |
| `20%` | percent | The retention rate improved from 20% to 35%, with natural search traffic accounting for 48% and user sessions making up 88% of the total. |
| `35%` | percent | The retention rate improved from 20% to 35%, with natural search traffic accounting for 48% and user sessions making up 88% of the total. |
| `48%` | percent | The retention rate improved from 20% to 35%, with natural search traffic accounting for 48% and user sessions making up 88% of the total. |
| `88%` | percent | The retention rate improved from 20% to 35%, with natural search traffic accounting for 48% and user sessions making up 88% of the total. |

## [AI Local Websites Don’t Rent for $3K/Month—Until You Do This](https://xyzs996.github.io/llm-api-pricing/articles/ai-local-websites-don-t-rent-for-3k-month-until-you-do-this.html)

Published 2026-08-10.

| Figure | Kind | In context |
| --- | --- | --- |
| `$500` per month | price | You can build AI-generated local business websites, rent them to plumbers or dentists for $500–$3,000 a month, and scale to passive income. |
| `$3,000` per month | price | You can build AI-generated local business websites, rent them to plumbers or dentists for $500–$3,000 a month, and scale to passive income. |
| `90%` | percent | The claim leaves out the gap: 90% of beginners quit during the first 90–180 days because traffic never arrives and the invoices never land. |
| `180 days` | duration | The claim leaves out the gap: 90% of beginners quit during the first 90–180 days because traffic never arrives and the invoices never land. |
| `$3,000` | price | High-ticket services in low-competition cities often sit at the $3,000 end for websites that actually deliver customers. |
| `$22,000` per month | price | Their Stripe records show $22,000 a month, proving that patience with organic strategies pays off. |
| `7 minutes` | duration | Similarly, WorkBuddy and BrowserAct can automate competitor price tracking and generate product opportunity reports in under 7 minutes — something to put in front of a skeptical client while the sandbox clock runs. |
| `90%` | percent | This approach has been validated by knowledge-based monetization experts, who emphasize that 90% of AI-generated articles fail due to low completion rates, but those using personality distillation and anti-AI fingerprinting techniques achieve 60%+ completion rates. |
| `60%` | percent | This approach has been validated by knowledge-based monetization experts, who emphasize that 90% of AI-generated articles fail due to low completion rates, but those using personality distillation and anti-AI fingerprinting techniques achieve 60%+ completion rates. |
| `$500` per month | price | The fastest documented case landed the first $500/month client at 12 weeks. |
| `12 weeks` | duration | The fastest documented case landed the first $500/month client at 12 weeks. |
| `$500` | price | If more than five paid ads appear above the organic results, the cost per lead will outstrip your $500–$3,000 margin. |
| `$3,000` | price | If more than five paid ads appear above the organic results, the cost per lead will outstrip your $500–$3,000 margin. |
| `$0` | price | Outreach: $0 if you send the emails yourself; a monthly fee once you automate with Lemlist |
| `2 hours` | duration | - Month 4+: 2 hours/week for maintenance |

## [AI Model Costs: Beyond Per-Token Pricing](https://xyzs996.github.io/llm-api-pricing/articles/ai-model-costs-beyond-per-token-pricing.html)

Published 2026-08-05.

| Figure | Kind | In context |
| --- | --- | --- |
| `60 percent` | percent | Microsoft's evaluation of Kimi K3 landed on a number that should change how you read a pricing page: about 60 percent of the cost difference between models comes from the thinking depth a task requires, not from the price per token. |
| `$1` per million | price | Here is what thinking depth costs in practice, why project context rather than generated code drives most of the bill, and what the $1-per-million tier tells you about where this market is heading. |
| `60 percent` | percent | Microsoft's testing puts that effect at roughly 60 percent of the observed cost spread, which makes it the dominant term and the unit price the correction. |
| `60 percent` | percent | A 60 percent price advantage measured on an isolated function can disappear entirely in a real repository, because the cheap model reads the same context the expensive one does and then needs another round to get it right. |
| `400 tokens` | tokens | Anthropic's SKILL.md file runs about 400 tokens, uses a two-pass approach with specific aesthetic guidance, and has passed 1.08 million installations. |
| `400-token` | tokens | A 400-token file at that install count is worth staring at for a moment, because it says the effective intervention was guidance rather than tooling, and it cost almost nothing per call to apply. |
| `$1` per million tokens | price | DeepSeek V4 Pro and GLM5.2 charge roughly $1 per million tokens and reportedly run at a 10 to 20 percent margin. |
| `20 percent` | percent | DeepSeek V4 Pro and GLM5.2 charge roughly $1 per million tokens and reportedly run at a 10 to 20 percent margin. |
| `900 million tokens` | tokens | MonkeyCode's free tier includes 900 million tokens, which is more than most competing coding tools offer and more than a solo developer working normally will exhaust. |
| `$19 billion` | price | Anthropic signed a data center lease reported at $19 billion, which is the kind of commitment that only makes sense if compute, not model architecture, is the constraint that decides who is still standing in five years. |
| `$1` | price | My reading, and I could be wrong about the timing, is that the $1 tier holds while that build-out is being financed and that the pressure surfaces later as capacity limits rather than as price rises. |
| `$19 billion` | price | Anthropic is not signing a $19 billion lease in order to cut prices in the next 12 months. |
| `12 months` | duration | Anthropic is not signing a $19 billion lease in order to cut prices in the next 12 months. |

## [AI Programming Tool Selection Strategy: From Rapid Prototyping to Long-term Collaboration](https://xyzs996.github.io/llm-api-pricing/articles/ai-programming-tool-selection-strategy-from-rapid.html)

Published 2026-08-07.

| Figure | Kind | In context |
| --- | --- | --- |
| `70%` | percent | Meanwhile ChatGPT Work saves non-technical staff up to 70% of their time on cross-application tasks, and those same people would get nothing out of an IDE. |
| `70%` | percent | They need the 70% time saving, and they need it without a repository. |
| `70%` | percent | The 70% figure is real for the finance analyst pulling numbers across four applications, and it is close to meaningless for the person maintaining a service, because their bottleneck was never the typing. |

## [AI Side Hustle: Stop Selling Hours, Start Selling Plans](https://xyzs996.github.io/llm-api-pricing/articles/ai-side-hustle-stop-selling-hours-start-selling-plans.html)

Published 2026-08-13.

| Figure | Kind | In context |
| --- | --- | --- |
| `20%` | percent | The efficiency target one operator set for themselves is specific and aggressive: compress delivery time to 20% of what it was. |
| `5 minutes` | duration | Pairing WorkBuddy with BrowserAct gets a competitor pricing table in roughly 5 minutes and a product-opportunity report in about 7; a free WorkBuddy account carries 100 credits a day against roughly 10 credits per complex task, which leaves room for around 10 research runs daily before money enters the conversation at all. |

## [AI Took Over My Coding. What Broke Was How I Learn.](https://xyzs996.github.io/llm-api-pricing/articles/ai-took-over-my-coding-what-broke-was-how-i-learn.html)

Published 2026-08-13.

| Figure | Kind | In context |
| --- | --- | --- |
| `$40 million` per year | price | Klarna replaced roughly 700 support agents with an AI assistant in early 2024, claimed about $40 million a year, and a bit over a year later the same CEO said they had overshot and started hiring back. |

## [Best Practices for AI Agent Skill Management](https://xyzs996.github.io/llm-api-pricing/articles/best-practices-for-ai-agent-skill-management.html)

Published 2026-08-21.

| Figure | Kind | In context |
| --- | --- | --- |
| `90%` | percent | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. |
| `80%` | percent | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. |
| `90 minutes` | duration | A developer reduced daily report creation from 90 minutes to 8 minutes by using Skill-MCP to automate data aggregation and formatting. |
| `8 minutes` | duration | A developer reduced daily report creation from 90 minutes to 8 minutes by using Skill-MCP to automate data aggregation and formatting. |
| `5 minutes` | duration | Tools like WorkBuddy + BrowserAct can expedite competitor analysis by extracting data to generate price tables in just 5 minutes and opportunity reports in 7 minutes. |
| `7 minutes` | duration | Tools like WorkBuddy + BrowserAct can expedite competitor analysis by extracting data to generate price tables in just 5 minutes and opportunity reports in 7 minutes. |
| `90 minutes` | duration | For example, developers using Skill-MCP reduced daily report generation time from 90 minutes to 8 minutes. |
| `8 minutes` | duration | For example, developers using Skill-MCP reduced daily report generation time from 90 minutes to 8 minutes. |
| `17-day` | duration | Transitioning from personal to enterprise account involves a 17-day process that includes subject migration, category completion, and dual-end true device payment verification, while the critical sequence—subject conversion, category supplementation, payment channel integration, and device verification—each step requiring specific audit procedures and material preparation, necessitates careful coordination to ensure compliance and operational continuity during the transition period, and For iOS platforms, separate verification is necessary due to distinct payment channels. |
| `90%` | percent | 90% of beginners fixate on tools (e.g., Pi's 4 default tools: read/write/edit/bash) instead of defining clear task boundaries. |
| `3x` | multiple | Example: A security team's bug bounty process improved 3x by adding context to Skill package, not just using new tools. |

## [Beyond Chat: How Codex Can Automate Your Word/Excel/PPT/PDF Workflows](https://xyzs996.github.io/llm-api-pricing/articles/beyond-chat-how-codex-can-automate-your-word-excel-ppt-pdf.html)

Published 2026-08-17.

| Figure | Kind | In context |
| --- | --- | --- |
| `70%` | percent | Codex's office automation capabilities, which are severely underestimated, can be transformed into powerful document processing agents, as shown by real-world developers, one of whom automated PDF data extraction to PPT report generation, cutting document processing time by 70%. |
| `2 hours` | duration | One developer processed 200 PDFs in 2 hours, a faster improvement in efficiency compared to the manual process, which would typically take 10 hours. |
| `10 hours` | duration | One developer processed 200 PDFs in 2 hours, a faster improvement in efficiency compared to the manual process, which would typically take 10 hours. |

## [Boosting AI Bot Conversion: A Deep Dive into Funnel Data](https://xyzs996.github.io/llm-api-pricing/articles/boosting-ai-bot-conversion-a-deep-dive-into-funnel-data.html)

Published 2026-08-19.

| Figure | Kind | In context |
| --- | --- | --- |
| `9.1%` | percent | One reported case moved entry-group conversion from 9.1% to 55.1% by rebuilding an automated onboarding flow around what the funnel data actually showed, rather than around what the team assumed users were doing. |
| `55.1%` | percent | One reported case moved entry-group conversion from 9.1% to 55.1% by rebuilding an automated onboarding flow around what the funnel data actually showed, rather than around what the team assumed users were doing. |
| `83.1%` | percent | Analyzing user behavior at each stage revealed the critical drop-off points, and the number that reframed the problem was this one: 83.1% of unmanaged groups contributed only 2.3% of new group entries. |
| `2.3%` | percent | Analyzing user behavior at each stage revealed the critical drop-off points, and the number that reframed the problem was this one: 83.1% of unmanaged groups contributed only 2.3% of new group entries. |
| `2.3%` | percent | The 2.3% is the weakest number in the set, and I'd treat it as directional rather than precise. |
| `48 hours` | duration | Setting the course price at 9.9 yuan tested one specific proposition, that people would pay for a simpler installation path, and produced 2 sales within 48 hours, for total revenue of 19.8 yuan. |
| `55.1%` | percent | The reported enterprise case reached 55.1% from 9.1% through exactly that loop: analyze the behaviour, change one stage, measure again. |
| `9.1%` | percent | The reported enterprise case reached 55.1% from 9.1% through exactly that loop: analyze the behaviour, change one stage, measure again. |

## [Charge Per Conversation, Not Per Seat: The Billing Model Behind AI Support](https://xyzs996.github.io/llm-api-pricing/articles/charge-per-conversation-not-per-seat-the-billing-model.html)

Published 2026-08-15.

| Figure | Kind | In context |
| --- | --- | --- |
| `3 months` | duration | A former Alibaba P8 engineer, laid off and 3 months into an unsuccessful job search, ended up running three separate AI instances — one tracking competitor pricing, one generating ad creative, one handling customer service — and reports about 170,000 yuan a month. |

## [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](https://xyzs996.github.io/llm-api-pricing/articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.html)

Published 2026-08-24.

| Figure | Kind | In context |
| --- | --- | --- |
| `$0.81` per million input tokens | price | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. |
| `$2.00` per million input tokens | price | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. |
| `2.47x` | multiple | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. |
| `1.51x` | multiple | Reprice the same 40 at the token mix a coding agent actually produces and the gap falls to 1.51x. |
| `8.04 billion tokens` | tokens | The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output. |
| `95.64%` | percent | The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output. |
| `4.07%` | percent | The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output. |
| `0.29%` | percent | The mix in this table was measured over 8.04 billion tokens of one person's coding agent on 2026-05-16, and published openly: 95.64% cache reads, 4.07% cache misses, 0.29% output. |
| `$25` | price | Output, the price with the scariest sticker, the one at $25 or $50 per million, is under a third of one percent of the volume. |
| `$50` per million | price | Output, the price with the scariest sticker, the one at $25 or $50 per million, is under a third of one percent of the volume. |
| `$0.2015` | price | Reprice at that mix and the medians land at $0.2015 against $0.3046. |
| `$0.3046` | price | Reprice at that mix and the medians land at $0.2015 against $0.3046. |
| `1.51x` | multiple | A gap of 1.51x. |
| `10%` | percent | Anthropic, Google and OpenAI each charge 10% of input for a cache read. |
| `12%` | percent | Meta charges 12%. |
| `20%` | percent | The Chinese vendors mostly do not. z-ai charges 20% across six rows. |
| `20%` | percent | MiniMax charges 20%. |
| `16%` | percent | Qwen and Moonshot both sit near 16%, Moonshot spreading from 10% as far as 25%. |
| `10%` | percent | Qwen and Moonshot both sit near 16%, Moonshot spreading from 10% as far as 25%. |
| `25%` | percent | Qwen and Moonshot both sit near 16%, Moonshot spreading from 10% as far as 25%. |
| `96%` | percent | So a model that undercuts by half on the pricing page hands a third to a half of that back on the line carrying 96% of the traffic. |
| `8.3%` | percent | DeepSeek is the exception that proves the rule: 8.3%, better than anyone's flat ten. |
| `$1.475` per million | price | Qwen3.7 Max lists at $1.475 per million input. |
| `$2.00` | price | Claude Sonnet 5 lists at $2.00. |
| `26%` | percent | On the pricing page Qwen is 26% cheaper and the decision looks made. |
| `$355.00` | price | Run the billion tokens through: Qwen3.7 Max bills $355.00, Claude Sonnet 5 bills $301.68. |
| `$301.68` | price | Run the billion tokens through: Qwen3.7 Max bills $355.00, Claude Sonnet 5 bills $301.68. |
| `18%` | percent | The cheaper-looking model costs 18% more. |
| `20%` | percent | Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice. |
| `10%` | percent | Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice. |
| `96%` | percent | Qwen's cache read is 20% of its input where Anthropic's is 10%, and at 96% cache reads that ratio is the invoice. |
| `$3,000` | price | While we are here: budgeting a billion tokens at Kimi K3's list input predicts $3,000. |
| `$452.52` | price | The real figure is $452.52, an overestimate of 6.6x. |
| `6.6x` | multiple | The real figure is $452.52, an overestimate of 6.6x. |
| `$50` per million | price | A model at $50 per million output looks four times worse than one at $12.50. |
| `$12.50` | price | A model at $50 per million output looks four times worse than one at $12.50. |
| `0.29%` | percent | At 0.29% of volume that difference contributes almost nothing, while a cache read at 10% versus 20% of input moves the same bill by a third. |
| `10%` | percent | At 0.29% of volume that difference contributes almost nothing, while a cache read at 10% versus 20% of input moves the same bill by a third. |
| `20%` | percent | At 0.29% of volume that difference contributes almost nothing, while a cache read at 10% versus 20% of input moves the same bill by a third. |
| `$0.0566` | price | Gemini 3.7 Flash is the cheapest of the 40 at $0.0566 effective, and DeepSeek V4 Pro sits right next to it. |
| `$0.0501` | price | The 2026-08-23 read put DeepSeek at $0.0501, ahead of Gemini; the next day's read of the same catalogue is a third higher on input, output and cache read alike, which puts it at $0.0664, behind. |
| `$0.0664` | price | The 2026-08-23 read put DeepSeek at $0.0501, ahead of Gemini; the next day's read of the same catalogue is a third higher on input, output and cache read alike, which puts it at $0.0664, behind. |
| `1.3%` | percent | A second public catalogue agrees with the higher figure to within 1.3%, so the move is real rather than a bad scrape. |
| `$0.4525` | price | Kimi K3 prices at $0.4525 effective. |
| `1.58x` | multiple | Across the 18 batch rows the list gap is 1.58x and the effective gap is 0.98x, meaning the Chinese rows come out marginally more expensive. |
| `0.98x` | multiple | Across the 18 batch rows the list gap is 1.58x and the effective gap is 0.98x, meaning the Chinese rows come out marginally more expensive. |
| `200,000 tokens` | tokens | Twelve models also carry a second, higher price band past a context threshold, mostly at 200,000 tokens and 272,000 for GPT-5.4. |
| `300,000-token` | tokens | An agent routinely running a 300,000-token context is paying a different table than this one. |
| `80%` | percent | Push it down toward 80%, which short sessions and cold starts and a pile of new files will do, and the vendors with cheap cache reads lose their edge; the comparison drifts back toward the card price, and back toward the Chinese side. |
| `98%` | percent | Push it past 98%, which long runs on a stable repo will do, and the flat-ten vendors stretch further ahead. |

## [Choosing the Right AI Model for Coding: Cost vs. Efficiency](https://xyzs996.github.io/llm-api-pricing/articles/choosing-the-right-ai-model-for-coding-cost-vs-efficiency.html)

Published 2026-08-12.

| Figure | Kind | In context |
| --- | --- | --- |
| `$9.05` per run | price | Fable 5, the cheapest option at $9.05 per run, delivers only 41.2% accuracy in React projects. |
| `41.2%` | percent | Fable 5, the cheapest option at $9.05 per run, delivers only 41.2% accuracy in React projects. |
| `$1.43` per run | price | In contrast, GPT-5.6 Sol, at $1.43 per run, achieves 43.1% accuracy in the same tests, suggesting that while cheaper models may save money upfront, they often result in longer, more costly development processes. |
| `43.1%` | percent | In contrast, GPT-5.6 Sol, at $1.43 per run, achieves 43.1% accuracy in the same tests, suggesting that while cheaper models may save money upfront, they often result in longer, more costly development processes. |
| `$9.05` per run | price | The most affordable AI model option, Fable 5, costs just $9.05 per run, but delivers only 41.2% accuracy in React projects. |
| `41.2%` | percent | The most affordable AI model option, Fable 5, costs just $9.05 per run, but delivers only 41.2% accuracy in React projects. |
| `$1.43` per run | price | For instance, GPT-5.6 Sol, while more expensive at $1.43 per run, shows superior performance with a 43.1% accuracy rate in the same ReactBench tests, which shows that cheaper models may save money upfront but can lead to longer development cycles due to frequent errors and rework. |
| `43.1%` | percent | For instance, GPT-5.6 Sol, while more expensive at $1.43 per run, shows superior performance with a 43.1% accuracy rate in the same ReactBench tests, which shows that cheaper models may save money upfront but can lead to longer development cycles due to frequent errors and rework. |
| `65.3%` | percent | A study found that 65.3% of AI-generated code passed functional tests but still introduced bugs that React Doctor caught, highlighting how even high-end models may not guarantee flawless results. |
| `2x` | multiple | Low-cost models like Fable 5 introduce bugs that cost 2x more in rework time. |
| `77.5%` | percent | The 77.5% failure rate in React projects means you'll spend more time fixing errors than actually coding. |
| `54%` | percent | 54% higher token efficiency for complex tasks |
| `54%` | percent | The 54% token efficiency gain means developers can complete more complex tasks with the same budget. |
| `$3` per million input tokens | price | The $3 per million input tokens price point means developers should carefully evaluate whether the premium model's capabilities justify the increased costs for their specific use cases. |
| `43.1%` | percent | ReactBench tests showed that GPT 5.6 Sol and Fable 5 had Pass@1 scores of only 43.1% and 41.2% respectively, indicating problems in real-world React projects. |
| `41.2%` | percent | ReactBench tests showed that GPT 5.6 Sol and Fable 5 had Pass@1 scores of only 43.1% and 41.2% respectively, indicating problems in real-world React projects. |
| `20%` | percent | For instance, the user profile of ChatGPT Work is expected to shift from 20% non-programming users to 60% in 12 months. |
| `60%` | percent | For instance, the user profile of ChatGPT Work is expected to shift from 20% non-programming users to 60% in 12 months. |
| `12 months` | duration | For instance, the user profile of ChatGPT Work is expected to shift from 20% non-programming users to 60% in 12 months. |

## [Claude Code and Codex for Office Automation](https://xyzs996.github.io/llm-api-pricing/articles/claude-code-and-codex-for-office-automation.html)

Published 2026-08-22.

| Figure | Kind | In context |
| --- | --- | --- |
| `80%` | percent | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. |

## [Debunking the Myth of Overnight Success in Micro-SaaS](https://xyzs996.github.io/llm-api-pricing/articles/debunking-the-myth-of-overnight-success-in-micro-saas.html)

Published 2026-08-21.

| Figure | Kind | In context |
| --- | --- | --- |
| `$400` per month | price | A six-hour Chrome extension pays $400 a month. |
| `10%` | percent | Roughly 10% of them pay $3 a month for the premium tier. |
| `$3` per month | price | Roughly 10% of them pay $3 a month for the premium tier. |
| `$3` | price | The $3 tier adds multi-word replacement, regex matching, and per-site rules. |
| `$29` | price | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. |
| `$9.90` | price | The sweet spot for a tool-shaped micro-SaaS in North America sits somewhere between $9.90 and $49 a month, but that range is a result rather than an opening decision. |
| `$49` per month | price | The sweet spot for a tool-shaped micro-SaaS in North America sits somewhere between $9.90 and $49 a month, but that range is a result rather than an opening decision. |
| `$19` | price | You do not set $19 and wait for buyers. |
| `$19` | price | You find buyers, and $19 turns out to be what they will pay. |
| `48 hours` | duration | Someone posted screenshots of the steps for setting up an AI tool on a personal account, watched the comments fill up with people who wanted the same setup and could not follow the official instructions, priced a walkthrough at 9.9 RMB to see whether the interest survived contact with a payment screen, and took two orders inside 48 hours. |
| `$44,000` | price | Then it sold a subscription around quitting, and reached $44,000 in monthly revenue without ever being a general health app. |
| `$125K` | price | It embedded a boring feature, the survey, into the one moment when an e-commerce buyer is honest, and got to $125K MRR. |
| `$55k` | price | James Dunn paired GPS trackers with a team that physically goes out and recovers stolen bikes, which is precisely the unpleasant part nobody wants to copy, and the thing runs at $55k MRR. |
| `$500` per month | price | Generating local SEO content at volume gets a small site ranking sooner, and sites like that rent to local businesses for $500 to $3,000 a month each. |
| `$3,000` per month | price | Generating local SEO content at volume gets a small site ranking sooner, and sites like that rent to local businesses for $500 to $3,000 a month each. |
| `$3` | price | Those six hours sat on top of a decision to keep every rule client-side, which is what made a $3 subscription at a 10% conversion rate profitable instead of merely busy. |
| `10%` | percent | Those six hours sat on top of a decision to keep every rule client-side, which is what made a $3 subscription at a 10% conversion rate profitable instead of merely busy. |
| `$400` | price | Zero servers meant all $400 stayed. |

## [From AI Demo to Product: Loop Engineering for Indie Devs](https://xyzs996.github.io/llm-api-pricing/articles/from-ai-demo-to-product-loop-engineering-for-indie-devs.html)

Published 2026-08-18.

| Figure | Kind | In context |
| --- | --- | --- |
| `5 minutes` | duration | WorkBuddy + BrowserAct combination delivers competitor price lists in 5 minutes and product opportunity reports in 7 minutes. |
| `7 minutes` | duration | WorkBuddy + BrowserAct combination delivers competitor price lists in 5 minutes and product opportunity reports in 7 minutes. |
| `40 seconds` | duration | By using an AI agent to automate responses, negotiation, and price adjustment, the average response time can be reduced to within 40 seconds. |
| `7 days` | duration | API keys rotate every 7 days via /hook-triggered management. |
| `30 Days` | duration | 30 Days: Task Identification — Use SimilarWeb to validate demand for automation, then identify 3 to 5 repeatable tasks such as blog drafts or data scraping. |

## [How Chinese Developers Are Using Codex Record & Replay to Streamline Repetitive Workflows](https://xyzs996.github.io/llm-api-pricing/articles/how-chinese-developers-are-using-codex-record-replay-to.html)

Published 2026-08-05.

| Figure | Kind | In context |
| --- | --- | --- |
| `80 percent` | percent | The claimed reduction in manual effort is 80 percent, and the feature is explicitly not built for enterprise-scale workflows. |
| `4 hours` | duration | He used OpenAI Codex's Record & Replay to automate monthly report generation, taking it from 4 hours to a few minutes. |
| `80%` | percent | The skill automates the workflow, reducing manual effort by 80%, and adapts to different document formats and storage options. |
| `4-hours` | duration | The 4-hours-to-minutes report passes that test. |
| `80 percent` | percent | Most of what feels repetitive in a week does not, which is why the 80 percent figure describes a narrow slice of the work rather than 80 percent of anyone's day. |
| `80 percent` | percent | The 80 percent figure should probably travel too, with the caveat that it applies to the recorded slice and not the day. |

## [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](https://xyzs996.github.io/llm-api-pricing/articles/how-indie-developers-are-building-ai-powered-digital.html)

Published 2026-08-20.

| Figure | Kind | In context |
| --- | --- | --- |
| `$500` | price | Independent developers are using AI to mass-produce local SEO content and build vertical service sites, packaging them into "digital properties" and renting them to local businesses for monthly rent between $500 and $3,000. |
| `$3,000` | price | Independent developers are using AI to mass-produce local SEO content and build vertical service sites, packaging them into "digital properties" and renting them to local businesses for monthly rent between $500 and $3,000. |
| `$1,000,000` | price | Divide $1,000,000 by 12 months and you get $83,333 a month, which breaks down to $2,777 a day. |
| `12 months` | duration | Divide $1,000,000 by 12 months and you get $83,333 a month, which breaks down to $2,777 a day. |
| `$83,333` per month | price | Divide $1,000,000 by 12 months and you get $83,333 a month, which breaks down to $2,777 a day. |
| `$2,777` per day | price | Divide $1,000,000 by 12 months and you get $83,333 a month, which breaks down to $2,777 a day. |
| `$150` | price | You can reach that daily number by selling 18 copies of a $150 product, or by scaling higher-ticket services across a handful of properties. |
| `2.5%` | percent | At a standard 2.5% landing page conversion rate, you need roughly 720 unique visitors every single day just to move those 18 orders at $150 each. |
| `$150` | price | At a standard 2.5% landing page conversion rate, you need roughly 720 unique visitors every single day just to move those 18 orders at $150 each. |
| `$10,000` | price | Convincing a single commercial roofing contractor that your site can send $10,000 worth of monthly leads for a $1,000 monthly rental fee is an infinitely cleaner conversation. |
| `$1,000` per month | price | Convincing a single commercial roofing contractor that your site can send $10,000 worth of monthly leads for a $1,000 monthly rental fee is an infinitely cleaner conversation. |
| `2.5%` | percent | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. |
| `$1,000` | price | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. |
| `$5,000` | price | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. |

## [How to Build a Micro-SaaS Without Spending a Dime on Ads](https://xyzs996.github.io/llm-api-pricing/articles/how-to-build-a-micro-saas-without-spending-a-dime-on-ads.html)

Published 2026-08-17.

| Figure | Kind | In context |
| --- | --- | --- |
| `$10,000` | price | Sam Shore handed roughly two-thirds of Typeshare's equity to two people with established audiences, Dickie and Cole, and monthly revenue moved from $10,000 to $15,000 inside 30 days. |
| `$15,000` | price | Sam Shore handed roughly two-thirds of Typeshare's equity to two people with established audiences, Dickie and Cole, and monthly revenue moved from $10,000 to $15,000 inside 30 days. |
| `30 days` | duration | Sam Shore handed roughly two-thirds of Typeshare's equity to two people with established audiences, Dickie and Cole, and monthly revenue moved from $10,000 to $15,000 inside 30 days. |

## [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](https://xyzs996.github.io/llm-api-pricing/articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.html)

Published 2026-08-23.

| Figure | Kind | In context |
| --- | --- | --- |
| `20%` | percent | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. |
| `5 minutes` | duration | Pair WorkBuddy with BrowserAct and a complex pricing table takes 5 minutes, a product opportunity report 7. |

## [Klarna Replaced 700 Support Agents With AI. Then It Started Hiring Again.](https://xyzs996.github.io/llm-api-pricing/articles/klarna-replaced-700-support-agents-with-ai-then-it-started.html)

Published 2026-08-08.

| Figure | Kind | In context |
| --- | --- | --- |
| `$40 million` per year | price | In early 2024 the European payments company Klarna put an AI customer-service assistant in place of roughly 700 human agents and said the move was worth about $40 million a year in additional profit. |
| `74%` | percent | Feishu Shennuo's Marvy 2.0 puts 5 agents — market insight, media strategy, creative, delivery and analytics — into a single AgentOS, and a Chinese consumer-electronics brand entering the Nigerian market reported overall optimization efficiency up 74% with manual hours down 89%. |
| `89%` | percent | Feishu Shennuo's Marvy 2.0 puts 5 agents — market insight, media strategy, creative, delivery and analytics — into a single AgentOS, and a Chinese consumer-electronics brand entering the Nigerian market reported overall optimization efficiency up 74% with manual hours down 89%. |
| `30%` | percent | Agency Agents ships 232 structured expert-persona files covering identity, workflow, delivery standards and success metrics, reports output quality gains above 30%, and works across 14 mainstream AI tools; the practical difference is that a setup which used to mean hand-tuning 4 separate prompts now installs with 1 command. |
| `5 minutes` | duration | WorkBuddy paired with BrowserAct produces a competitor pricing table in about 5 minutes and a product-opportunity report in about 7, and a free WorkBuddy account carries 100 credits a day against roughly 10 credits per complex task, so the first 10 experiments cost attention rather than money. |
| `1%` | percent | One more piece of evidence that operators underweight the fragility of what they build on: a developer's Stripe account was frozen for a dispute rate above 1%, and 1,500-plus paying subscriptions stopped with it. |
| `$40 million` | price | Klarna's $40 million was probably accurate on the day it was published. |

## [MonkeyCode: The Open-Source AI Coding Platform With 900 Million Free Tokens](https://xyzs996.github.io/llm-api-pricing/articles/monkeycode-the-open-source-ai-coding-platform-with-900.html)

Published 2026-08-16.

| Figure | Kind | In context |
| --- | --- | --- |
| `900 million tokens` | tokens | MonkeyCode's free tier includes 900 million tokens, deploys to your own network with 1 command, and ships as open source you can read. |
| `900 million tokens` | tokens | The free allocation is what people notice, since 900 million tokens is well beyond what most competing tools give away and beyond what a solo developer exhausts in normal work. |
| `900 million tokens` | tokens | Which means the honest answer to "how long does 900 million tokens last" is that it depends on your repository rather than on your discipline. |
| `80 percent` | percent | Track consumption from the first week rather than from the first warning at 80 percent. |

## [Never Use a Model Where Code Can Decide](https://xyzs996.github.io/llm-api-pricing/articles/never-use-a-model-where-code-can-decide.html)

Published 2026-08-23.

| Figure | Kind | In context |
| --- | --- | --- |
| `30%` | percent | Agency Agents goes wider still, with 232 structured expert persona files, each carrying an identity, a workflow, delivery criteria and success metrics, compatible with 14 mainstream tools, and claiming an output-quality improvement of over 30%. |
| `30%` | percent | I do not believe the 30%. |
| `1,000 tokens` | tokens | One counterweight runs against all of this, and it comes from a coding agent built on an open base called Pi with only four tools, namely read, write, edit and bash, whose initial system prompt and tool descriptions together came to under 1,000 tokens. |

## [One Person, 8 AI Agents, 3,000 Baseball Caps in Two Months](https://xyzs996.github.io/llm-api-pricing/articles/one-person-8-ai-agents-3-000-baseball-caps-in-two-months.html)

Published 2026-08-05.

| Figure | Kind | In context |
| --- | --- | --- |
| `2 months` | duration | Zhang Qianchao runs a custom baseball cap export business on Alibaba.com with 8 AI agents and no employees, and in 2 months he shipped 3,000 caps to buyers across Europe, the Americas and South America at roughly the throughput of a 9-person team. |
| `3 minutes` | duration | The numbers underneath that headline are the interesting part: 3 minutes for a deep market research pass, 1,800 designs produced in a month, 12 minutes from a customer request to a rendering, and orders signed on the spot while the buyer was still in the conversation. |
| `12 minutes` | duration | The numbers underneath that headline are the interesting part: 3 minutes for a deep market research pass, 1,800 designs produced in a month, 12 minutes from a customer request to a rendering, and orders signed on the spot while the buyer was still in the conversation. |
| `12 minutes` | duration | Compressing product selection and design into a single day removes most of that gap, and compressing the rendering itself to 12 minutes removes it entirely, because the buyer is still on the call when the picture arrives. |
| `3-minute` | duration | The 3-minute research pass produces a document; knowing which parts of it are wrong is a separate skill that came from years of doing the job manually. |
| `1%` | percent | The version of this I have seen bite hardest is on the payments side, where one developer's Stripe account was frozen for a dispute rate above 1% and 1,500-plus paying subscriptions stopped at once. |
| `3 minutes` | duration | If you do not, 8 agents will get you to the wrong answer in 3 minutes instead of an afternoon, and the invoice arrives either way. |

## [Rank and Rent: Local SEO Sites That Earn $500 to $3,000 a Month](https://xyzs996.github.io/llm-api-pricing/articles/rank-and-rent-local-seo-sites-that-earn-500-to-3-000-a-month.html)

Published 2026-08-09.

| Figure | Kind | In context |
| --- | --- | --- |
| `$500` | price | The rank-and-rent model is old enough that most people have heard of it and specific enough that almost nobody runs the numbers before starting: you build a website for a local service category, you rank it in Google for the searches that category gets, and then you rent the finished site to one business in that town for somewhere between $500 and $3,000 a month. |
| `$3,000` per month | price | The rank-and-rent model is old enough that most people have heard of it and specific enough that almost nobody runs the numbers before starting: you build a website for a local service category, you rank it in Google for the searches that category gets, and then you rent the finished site to one business in that town for somewhere between $500 and $3,000 a month. |
| `$55,000` | price | BackPedal makes the point in an adjacent category: founder James Dunn pairs GPS trackers with an offline recovery team and runs about $55,000 in monthly recurring revenue, and the moat is not the tracker. |
| `$800` per month | price | A plumber comparing $800 a month to the cost of one lost emergency job is doing arithmetic that favors you. |
| `$800` per month | price | A plumber comparing $800 a month to what a website "should" cost is doing arithmetic you introduced by accident. |
| `$500` | price | Every figure in this article comes from operators describing their own results, and the $500 to $3,000 range is a report rather than a distribution — I have no idea what the median is, or how many sites never rent at all. |
| `$3,000` | price | Every figure in this article comes from operators describing their own results, and the $500 to $3,000 range is a report rather than a distribution — I have no idea what the median is, or how many sites never rent at all. |

## [Sell It Before You Build It: How Indie Devs Validate AI Products](https://xyzs996.github.io/llm-api-pricing/articles/sell-it-before-you-build-it-how-indie-devs-validate-ai.html)

Published 2026-08-12.

| Figure | Kind | In context |
| --- | --- | --- |
| `5 minutes` | duration | Pairing WorkBuddy with BrowserAct produces a competitive pricing table in about 5 minutes and a product opportunity report in about 7, which is the difference between researching a niche and researching twelve. |
| `$30` per day | price | A small Meta budget of $30 a day, run against Instagram content, produced qualified leads at $3 to $4 each in one reported test. |
| `$3` | price | A small Meta budget of $30 a day, run against Instagram content, produced qualified leads at $3 to $4 each in one reported test. |
| `$4` | price | A small Meta budget of $30 a day, run against Instagram content, produced qualified leads at $3 to $4 each in one reported test. |

## [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](https://xyzs996.github.io/llm-api-pricing/articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.html)

Published 2026-08-19.

| Figure | Kind | In context |
| --- | --- | --- |
| `40-second` | duration | When an independent developer uses Agency Agents to set up a 40-second response cycle for e-commerce listings, they are building a feedback loop that reads market conditions and adjusts, which is what separates a timed automation from a script on a timer. |
| `40-second` | duration | The 40-second number I cannot check. |

## [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](https://xyzs996.github.io/llm-api-pricing/articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.html)

Published 2026-08-22.

| Figure | Kind | In context |
| --- | --- | --- |
| `1000 tokens` | tokens | Its initial system prompt and tool description total under 1000 tokens. |
| `1000-token` | tokens | Still, I'd say the Pi base framework's 1000-token limit seems overstated. |

## [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](https://xyzs996.github.io/llm-api-pricing/articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.html)

Published 2026-08-20.

| Figure | Kind | In context |
| --- | --- | --- |
| `$30` per day | price | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. |
| `$3` | price | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. |
| `$4` | price | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. |
| `5 minutes` | duration | WorkBuddy combined with BrowserAct can produce a competitive price table in 5 minutes and an opportunity report in 7, which is roughly the difference between checking a hypothesis during a coffee break and scheduling an afternoon for it. |
| `5-minute` | duration | I remain a little skeptical of how well those reports hold up on messy niches, but for a first pass on pricing structure the speed is hard to argue with, and a 5-minute price table you can throw away costs you nothing when the niche turns out to be wrong. |

## [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](https://xyzs996.github.io/llm-api-pricing/articles/stop-using-ai-as-a-chatbot-how-to-build-an-indie.html)

Published 2026-08-23.

| Figure | Kind | In context |
| --- | --- | --- |
| `$24,000` | price | One watched competitor prices, one produced ad creative, one answered customer mail, and together they pulled 170,000 yuan a month out of them, somewhere near $24,000. |
| `90%` | percent | I would not defend the 90% too hard — nobody audited it, and it reads like a number someone rounded up on stage. |
| `30%` | percent | The Agency Agents project keeps 232 structured expert persona files, each one pinning down an identity, a workflow, a delivery standard and a definition of success; the project claims over 30% better output across the 14 AI tools it supports. |
| `30%` | percent | I have no idea how they measured that 30%, and I suspect nobody outside the project does either. |
| `1000 tokens` | tokens | Under 1000 tokens of system prompt is not a ceiling, though — it is a starting position, and a deliberate one. |
| `90 minutes` | duration | The results people report from this are unglamorous and large: a security team that froze its vulnerability-scanning routine into a package watched its bug bounty income triple, and a daily-report routine standardised the same way dropped from 90 minutes to 8. |
| `5 minutes` | duration | WorkBuddy and BrowserAct put numbers on the same shift for e-commerce sellers: a competitor pricing table in 5 minutes, a product opportunity report in 7. |

## [The $22K-a-Month AI Tool That Never Bought a Single Ad](https://xyzs996.github.io/llm-api-pricing/articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.html)

Published 2026-08-23.

| Figure | Kind | In context |
| --- | --- | --- |
| `$22,000` per month | price | StoryShort hit $22,000 a month in its first three months. |
| `$500,000` | price | Cumulative revenue was close to $500,000 by the time the product went up for sale. |
| `$63,000` per month | price | That script became Resellbot, which runs at $63,000 a month. |
| `95%` | percent | Across four independent cases, roughly 95% of users arrived through content rather than paid placement, and the operators who sustained it did so on a fixed publishing cadence with a repeatable hook rather than on inspiration. |
| `$83,333` per month | price | A million dollars a year is $83,333 a month, or $2,777 a day. |
| `$2,777` per day | price | A million dollars a year is $83,333 a month, or $2,777 a day. |
| `$150` | price | On a $150 product that is 18 sales a day, and at a 2.5% landing-page conversion rate, 18 sales needs 720 visitors a day. |
| `2.5%` | percent | On a $150 product that is 18 sales a day, and at a 2.5% landing-page conversion rate, 18 sales needs 720 visitors a day. |
| `$22,000` per month | price | The organic channel that produced $22,000 a month is running at roughly half the traffic a million-dollar year would need, and it took three months to get there. |
| `$1.2 million` | price | StoryShort was listed at $1.2 million, about 4.4 times annual revenue, at a point when its most recent thirty days were running 11% below the thirty before them. |
| `11%` | percent | StoryShort was listed at $1.2 million, about 4.4 times annual revenue, at a point when its most recent thirty days were running 11% below the thirty before them. |

## [The 5 AI Features That Separated 27 Profitable Solopreneurs From the Rest](https://xyzs996.github.io/llm-api-pricing/articles/the-5-ai-features-that-separated-27-profitable-solopreneurs.html)

Published 2026-08-18.

| Figure | Kind | In context |
| --- | --- | --- |
| `2 hours` | duration | An administrative staff member cut sales data reporting from 2 hours to 5 minutes with an automated daily data pull. |
| `5 minutes` | duration | An administrative staff member cut sales data reporting from 2 hours to 5 minutes with an automated daily data pull. |
| `2 hours` | duration | 2 hours down to 5 minutes is the headline, and it is not the interesting part. |
| `5 minutes` | duration | 2 hours down to 5 minutes is the headline, and it is not the interesting part. |
| `3 hours` | duration | Newsletter creation dropped from 3 hours to 15 minutes once research, writing, and distribution were packaged together, which is the same 12-to-1 compression the reporting case showed and probably not a coincidence, since both were sequences of small handoffs rather than single hard problems. |
| `15 minutes` | duration | Newsletter creation dropped from 3 hours to 15 minutes once research, writing, and distribution were packaged together, which is the same 12-to-1 compression the reporting case showed and probably not a coincidence, since both were sequences of small handoffs rather than single hard problems. |
| `87 percent` | percent | MCP connectors reduced manual data handling time by 87 percent in the cases that used them. |
| `4 hours` | duration | Analysts cut Power BI debugging from 4 hours to 5 minutes using built-in modeling skills that generated correct DAX formulas, and customer service response times fell from 1 hour to 3 minutes once agents could read and update CRM records directly. |
| `5 minutes` | duration | Analysts cut Power BI debugging from 4 hours to 5 minutes using built-in modeling skills that generated correct DAX formulas, and customer service response times fell from 1 hour to 3 minutes once agents could read and update CRM records directly. |
| `1 hour` | duration | Analysts cut Power BI debugging from 4 hours to 5 minutes using built-in modeling skills that generated correct DAX formulas, and customer service response times fell from 1 hour to 3 minutes once agents could read and update CRM records directly. |
| `3 minutes` | duration | Analysts cut Power BI debugging from 4 hours to 5 minutes using built-in modeling skills that generated correct DAX formulas, and customer service response times fell from 1 hour to 3 minutes once agents could read and update CRM records directly. |
| `87 percent` | percent | The 87 percent figure and those two cases are measuring the same thing from different angles, which is time spent moving data by hand between a system that knows the answer and a system that needs it. |
| `3 weeks` | duration | Average time from concept to full production deployment was about 2 to 3 weeks. |
| `3 weeks` | duration | If your work is mostly one-off, the components that make repetition cheap are solving a problem you do not have, and those 2 to 3 weeks are better spent elsewhere. |

## [The AI Branding Revolution: How Indie Developers Are Ditching Design Costs with AI](https://xyzs996.github.io/llm-api-pricing/articles/the-ai-branding-revolution-how-indie-developers-are.html)

Published 2026-08-16.

| Figure | Kind | In context |
| --- | --- | --- |
| `90%` | percent | AI branding tools like Miora let indie developers cut design costs by 90%. |

## [The First Line of Defense in AI Programming: Environment Variable Management](https://xyzs996.github.io/llm-api-pricing/articles/the-first-line-of-defense-in-ai-programming-environment.html)

Published 2026-08-08.

| Figure | Kind | In context |
| --- | --- | --- |
| `10 minutes` | duration | The mechanics are unglamorous and take about 10 minutes on a project that does not exist yet. |
| `6 hours` | duration | 10 lines of validation buys back an hour of debugging the first time it fires, and probably 5 or 6 hours across a year on a project with 3 or 4 deployment environments, which is a return most refactors cannot match. |
| `30-second` | duration | The gap opens when someone pastes a key into a chat window to debug why a call is failing, which is a 30-second decision that puts a live credential into a log you do not control and cannot delete. |
| `10 minutes` | duration | Setting this up takes 10 minutes on a new project and rather longer on an existing one, which is why people put it off. |

## [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](https://xyzs996.github.io/llm-api-pricing/articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.html)

Published 2026-08-23.

| Figure | Kind | In context |
| --- | --- | --- |
| `10,000 token` | tokens | One project crashed when it hit an undocumented 10,000 token limit in one coding session. |
| `20%` | percent | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. |
| `30%` | percent | Those who have already made the switch to Chinese tools have seen productivity increases of up to 30%. |

## [The Hidden Costs of GPT-5.6 Model Selection: A Developer's Real-World Guide](https://xyzs996.github.io/llm-api-pricing/articles/the-hidden-costs-of-gpt-5-6-model-selection-a-developer-s.html)

Published 2026-08-12.

| Figure | Kind | In context |
| --- | --- | --- |
| `95%` | percent | Luna's 95% accuracy rate at 1/3 the cost of Terra shows how much you can save by making the right choice. |
| `3x` | multiple | Terra requires 3x more tokens for equivalent tasks, and its 800ms response time makes it far less efficient for time-sensitive applications. |
| `95%` | percent | Terra's document processing capabilities might seem cost-effective initially, but Luna's 95% accuracy on basic QA tasks and faster response times mean fewer errors and rework, whereas Terra's higher failure rate on complex tasks can lead to time wasted fixing mistakes, and Luna's superior accuracy and reliability make it a better long-term choice, even though Terra often requires more tokens for similar tasks. |
| `95%` | percent | For example, Luna's 95% accuracy rate for basic questions drops when faced with more complex queries, and Terra's document analysis accuracy can vary depending on document structure and content. |
| `20%` | percent | Open Code Review requires 1/9th the tokens of standard agents and offers a 20% higher accuracy rate. |
| `95%` | percent | For example, Luna's 95% accuracy in basic Q&A is great for customer service, but the error correction time can be a drawback. |
| `2x` | multiple | Terra's ability to extract all data is ideal for document processing, but its 2x token usage may be a concern for large-scale projects. |
| `95%` | percent | Luna's 95% accuracy rate for basic questions makes it ideal for simple tasks, while Terra's strength shows up in document analysis and more complex scenarios. |
| `2x` | multiple | Luna takes less developer time, which shows how much more efficient it is overall, and Terra's 2x more tokens for equivalent tasks adds up quickly in larger projects. |
| `95%` | percent | Luna's 95% accuracy rate reduces rework costs, and Terra's higher token costs add up over time. |
| `9 token` | tokens | Open Code Review's 1/9 token consumption advantage over general-purpose agents translates to large cost savings for development teams. |
| `6 months` | duration | A mid-sized e-commerce company cut its model spend over 6 months. |

## [The Klarna Lesson: Why AI Implementation Needs a Staircase, Not a Leap](https://xyzs996.github.io/llm-api-pricing/articles/the-klarna-lesson-why-ai-implementation-needs-a-staircase.html)

Published 2026-08-10.

| Figure | Kind | In context |
| --- | --- | --- |
| `$40 million` | price | Klarna's AI customer service experiment, which replaced 700 human agents, initially saved $40 million in a year, but the quality of service suffered so badly that they had to rehire humans, leading the CEO to admit they "went too far" with automation after 12 months. |
| `12 months` | duration | Klarna's AI customer service experiment, which replaced 700 human agents, initially saved $40 million in a year, but the quality of service suffered so badly that they had to rehire humans, leading the CEO to admit they "went too far" with automation after 12 months. |
| `12 months` | duration | Quality degradation typically appears 6-12 months after full automation—long after the press releases have been sent. |

## [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](https://xyzs996.github.io/llm-api-pricing/articles/the-token-cost-war-why-price-per-million-tokens-now-decides.html)

Published 2026-08-10.

| Figure | Kind | In context |
| --- | --- | --- |
| `$0.19` per million tokens | price | The competition among model vendors used to be argued in benchmark scores, and it is now being argued in cost per million tokens — Indian enterprises are adopting Chinese models at input prices as low as $0.19 per million tokens against $5 to $12 for comparable American offerings, which is not a discount so much as a different category of product. |
| `$5` per million tokens | price | The competition among model vendors used to be argued in benchmark scores, and it is now being argued in cost per million tokens — Indian enterprises are adopting Chinese models at input prices as low as $0.19 per million tokens against $5 to $12 for comparable American offerings, which is not a discount so much as a different category of product. |
| `$12` | price | The competition among model vendors used to be argued in benchmark scores, and it is now being argued in cost per million tokens — Indian enterprises are adopting Chinese models at input prices as low as $0.19 per million tokens against $5 to $12 for comparable American offerings, which is not a discount so much as a different category of product. |
| `$19 billion` | price | Anthropic's $19 billion data center lease locks in five to eight years of compute, which reframes the competition as a contest over power and floor space rather than architecture. |
| `$1.25` per million input tokens | price | Meta's Muse Spark 1.1 agent model API is priced at $1.25 per million input tokens and $4.25 per million output tokens — roughly 75% and 83% below Anthropic Opus on input and output respectively — and the target is explicit: become the cheap entry point for agent workflows and pull developers into the ecosystem. |
| `$4.25` per million output tokens | price | Meta's Muse Spark 1.1 agent model API is priced at $1.25 per million input tokens and $4.25 per million output tokens — roughly 75% and 83% below Anthropic Opus on input and output respectively — and the target is explicit: become the cheap entry point for agent workflows and pull developers into the ecosystem. |
| `75%` | percent | Meta's Muse Spark 1.1 agent model API is priced at $1.25 per million input tokens and $4.25 per million output tokens — roughly 75% and 83% below Anthropic Opus on input and output respectively — and the target is explicit: become the cheap entry point for agent workflows and pull developers into the ecosystem. |
| `83%` | percent | Meta's Muse Spark 1.1 agent model API is priced at $1.25 per million input tokens and $4.25 per million output tokens — roughly 75% and 83% below Anthropic Opus on input and output respectively — and the target is explicit: become the cheap entry point for agent workflows and pull developers into the ecosystem. |
| `80%` | percent | Aggressive pricing at the agent tier is a different move from aggressive pricing at the chat tier, because agent workloads consume tokens in volumes where an 80% cut changes what is economically possible rather than just what is comfortable. |
| `$1.43` | price | On ReactBench, one run of GPT-5.6 Sol costs about $1.43 while Fable 5 costs $9.05 for the same work — a gap that no per-token price list would have predicted, because the expensive model is not six times more expensive per token, it is six times less efficient at finishing the job. |
| `$9.05` | price | On ReactBench, one run of GPT-5.6 Sol costs about $1.43 while Fable 5 costs $9.05 for the same work — a gap that no per-token price list would have predicted, because the expensive model is not six times more expensive per token, it is six times less efficient at finishing the job. |
| `10,000 tokens` | tokens | OmniRoute pools 237 providers into around 1.6 billion free tokens a month and applies RTK plus Caveman compression to squeeze 10,000 tokens down to 1,080, which effectively multiplies whatever free allowance you have by ten. |
| `400 tokens` | tokens | Anthropic's SKILL.md file is 400 tokens of aesthetic guidance and a two-pass working method, and it has been installed over 1.08 million times — a return on 400 tokens that argues taste-shaping is worth more than tool-building, at least in front-end generation. |
| `$13 billion` | price | Deloitte figures suggest an enterprise with $13 billion in annual revenue may put as much as $700 million into AI, while Jellyfish research finds high token consumption badly out of balance with productivity gains. |
| `$700 million` | price | Deloitte figures suggest an enterprise with $13 billion in annual revenue may put as much as $700 million into AI, while Jellyfish research finds high token consumption badly out of balance with productivity gains. |

## [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](https://xyzs996.github.io/llm-api-pricing/articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.html)

Published 2026-08-21.

| Figure | Kind | In context |
| --- | --- | --- |
| `43.1%` | percent | On ReactBench, GPT 5.6 Sol and Fable 5 posted Pass@1 scores of 43.1% and 41.2%. |
| `41.2%` | percent | On ReactBench, GPT 5.6 Sol and Fable 5 posted Pass@1 scores of 43.1% and 41.2%. |
| `$1.43` | price | A single run costs about $1.43 on the first and $9.05 on the second. |
| `$9.05` | price | A single run costs about $1.43 on the first and $9.05 on the second. |
| `43.1%` | percent | Any workflow you build on top of that has to assume a human reads the output, because a tool at 43.1% is a filter, not an approver. |
| `43.1%` | percent | A 43.1% filter is useful in front of a reviewer and useless in place of one. |
| `$1.43` | price | $1.43 against $9.05, per run, on the same benchmark. |
| `$9.05` | price | $1.43 against $9.05, per run, on the same benchmark. |
| `43%` | percent | It compounds in the direction people least expect, too — the cheaper model is the one you can afford to run twice on the same diff, and running a 43% filter twice catches more than running it once. |
| `54%` | percent | Sol operates in an ultra-mode with internal multi-agents, which improves task completion accuracy and token efficiency; in agentic coding tasks it is 54% more token-efficient than comparable models. |
| `$1.43` | price | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. |
| `$9.05` | price | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. |
| `43.1%` | percent | Those are the two things a 43.1% score is telling you the model cannot do. |
| `9 token` | tokens | Run a specialised reviewer rather than a general agent where one exists for your stack — the 1/9 token figure is the largest single number in this whole comparison, and it is the one people skip. |
| `43.1%` | percent | At 43.1%, that is what it is. |

## [Token Optimization for Indie Developers' AI API Bills](https://xyzs996.github.io/llm-api-pricing/articles/token-optimization-for-indie-developers-ai-api-bills.html)

Published 2026-08-18.

| Figure | Kind | In context |
| --- | --- | --- |
| `10 minutes` | duration | 10 minutes of consolidation on a calm afternoon converts that outage into a 1-line change. |
| `10,000 tokens` | tokens | Long coding sessions push entire directory trees into the prompt on every iteration, so gateways have started applying compression algorithms such as RTK and Caveman, which OmniRoute reports can shrink 10,000 tokens to 1,080. |
| `10,000-token` | tokens | Compression numbers are measured on the payloads that compress best, and a 10,000-token blob of repeated boilerplate is not the same as 10,000 tokens of dense, unique source. |
| `10,000 tokens` | tokens | Compression numbers are measured on the payloads that compress best, and a 10,000-token blob of repeated boilerplate is not the same as 10,000 tokens of dense, unique source. |
| `9x` | multiple | Open Code Review reports roughly 9x lower token consumption than general-purpose agents while holding accuracy, which suggests that a specialized agent aimed at one job often beats a heavy generalist on the only axis an indie developer can afford to optimize. |
| `3,000 tokens` | tokens | It comes from a system prompt of 3,000 tokens replayed on every one of 40 turns in an agent loop, or from a file-tree dump the editor attaches whether or not the current question touches those files. |

## [When AI Customer Service Backfired: Klarna’s Case and the Four-Stage Path to Enterprise AI Adoption](https://xyzs996.github.io/llm-api-pricing/articles/when-ai-customer-service-backfired-klarna-s-case-and-the.html)

Published 2026-08-16.

| Figure | Kind | In context |
| --- | --- | --- |
| `$4 million` per year | price | Klarna reported $4 million a year in savings and a 99.96 percent conversation engagement rate, the kind of pair of numbers that ends an internal debate before it starts. |
| `99.96 percent` | percent | Klarna reported $4 million a year in savings and a 99.96 percent conversation engagement rate, the kind of pair of numbers that ends an internal debate before it starts. |
| `$4 million` | price | Klarna ran that sequence backwards, and the $4 million showed up on the books months before the CSAT number showed up to argue with it. |
| `$4 million` | price | The company reported $4 million in annual savings after the switch, which is the number that frees up budget for everything else on the roadmap. |
| `99.96%` | percent | The AI held a 99.96% conversation engagement rate, level with what the human agents had been delivering, and that consistency is what customer retention runs on. |
| `68%` | percent | Six months after Klarna’s rollout, customer satisfaction scores fell to 68%. |
| `10%` | percent | In 10% of cases it misclassified a complaint as a simple issue and left a customer waiting on a resolution that was never coming, and another 18% of the cases that did get escalated were mishandled after the handoff. |
| `18%` | percent | In 10% of cases it misclassified a complaint as a simple issue and left a customer waiting on a resolution that was never coming, and another 18% of the cases that did get escalated were mishandled after the handoff. |
| `99.96%` | percent | The 99.96% engagement rate says it could hold up the interaction volume; the 18% conversion rate says the emotional read was missing. |
| `18%` | percent | The 99.96% engagement rate says it could hold up the interaction volume; the 18% conversion rate says the emotional read was missing. |
| `10%` | percent | Complaints about "cold responses" rose 10%, which is the number that told them a transactional bot was not going to carry a long-term relationship. |
| `68%` | percent | A CSAT of 68% is what that looks like from the outside: the queries still get answered, and the people asking them stop believing the answers. |
| `10%` | percent | The 10% misclassified as simple and the 18% mishandled after escalation are both routing errors with a paper trail. |
| `18%` | percent | The 10% misclassified as simple and the 18% mishandled after escalation are both routing errors with a paper trail. |
| `22%` | percent | Klarna’s hybrid model steered customers to human agents automatically when the AI detected emotional distress or a policy exception, and that, paired with clear handoff protocols, lifted first-contact resolution by 22%. |
| `10%` | percent | Klarna’s AI now handles the simple issues and a human agent audits 10% of escalated cases weekly, which holds quality while cutting costs by 60%. |
| `60%` | percent | Klarna’s AI now handles the simple issues and a human agent audits 10% of escalated cases weekly, which holds quality while cutting costs by 60%. |
| `60%` | percent | What the ladder bought Klarna was the 60% cost reduction without the service collapse, and the reason it held is that each rung was allowed to fail cheaply before the next one got built. |
| `10%` | percent | One A/B test cuts against the intuition here: the blunter, more pressuring script was the one that lifted lead conversion from 10% to 18%, not the gentler one. |
| `18%` | percent | One A/B test cuts against the intuition here: the blunter, more pressuring script was the one that lifted lead conversion from 10% to 18%, not the gentler one. |
| `$4 million` | price | This is one company, one quarter, and Klarna had reasons to publish both the $4 million and the retraction that have nothing to do with what works for a team of one. |
| `10%` | percent | Klarna's 10% and 18% are exactly those two counters, and they are the only numbers in this story that would have predicted the rehiring before it happened. |
| `18%` | percent | Klarna's 10% and 18% are exactly those two counters, and they are the only numbers in this story that would have predicted the rehiring before it happened. |

## [When the AI Picks for the Customer, You Become a Supplier](https://xyzs996.github.io/llm-api-pricing/articles/when-the-ai-picks-for-the-customer-you-become-a-supplier.html)

Published 2026-08-15.

| Figure | Kind | In context |
| --- | --- | --- |
| `15 minutes` | duration | "Order hot or iced coffee for pickup within 15 minutes, 7 a.m. to 8 p.m., at 3 locations in this district, with member pricing applied at checkout" matches a request, and it also happens to tell the assistant that member pricing exists, which is how a brand agent like the one Luckin Coffee and KFC connected to keeps its loyalty economics visible instead of getting flattened into a generic listing. |

## [Why Pi's 1000-Token Agent Engine Needs a Sandbox Before You Touch It](https://xyzs996.github.io/llm-api-pricing/articles/why-pi-s-1000-token-agent-engine-needs-a-sandbox-before-you.html)

Published 2026-08-17.

| Figure | Kind | In context |
| --- | --- | --- |
| `1,000 tokens` | tokens | Pi's system prompt and its 4 tool descriptions come to under 1,000 tokens, which is the whole reason to like it. |
| `1,000 tokens` | tokens | Under 1,000 tokens for the prompt and all 4 tool descriptions is roughly the length of this section, and every token you save there is a token available for the actual problem. |
| `1,000 tokens` | tokens | The fourth is not a tool so much as an escape hatch to the entire operating system, and it is doing the work that 20 tools would do in a larger framework, which is exactly why the total comes in under 1,000 tokens. |
| `1,000 tokens` | tokens | That is arguably the correct decision for Pi, since guided discovery is exactly the kind of thing that costs tokens in the system prompt, and the whole premise here is that the prompt stays under 1,000 tokens. |

## [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](https://xyzs996.github.io/llm-api-pricing/articles/why-stripping-80-of-system-prompts-actually-improved-claude.html)

Published 2026-08-20.

| Figure | Kind | In context |
| --- | --- | --- |
| `80%` | percent | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. |
| `80%` | percent | Stripping away that redundant 80% removes the cognitive drag holding the model back, freeing native reasoning capacity and cutting the token burn. |

## [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](https://xyzs996.github.io/llm-api-pricing/articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.html)

Published 2026-08-22.

| Figure | Kind | In context |
| --- | --- | --- |
| `$1,000,000` | price | Breaking a $1,000,000 annual revenue goal into a daily intake of $2,777 — eighteen standardized units at $150 a day — is the same discipline applied with a bigger numerator, and it works for the same reason: it converts an ambition into a countable daily event. |
| `$2,777` | price | Breaking a $1,000,000 annual revenue goal into a daily intake of $2,777 — eighteen standardized units at $150 a day — is the same discipline applied with a bigger numerator, and it works for the same reason: it converts an ambition into a countable daily event. |
| `$150` per day | price | Breaking a $1,000,000 annual revenue goal into a daily intake of $2,777 — eighteen standardized units at $150 a day — is the same discipline applied with a bigger numerator, and it works for the same reason: it converts an ambition into a countable daily event. |
| `9.1%` | percent | An automated intake system handled 287 users, and 158 of them actually made it into the group — the entry rate went from 9.1% to 55.1%, and the median time from adding a contact to landing in the group dropped from 164.84 minutes to 13.88 minutes. |
| `55.1%` | percent | An automated intake system handled 287 users, and 158 of them actually made it into the group — the entry rate went from 9.1% to 55.1%, and the median time from adding a contact to landing in the group dropped from 164.84 minutes to 13.88 minutes. |
| `164.84 minutes` | duration | An automated intake system handled 287 users, and 158 of them actually made it into the group — the entry rate went from 9.1% to 55.1%, and the median time from adding a contact to landing in the group dropped from 164.84 minutes to 13.88 minutes. |
| `13.88 minutes` | duration | An automated intake system handled 287 users, and 158 of them actually made it into the group — the entry rate went from 9.1% to 55.1%, and the median time from adding a contact to landing in the group dropped from 164.84 minutes to 13.88 minutes. |
| `83.1%` | percent | Unmanaged groups held 83.1% of the total group inventory and contributed 2.3% of new incoming traffic; the managed ones recorded 170 new entries against 4 from everything else combined. |
| `2.3%` | percent | Unmanaged groups held 83.1% of the total group inventory and contributed 2.3% of new incoming traffic; the managed ones recorded 170 new entries against 4 from everything else combined. |
| `3 months` | duration | Running a closed loop across a content platform, visual assets, and a private community, a vertical sub-account booked over 700 customer conversions and 60,000 RMB in gross merchandise volume within 3 months. |
| `3 hours` | duration | A modular production pipeline built on Feishu, Obsidian and scripted automation cut document management from hours to minutes, and a single trigger word now generates the draft, the illustrated body and the promotional copy in one pass, replacing the 2 to 3 hours of daily manual compilation that used to sit in front of every publish. |
| `3 months` | duration | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. |
| `2 years` | duration | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. |
| `$22,000` | price | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. |
| `$500,000` | price | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. |

## [Why Your AI Agent Goes Off the Rails: Give It Boring Work First](https://xyzs996.github.io/llm-api-pricing/articles/why-your-ai-agent-goes-off-the-rails-give-it-boring-work.html)

Published 2026-08-05.

| Figure | Kind | In context |
| --- | --- | --- |
| `300 million tokens` | tokens | One developer logged token consumption across the first three days of an agent-driven project in July 2026 and got a curve that says almost everything I think is worth saying about this technology: 300 million tokens on day one, about 200 million on day two, about 100 million on day three. |
| `72 hours` | duration | Nothing about the models changed in those 72 hours. |
| `3 weeks` | duration | Version your skills like software. treats AI skills as packages with rollback and permission control, which is the difference between a team that can undo a bad change and a team whose output quality quietly degrades because somebody edited a prompt in place 3 weeks ago. |

## [Why Your Indie App Needs Short-Form Video Marketing (And How to Get Started)](https://xyzs996.github.io/llm-api-pricing/articles/why-your-indie-app-needs-short-form-video-marketing-and-how.html)

Published 2026-08-11.

| Figure | Kind | In context |
| --- | --- | --- |
| `60 seconds` | duration | The videos run about 60 seconds. |
| `95 percent` | percent | The developer posts 3 to 5 a week across several platforms, mostly product demos and short tutorials, and 95 percent of the users arrive through that organic content rather than through anything paid. |
| `95 percent` | percent | The 95 percent is the number worth being suspicious of, and the 12 hours a week behind it is the number worth doing arithmetic on. |
| `12 hours` | duration | The 95 percent is the number worth being suspicious of, and the 12 hours a week behind it is the number worth doing arithmetic on. |
| `60-second` | duration | Here is what a 60-second demo has to contain to be worth posting, why the weekly time budget is tighter than it looks, and where the organic numbers stop being believable. |
| `60 seconds` | duration | The videos are around 60 seconds, the format is product demonstrations and concise tutorials, and the cadence is 3 to 5 a week across YouTube and TikTok. |
| `95 percent` | percent | A 95 percent organic share is not implausible for a product with no ad budget, because when the denominator contains no paid traffic at all, organic wins by default. |
| `95 percent` | percent | A product with 200 users and a product with 200,000 can both report 95 percent organic, and the strategy that produced the first one is not evidence for anything. |
| `2 hours` | duration | Editing takes about 2 hours per 60-second video, including AI-assisted effects and transitions. |
| `60-second` | duration | Editing takes about 2 hours per 60-second video, including AI-assisted effects and transitions. |
| `12 hours` | duration | The overall commitment is roughly 12 hours a week on video creation and platform management, and AI tools cut the scripting and editing time by about 30 percent. |
| `30 percent` | percent | The overall commitment is roughly 12 hours a week on video creation and platform management, and AI tools cut the scripting and editing time by about 30 percent. |
| `2 hours` | duration | Four videos a week at 2 hours each is 8 hours of editing before anyone has written a script, answered a comment, or looked at an analytics dashboard, which leaves about 4 hours for everything else in a 12-hour budget. |
| `8 hours` | duration | Four videos a week at 2 hours each is 8 hours of editing before anyone has written a script, answered a comment, or looked at an analytics dashboard, which leaves about 4 hours for everything else in a 12-hour budget. |
| `4 hours` | duration | Four videos a week at 2 hours each is 8 hours of editing before anyone has written a script, answered a comment, or looked at an analytics dashboard, which leaves about 4 hours for everything else in a 12-hour budget. |
| `12-hour` | duration | Four videos a week at 2 hours each is 8 hours of editing before anyone has written a script, answered a comment, or looked at an analytics dashboard, which leaves about 4 hours for everything else in a 12-hour budget. |
| `30 percent` | percent | It is a part-time job attached to the product, and the 30 percent that AI tools give back is the difference between it being sustainable and it quietly stopping in week six. |
| `60 percent` | percent | Roughly 60 percent of the video content gets reused across platforms, cutting production time by about 40 percent, and the reused clips hold engagement rates comparable to the originals. |
| `40 percent` | percent | Roughly 60 percent of the video content gets reused across platforms, cutting production time by about 40 percent, and the reused clips hold engagement rates comparable to the originals. |
| `40 percent` | percent | If repurposed content performed noticeably worse, the 40 percent saving would be an illusion, since you would need more posts to get the same result. |
| `3.5 hours` | duration | An independent developer automated an entire publishing workflow using two AI skills, shiwen and ai-wechat-publisher, going from topic selection to a finished draft in under 3.5 hours. |
| `3.5 hours` | duration | Under 3.5 hours is a believable number precisely because it is unremarkable. |
| `5 minutes` | duration | WorkBuddy and BrowserAct together generate a complete competitor price list in about 5 minutes and a product opportunity report in about 7, which replaces the browser-tab afternoon that most solo developers either do badly or skip entirely. |
| `60 seconds` | duration | They do not decide what to build, which product to compare yourself against, or whether the demo you just recorded is worth a stranger's 60 seconds. |
| `$1 million` | price | The revenue arithmetic behind a $1 million annual target is simple enough to do on a napkin. |
| `$150` | price | Selling 18 units of a $150 product every day gets you there, and 18 daily sales at a 2.5 percent landing-page conversion rate requires roughly 720 visitors a day. |
| `2.5 percent` | percent | Selling 18 units of a $150 product every day gets you there, and 18 daily sales at a 2.5 percent landing-page conversion rate requires roughly 720 visitors a day. |
| `20 percent` | percent | AI tooling produced about a 20 percent increase in content output with no corresponding increase in monetization. |
| `20 percent` | percent | If the demo does not land, making 20 percent more of it produces 20 percent more of nothing, and the founder is now busier while measuring the same revenue. |
| `20 percent` | percent | I may be reading too much into a single case, but a 20 percent lift that moves no money at all looks less like a slow start and more like a signal that the bottleneck sits somewhere the tooling never touched, probably in what the first two seconds of the video promise. |
| `8 hours` | duration | Around 8 hours went into learning them, and their output quality varies enough to need manual adjustment that nobody accounts for in the original estimate. |
| `12-hour` | duration | The real cost of the 12-hour weekly commitment is not the 12 hours. |
| `12 hours` | duration | The real cost of the 12-hour weekly commitment is not the 12 hours. |
| `60-second` | duration | Formal production training is not required for a 60-second screen recording of software doing something useful, and AI tools cover most of the gap that skill would have filled. |
| `60 percent` | percent | A structured gate that lifted article read rates to 60 percent did so by reducing algorithmic demotion, which is a reminder that platforms are not just distributing your content, they are grading it, and the grade compounds. |
| `12 hours` | duration | Skip this approach if you cannot commit 12 hours a week for several months, or if your product does not demonstrate visually. |
| `60-second` | duration | A tool whose value only appears after a week of use has no 60-second version, and no amount of editing skill invents one. |

## [Your AI Coding Bill Scales With Your Repo, Not Your Output](https://xyzs996.github.io/llm-api-pricing/articles/your-ai-coding-bill-scales-with-your-repo-not-your-output.html)

Published 2026-08-11.

| Figure | Kind | In context |
| --- | --- | --- |
| `9x` | multiple | Alibaba's Open Code Review was benchmarked against general-purpose agents on 200 real pull requests drawn from 50 open-source repositories across 10 languages, and it scored higher on accuracy and F1 while consuming roughly one-ninth the tokens, a 9x gap on identical work. |

## [Your Agent Writes Code Faster Than Anyone Can Review It](https://xyzs996.github.io/llm-api-pricing/articles/your-agent-writes-code-faster-than-anyone-can-review-it.html)

Published 2026-08-11.

| Figure | Kind | In context |
| --- | --- | --- |
| `30%` | percent | Agency Agents takes that to its logical end with 232 structured expert-persona files that work across 14 mainstream AI tools and a claimed output-quality improvement above 30%. |

<script type="application/ld+json">
{"@context": "https://schema.org", "@type": "Dataset", "name": "Every figure published in AI Coding Field Notes", "description": "479 figures pulled out of 53 write-ups on running AI coding agents in production (prices, percentages, multiples, token counts and durations). Each row carries the full sentence the figure appeared in, quoted verbatim from the published piece, plus a link to that piece. Prices also carry the unit they were quoted in (per million tokens, per month, per run) wherever the sentence states one.", "url": "https://xyzs996.github.io/llm-api-pricing/figures.html", "license": "https://creativecommons.org/licenses/by/4.0/", "isAccessibleForFree": true, "creator": {"@type": "Person", "name": "xyzs996", "url": "https://github.com/xyzs996"}, "keywords": ["AI coding agents", "LLM pricing", "developer tools", "token costs", "AI coding assistants"], "variableMeasured": ["prices", "percentages", "multiples", "token counts", "durations"], "distribution": [{"@type": "DataDownload", "encodingFormat": "application/json", "contentUrl": "https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json"}, {"@type": "DataDownload", "encodingFormat": "text/csv", "contentUrl": "https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv"}], "isBasedOn": "https://github.com/xyzs996/llm-api-pricing", "temporalCoverage": "2026-08-05/2026-08-24", "dateModified": "2026-08-24"}
</script>
