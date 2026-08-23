# What a coding-agent model costs, next to how it ranks

60 models that have been ranked in an agent category of the
Design Arena, with what each one lists per million tokens. Read from
[OpenRouter](https://openrouter.ai/models)'s public catalog on **2026-08-23**.

**List price is not your bill, and here is by how much.** A coding
agent re-reads its context on every step, so about **95.6% of the
tokens it sends are cache reads** — priced at a fraction of the
list input price that every other pricing table sorts by. Repriced
at that mix, the list input price overstates what an agent actually
pays by a median **6.5×** (range 3.4×–7.9× across the
58 rows where it can be computed).

**The ranking barely moves; the bill does.** 9 of
the 10 cheapest by list price are still in the cheapest 10 repriced,
and the spread from cheapest to dearest is 53× either way. So list price tells you
*which* model is cheap and lies about *what you will pay* — and the
3.4×–7.9× spread in that multiple is what actually
separates two models whose list prices look identical.

That 95.6% is **one person's measurement of one coding agent** ([8.04B tokens, 2026-05-16](https://gist.github.com/hungson175/91147b729afdf9fd691342359265731b)), not an industry figure — it is simply the only public measurement we could find. 58 of these rows publish a cached-input price, so the weights ship in the JSON: recompute with your own mix. Cache-*write* prices are not in the catalog, so that 2.7% of tokens is folded into the cache-miss share, which understates cost by roughly 0.7%.

**12 of the 60 rows below cost more than the price in their own row, and the trigger is how long your prompt is.** Once a prompt is past the threshold, every token in that request bills at the higher rate — including the tokens before the threshold. It is a cliff, not a tier, so a request one token over the line costs about double a request one token under it. The thresholds in this table are 200k and 272k prompt tokens.

The counter-intuitive part is that **the bigger the advertised context window, the smaller the share of it that the advertised price covers.** `x-ai/grok-4.20` advertises 2 000k of context at $1.25 per million input, but the price steps to $2.50 (2.0×) at 200k — so **90% of that window is billed at the higher number**, not the one in the row. The highest-ranked agent model here, `x-ai/grok-4.6` (rank 1 in `androidnative`), carries the same cliff at 200k.

That matters more for agents than for chat: an agent that has read a repository is over the line on most turns, so the higher number is the normal price and the row price is the exception. Both numbers are in `long_input_per_million` and `long_context_from` in the JSON and CSV. Source is the same catalog as every other column — the `pricing.overrides` array, which most published price tables drop.

## Same number, opposite answer

**Where exactly the line falls is not the same for every vendor, and the tables that publish these thresholds print one number for all of them.** Google and xAI both put the step at 200,000 prompt tokens, and they disagree about that token: a prompt of exactly 200,000 bills at the *cheap* rate on Google and at the *expensive* rate on xAI. Same number, opposite answer — the same prompt is under the line at one vendor and over it at the other. The other threshold in this table is a different number entirely, so nothing here carries over to it: OpenAI steps only above 272,000. Each of these was read off the vendor's own page rather than a catalog: [Google](https://ai.google.dev/gemini-api/docs/pricing) puts it in a sentence — “$2.00, prompts <= 200k tokens $4.00, prompts > 200k tokens” (read 2026-08-22); [xAI](https://docs.x.ai/docs/models) puts it in a sentence — “requests whose prompt reaches the listed token threshold” (read 2026-08-22); [OpenAI](https://developers.openai.com/api/docs/models/gpt-5.4) puts it in a sentence — “prompts with >272K input tokens are priced at 2x input and 1.5x output for the full session” (read 2026-08-22), while [the same vendor's own pricing page](https://developers.openai.com/api/docs/pricing) carries both readings at once — “gpt-5.4 (<272K context length)” and “≤272K input tokens” (a row label and the tooltip on the column heading above it, on one page, on opposite sides of that one token, read 2026-08-22).

**One model's cliff here cannot be reached any more, and the catalog still carries it.** The 2 `anthropic/claude-sonnet-4.5` rows above list a step at 200k, but its 1M context window was beta-only (`context-1m-2025-08-07`) and the beta was retired on 2026-04-30, after which requests over the standard 200k window return an error — so there is no prompt long enough to trigger the higher rate. The price is not wrong; the condition that would charge it is gone. Per [Anthropic's release notes](https://platform.claude.com/docs/en/release-notes/api) read 2026-08-22. We leave the rows in because that is what the catalog says, and flag it here rather than silently dropping it.

**One row here was checked against its vendor's own page, and it is wrong in every column and nearly right in the one that matters.** `deepseek/deepseek-v4-pro` is quoted from the catalog at $0.3969 in and $0.0331 cache-read. Calling `deepseek-v4-pro` direct, per [DeepSeek's pricing page](https://api-docs.deepseek.com/quick_start/pricing/) read 2026-08-23, the input price is **1.7× higher** off-peak and **3.3× higher** at peak — but the cache-read price is **1.5× *lower*** at the vendor off-peak. The two errors point in opposite directions, and because 95.6% of an agent's tokens are cache reads they very nearly cancel: $0.0536 per million at the vendor off-peak against $0.0501 for the catalog row, **107% of each other**. At peak they do not cancel — $0.1073, or 2.1× the catalog row.

So the headline list price on that row is off by a factor of 1.7 and the number an agent actually pays is off by 7% — in opposite directions, off-peak only. The giveaway that these are two different price lists is the ratio: the catalog lists output at exactly 2× input, DeepSeek charges 3×, and a vendor does not change that ratio per reseller. Peak is `01:00-04:00 UTC` and `06:00-10:00 UTC`; from 00:00 on 2026-08-23 Asia/Shanghai — 2026-08-22 16:00 UTC — weekends bill off-peak all day, and that weekend is bounded where the vendor says, not in UTC: it runs from 16:00 UTC Friday to 16:00 UTC Sunday. The English pricing page attaches `UTC` to the hours and leaves the weekday unqualified — *Monday through Friday* — while the Chinese page reads 北京时间周一至周五, the weekday in Beijing time. Both were re-read on 2026-08-23. That is where the eight-hour offset comes from, and why this table follows the Chinese wording. Both peak windows sit clear of the hours those two readings disagree over, so reading the weekday off the UTC clock lands on the right band today and starts lying the day the windows move — we checked rather than assumed, and it is a trap, not a leak. Two numbers a day and two sets a week, which no single scalar in any catalog, this one included, can carry.

**Of the 60 rows in this table, 1 was checked this way.** The other 59 are quoted from the catalog and not re-verified against their vendors; we are not claiming they are wrong, only that we have not looked.

**2 of the 3 models we checked against the vendor's own page are not in this table at all.** DeepSeek sells `deepseek-v4-flash` and `deepseek-v4-flash-vision-exp`; the catalog carries neither. A table that is wrong about a price hands you a number you can argue with — the row above is off by a factor of 1.7 and we caught it by dividing. A table that has never heard of a model hands you a clean empty instead, and code that looks a price up by exact model id turns that empty into a confident $0.00 in the same column as real costs, which is the harder failure to see because nothing looks broken ([one such tool, found this way](https://github.com/JPHutchins/code-review/issues/221)). The vendor prices these two identically today, so a tool that folded the longer name onto the shorter one would happen to be right — that is today's luck, not a rule, and nothing on the vendor's page undertakes to keep it true. Both are in the JSON under `vendor_checked`, flagged `in_catalog: false`, carrying the same peak windows and the same two UTC weekend edges as the row above.

Rows marked `batch` are the batch entries the catalog lists
separately — kept apart on purpose, because folding them in would
read as if a normal call cost half of what it does.

**The rank is the best one that model holds in any *agents* category,
and the category is in the table** so you can check it rather than
take our word for it. A rank without its category is unverifiable.

[JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv) · CC BY 4.0 · re-read daily

| $ / 1M at agent mix | $ in / 1M | $ out / 1M | Model | Context | Best agents rank | Written up |
| --- | --- | --- | --- | --- | --- | --- |
| **$0.0283** | $0.1875 | $0.9375 | [Gemini 3.7 Flash](https://openrouter.ai/google/gemini-3.7-flash:batch) `batch` | 1M | #2 agenticgamedev |  |
| **$0.0501** | $0.3969 | $0.7938 | [DeepSeek V4 Pro 0423](https://openrouter.ai/deepseek/deepseek-v4-pro) | 1M | #27 godotgamedev |  |
| **$0.0566** | $0.375 | $1.875 | [Gemini 3.6 Flash](https://openrouter.ai/google/gemini-3.6-flash:batch) `batch` | 1M | #7 agenticgamedev |  |
| **$0.0566** | $0.375 | $1.875 | [Gemini 3.7 Flash](https://openrouter.ai/google/gemini-3.7-flash) | 1M | #2 agenticgamedev |  |
| **$0.0731** | $0.30 | $1.20 | [MiniMax M3](https://openrouter.ai/minimax/minimax-m3) | 1M | #10 python-pptxslides | [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](https://xyzs996.github.io/llm-api-pricing/articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.html) |
| **$0.0731** | $0.30 | $1.20 | [MiniMax M3](https://openrouter.ai/minimax/minimax-m3:batch) `batch` | 524K | #10 python-pptxslides | [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](https://xyzs996.github.io/llm-api-pricing/articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.html) |
| **$0.0769** | $0.50 | $3.00 | [Gemini 3 Flash Preview](https://openrouter.ai/google/gemini-3-flash-preview) | 1M | #9 agenticslides |  |
| **$0.0918** | $0.45 | $2.25 | [Kimi K2.5](https://openrouter.ai/moonshotai/kimi-k2.5) | 262K | #9 godotgamedev |  |
| **$0.0979** | $0.40 | $1.75 | [GLM 4.7](https://openrouter.ai/z-ai/glm-4.7) | 204K | #27 androidnative |  |
| **$0.1131** | $0.75 | $3.75 | [Gemini 3.6 Flash](https://openrouter.ai/google/gemini-3.6-flash) | 1M | #7 agenticgamedev |  |
| **$0.1153** | $0.75 | $4.50 | [Gemini 3.5 Flash](https://openrouter.ai/google/gemini-3.5-flash:batch) `batch` | 1M | #3 agenticslides(python-pptx) |  |
| **$0.1218** | $0.50 | $2.00 | [GLM 4.6](https://openrouter.ai/z-ai/glm-4.6) | 204K | #13 godotgamedev |  |
| **$0.1396** | $0.875 | $7.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2:batch) `batch` | 400K | #18 godotgamedev |  |
| **$0.1448** | $0.60 | $1.92 | [GLM 5](https://openrouter.ai/z-ai/glm-5) | 204K | #16 godotgamedev |  |
| **$0.1508** | $1.00 | $5.00 | [Claude Sonnet 5](https://openrouter.ai/anthropic/claude-sonnet-5:batch) `batch` | 1M | #4 godotgamedev |  |
| **$0.1922** | $1.25 | $7.50 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4:batch) `batch` | 1.1M | #22 godotgamedev |  |
| **$0.1997** | $0.67 | $3.40 | [Kimi K2.7 Code](https://openrouter.ai/moonshotai/kimi-k2.7-code) | 262K | #7 htmlslides |  |
| **$0.2033** | $0.95 | $4.00 | [Kimi K2.6](https://openrouter.ai/moonshotai/kimi-k2.6) | 262K | #2 agentichtmlslides |  |
| **$0.2042** | $1.25 | $10.00 | [GPT-5.1-Codex](https://openrouter.ai/openai/gpt-5.1-codex) | 400K | #24 mobileapps |  |
| **$0.2067** | $1.25 | $4.25 | [Muse Spark 1.1](https://openrouter.ai/meta/muse-spark-1.1) | 1M | #8 agenticgamedev | [1.6 Billion Free Tokens Is a Compression Ratio, Not a Strategy](https://xyzs996.github.io/llm-api-pricing/articles/1-6-billion-free-tokens-is-a-compression-ratio-not-a.html) |
| **$0.2067** | $1.25 | $4.25 | [Muse Spark 1.2](https://openrouter.ai/meta/muse-spark-1.2) | 1M | #9 webapps |  |
| **$0.2197** | $0.966 | $3.036 | [GLM 5.1](https://openrouter.ai/z-ai/glm-5.1) | 204K | #3 agenticslides |  |
| **$0.2263** | $1.50 | $7.50 | [Claude Sonnet 4.5](https://openrouter.ai/anthropic/claude-sonnet-4.5:batch) `batch` | 1M | #26 mobileapps |  |
| **$0.2263** | $1.50 | $7.50 | [Claude Sonnet 4.6](https://openrouter.ai/anthropic/claude-sonnet-4.6:batch) `batch` | 1M | #4 mobileapps |  |
| **$0.2306** | $1.50 | $9.00 | [Gemini 3.5 Flash](https://openrouter.ai/google/gemini-3.5-flash) | 1M | #3 agenticslides(python-pptx) |  |
| **$0.232** | $0.95 | $4.00 | [Kimi K2.7 Code](https://openrouter.ai/moonshotai/kimi-k2.7-code:batch) `batch` | 262K | #7 htmlslides |  |
| **$0.2329** | $0.966 | $3.036 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2) | 1M | #10 agenticgamedev |  |
| **$0.2494** | $1.25 | $2.50 | [Grok 4.20](https://openrouter.ai/x-ai/grok-4.20) | 2M | #12 htmlslides |  |
| **$0.2494** | $1.25 | $2.50 | [Grok 4.3](https://openrouter.ai/x-ai/grok-4.3) | 1M | #9 pptxslides |  |
| **$0.2792** | $1.75 | $14.00 | [GPT-5.2](https://openrouter.ai/openai/gpt-5.2) | 400K | #18 godotgamedev |  |
| **$0.2792** | $1.75 | $14.00 | [GPT-5.2-Codex](https://openrouter.ai/openai/gpt-5.2-codex) | 400K | #19 godotgamedev |  |
| **$0.2792** | $1.75 | $14.00 | [GPT-5.3-Codex](https://openrouter.ai/openai/gpt-5.3-codex) | 400K | #24 godotgamedev |  |
| **$0.29** | $1.20 | $4.00 | [GLM 5V Turbo](https://openrouter.ai/z-ai/glm-5v-turbo) | 202K | #4 androidnative |  |
| **$0.3017** | $2.00 | $10.00 | [Claude Sonnet 5](https://openrouter.ai/anthropic/claude-sonnet-5) | 1M | #4 godotgamedev |  |
| **$0.3075** | $2.00 | $12.00 | [Gemini 3.1 Pro Preview](https://openrouter.ai/google/gemini-3.1-pro-preview) | 1M | #5 agentichtmlslides |  |
| **$0.3184** | $1.40 | $4.40 | [GLM 5.2](https://openrouter.ai/z-ai/glm-5.2:batch) `batch` | 1M | #10 agenticgamedev |  |
| **$0.3379** | $2.00 | $6.00 | [Qwen3.8 Max](https://openrouter.ai/qwen/qwen3.8-max) | 1M | #1 webapps |  |
| **$0.355** | $1.475 | $4.425 | [Qwen3.7 Max](https://openrouter.ai/qwen/qwen3.7-max) | 1M | #8 godotgamedev |  |
| **$0.3771** | $2.50 | $12.50 | [Claude Opus 4.5](https://openrouter.ai/anthropic/claude-opus-4.5:batch) `batch` | 200K | #11 mobileapps |  |
| **$0.3771** | $2.50 | $12.50 | [Claude Opus 4.6](https://openrouter.ai/anthropic/claude-opus-4.6:batch) `batch` | 1M | #6 mobileapps |  |
| **$0.3771** | $2.50 | $12.50 | [Claude Opus 4.7](https://openrouter.ai/anthropic/claude-opus-4.7:batch) `batch` | 1M | #1 agenticslides |  |
| **$0.3771** | $2.50 | $12.50 | [Claude Opus 4.8](https://openrouter.ai/anthropic/claude-opus-4.8:batch) `batch` | 1M | #2 agenticslides |  |
| **$0.3771** | $2.50 | $12.50 | [Claude Opus 5](https://openrouter.ai/anthropic/claude-opus-5:batch) `batch` | 1M | #3 fullstack |  |
| **$0.3843** | $2.50 | $15.00 | [GPT-5.4](https://openrouter.ai/openai/gpt-5.4) | 1.1M | #22 godotgamedev |  |
| **$0.3843** | $2.50 | $15.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5:batch) `batch` | 1.1M | #7 agenticslides |  |
| **$0.3857** | $2.00 | $6.00 | [Grok 4.5](https://openrouter.ai/x-ai/grok-4.5) | 500K | #3 godotgamedev |  |
| **$0.4525** | $3.00 | $15.00 | [Claude Sonnet 4.5](https://openrouter.ai/anthropic/claude-sonnet-4.5) | 1M | #26 mobileapps |  |
| **$0.4525** | $3.00 | $15.00 | [Claude Sonnet 4.6](https://openrouter.ai/anthropic/claude-sonnet-4.6) | 1M | #4 mobileapps |  |
| **$0.4525** | $3.00 | $15.00 | [Kimi K3](https://openrouter.ai/moonshotai/kimi-k3) | 1M | #1 mobileapps | [Beyond Token Pricing: How Indie Devs Should Really Evaluate AI Model Costs](https://xyzs996.github.io/llm-api-pricing/articles/ai-model-costs-beyond-per-token-pricing.html) |
| **$0.577** | $2.00 | $6.00 | [Grok 4.6](https://openrouter.ai/x-ai/grok-4.6) | 500K | #1 androidnative |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Fable 5](https://openrouter.ai/anthropic/claude-fable-5:batch) `batch` | 1M | #1 agenticgamedev |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Opus 4.5](https://openrouter.ai/anthropic/claude-opus-4.5) | 200K | #11 mobileapps |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Opus 4.6](https://openrouter.ai/anthropic/claude-opus-4.6) | 1M | #6 mobileapps |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Opus 4.7](https://openrouter.ai/anthropic/claude-opus-4.7) | 1M | #1 agenticslides |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Opus 4.8](https://openrouter.ai/anthropic/claude-opus-4.8) | 1M | #2 agenticslides |  |
| **$0.7542** | $5.00 | $25.00 | [Claude Opus 5](https://openrouter.ai/anthropic/claude-opus-5) | 1M | #3 fullstack |  |
| **$0.7687** | $5.00 | $30.00 | [GPT-5.5](https://openrouter.ai/openai/gpt-5.5) | 1.1M | #7 agenticslides |  |
| **$1.5084** | $10.00 | $50.00 | [Claude Fable 5](https://openrouter.ai/anthropic/claude-fable-5) | 1M | #1 agenticgamedev |  |
| — | $0.25 | $1.50 | [Gemini 3 Flash Preview](https://openrouter.ai/google/gemini-3-flash-preview:batch) `batch` | 1M | #9 agenticslides |  |
| — | $1.00 | $6.00 | [Gemini 3.1 Pro Preview](https://openrouter.ai/google/gemini-3.1-pro-preview:batch) `batch` | 1M | #5 agentichtmlslides |  |

**4 of these 60 have a write-up behind them.**
The empty cells are not an oversight — they are the models nobody
here has written about yet, which is also the honest answer to which
one to write about next.

## Put your own numbers in

Everything above is a rate card, read on one date. The three things that actually decide your bill — which side of a vendor's clock the call lands on, whether the prompt crosses a long-context threshold, and what share of your tokens are cache reads — depend on your usage, and no price column can carry them.

[The same table, as a calculator](https://xyzs996.github.io/llm-cost-calculator/) — one page, nothing to install, no account. It reads the JSON linked above, so it is never a day behind this table: it resolves the clock for the moment you are asking, applies the cliff to the request you describe instead of quoting the row, and lets you replace the cache-read share assumed above with the one your own logs say.

---

**Did this answer it?** [A star](https://github.com/xyzs996/llm-api-pricing) on the repository is the whole ask — it is what puts these in front of the next person looking; the data is CC BY and does not require starring.

**Does your own number disagree?** [This same table has a reply box](https://github.com/xyzs996/llm-api-pricing/discussions/42) — one line answers it. No template, no title, nothing to organise first.

**Want a figure that is not here yet?** [Say which metric, which provider, which unit](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=prices.md) — one required field, and the page you came from is already filled in.

**Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=prices.md) — corrections and counter-data are the point.

*Prices are quoted from OpenRouter's public catalog, which is the
source of every number in this table; the ranks are Design Arena's.
Neither is our measurement, and both move — the date above is when
this copy was last read, not when you are reading it.*

<script type="application/ld+json">
{"@context": "https://schema.org", "@type": "Dataset", "name": "Coding-agent model prices, next to their agent-arena rank", "description": "List price per million tokens for 60 models that have been ranked in an agent category of the Design Arena, with the context window, the best rank each one holds and the category it holds it in. Read from OpenRouter's public model catalog on 2026-08-23.", "url": "https://xyzs996.github.io/llm-api-pricing/prices.html", "license": "https://creativecommons.org/licenses/by/4.0/", "isAccessibleForFree": true, "creator": {"@type": "Person", "name": "xyzs996", "url": "https://github.com/xyzs996"}, "keywords": ["LLM pricing", "AI coding agents", "token costs", "model comparison", "cost per million tokens"], "variableMeasured": ["input price per million tokens", "output price per million tokens", "context window", "agent arena rank"], "distribution": [{"@type": "DataDownload", "encodingFormat": "application/json", "contentUrl": "https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json"}, {"@type": "DataDownload", "encodingFormat": "text/csv", "contentUrl": "https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv"}], "isBasedOn": "https://openrouter.ai/models", "dateModified": "2026-08-23"}
</script>
