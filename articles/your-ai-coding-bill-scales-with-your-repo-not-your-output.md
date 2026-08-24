# Your AI Coding Bill Scales With Your Repo, Not Your Output

![Your AI Coding Bill Scales With Your Repo, Not Your Output](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/assets/cards/a/your-ai-coding-bill-scales-with-your-repo-not-your-output.png)

*Written with AI assistance. Figures without a traceable source were cut before publishing.*

*The same piece is posted [as a thread on GitHub](https://github.com/xyzs996/llm-api-pricing/discussions/56) — that copy has a reply box under it, and this one does not.*

Most people budgeting for a coding assistant reason about it the way they reason about a printer, as though the cost tracked how much comes out. It does not, and the mismatch is why the bill surprises people in month three rather than month one. The dominant consumption in an AI coding workflow is the repeated reading and re-processing of project context, not the length of the code the model writes, and once you see that clearly a lot of otherwise confusing advice about file structure and rules files turns out to be cost engineering wearing a different hat.

## The Loop Feeds Itself

Here is the mechanism, and it is simpler than the pricing pages make it look.

The model produces code and commands, which is output. Then the test results come back, the error messages come back, and every edit made earlier in the session is still sitting there, and all of that becomes input on the next turn. The conversation is not a series of independent questions; it is one growing document that gets re-read every time you press enter. Which means the thing driving your spend is the size of what has to be carried forward, and the size of what has to be carried forward is mostly a property of your project rather than a property of your prompt.

Bigger repo. More to read. More consumed, every single turn.

I think this explains the specific shape of the surprise people report, where the same assistant that felt nearly free during a weekend prototype becomes expensive on a real codebase doing exactly the same kind of work. Nothing changed about how you use it. The denominator changed.

## Three Thresholds, Not a Slope

The consumption does not rise smoothly either. There are 3 recognizable thresholds, and they correspond to the role the AI is playing rather than to how much you are typing.

The first is cloud conversation, where you paste a snippet into a chat window and ask a question. Cheap, bounded, and where most people's mental model of cost was formed. The second is a local project, where Cursor or Claude Code is reading your actual files, running your actual tests, and holding the state of a real task across many turns. The third is business automation delivery, where the thing runs against production systems and the loop includes external data, failures and retries.

Each step up multiplies what has to be in context, and the jump is not gradual.

The practical consequence is that budgeting from your prototype experience underestimates the next stage by a lot, and I'd argue the useful planning question is not "what does this cost per month" but "which threshold am I about to cross." Crossing one is a decision. It usually gets made by accident.

## Context Management Is the Lever

If the cost is context, then managing context is the optimization, and the concrete version of that advice is unglamorous.

Write the global rules and the project rules into files. Not into a conversation, into files that live in the repository, so that any assistant in any window on any day starts with the same picture of what this project is, what it does not do, which conventions apply and which constraints are non-negotiable. The immediate benefit people notice is consistency across sessions. The benefit they notice later is that the assistant stops re-deriving the same background from scratch, which is precisely the re-reading that was costing money.

A rules file is cheaper than re-explaining. Every time.

There is a measurable version of this worth knowing about. Alibaba's Open Code Review was benchmarked against general-purpose agents on 200 real pull requests drawn from 50 open-source repositories across 10 languages, and it scored higher on accuracy and F1 while consuming roughly one-ninth the tokens, a 9x gap on identical work. Read that as a statement about context rather than about model quality, because both sides were reviewing the same diffs; the difference is how much surrounding material each one had to pull in to form an opinion.

There is a quality argument for the same practice that is at least as strong as the cost argument. An assistant that misbehaves is very often responding to a requirement nobody wrote down, an interface convention that exists only in someone's habits, or a constraint that was mentioned once in a conversation that has since been compacted away. Putting those in a file does not just save tokens; it removes the ambiguity that was generating the wrong output in the first place.

## Small Steps Beat Big Asks, and Not for the Reason You Think

The other habit that changes both cost and quality is scope per request.

Ask for a whole e-commerce site and you get a pile that does not work. Ask for the product list page with fake data standing in for the backend, and you get something usable. That is the first principle of working with these tools, and the reason it works is mechanical rather than motivational: the smaller the unit of work, the higher the model's hit rate, and the easier it is to locate the mistake when there is one.

Accept at every step. A rejected small change costs you one small change. A rejected large change costs you the whole session's context, because now you are debugging something you did not write, holding a conversation that has already grown large, and paying to re-read all of it on every attempt at a fix.

That last part is the cost connection people miss. Rework is not merely annoying; rework is the most expensive kind of token consumption available, since it re-processes an already-bloated context repeatedly in order to fix something that a smaller request would have gotten right the first time.

## The Model Sets the Floor

Which brings up the decision that looks like a cost lever and is usually the opposite.

Use the flagship model from whichever vendor you prefer when you are writing code, meaning the current top-tier Claude, GPT or Gemini release rather than the cheap tier underneath it. The same tool with a different model behind it produces genuinely different results, and the money saved on a lower subscription tends to come back as double the rework time. The tool is the shell; the model is the engine. Honestly, this is the one place where I would spend without much analysis, because the failure mode of a weaker model is not that it produces less, it is that it produces plausible output you then have to pay to discover is wrong.

And keep the secrets out of it entirely. Sensitive values belong in a `.env` file, with nothing sensitive in the code the assistant reads or writes. That is a security baseline rather than a cost one, but it belongs in the same conversation, because the same context that is expensive to carry is also context you may not want in someone else's logs.

## What I Would Actually Do

Four things, in rough order of payback.

Put the project rules in a file before the project gets big, since retrofitting them is the same work done later against more code. Keep requests small enough that acceptance is obvious, because acceptance is what stops a bad turn from contaminating everything after it. Pay for the good model, on the grounds that the cheap one bills you in a currency that does not show up on the invoice. And know which of the 3 thresholds you are standing on, particularly before you promise anyone a monthly number.

One more thing worth saying about tooling, briefly. Hosted platforms like Lovable are the fastest way to get a first result, and moving to Cursor or Claude Code, where the code lives in your own Git repository, is what makes the project survivable past the prototype, since exporting from a hosted platform later is reliably more painful than people expect.

The bill is not a printing charge. It is a rent on how much your assistant has to remember, and almost everything you can do about it comes down to making that memory smaller and more deliberate.

*Also readable on [Telegraph](https://telegra.ph/Your-AI-Coding-Bill-Scales-With-Your-Repo-Not-Your-Output-08-23).*


---

**Read next**

- [Your Agent Writes Code Faster Than Anyone Can Review It](your-agent-writes-code-faster-than-anyone-can-review-it.md)
- [The Token Cost War: Why Price per Million Tokens Now Decides the AI Market](the-token-cost-war-why-price-per-million-tokens-now-decides.md)
- [Debunking the Myth of Overnight Success in Micro-SaaS](debunking-the-myth-of-overnight-success-in-micro-saas.md)

[All 53 write-ups](../README.md)

The 1 figures in this piece — each with the sentence it came from — are in [the figures table](../figures.md), alongside 478 more, as JSON and CSV.

Topics: [Artificial Intelligence](../topics/artificial-intelligence.md) · [AI](../topics/ai.md)


---

*Part of [llm-api-pricing](https://github.com/xyzs996/llm-api-pricing) — field notes on AI coding
agents.*

**Did this save you an afternoon?** [A star](https://github.com/xyzs996/llm-api-pricing)
on the repository is the whole ask — it is what puts these in front of the next
person looking; the data is CC BY and does not require starring.

**One thing this piece could not settle:** How many files are in your largest repo? Reply with a number. [The reply box is on the thread copy of this piece](https://github.com/xyzs996/llm-api-pricing/discussions/56).

**Want a figure
that is not in here yet?** Say which metric, which provider, which unit — [in one
line](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml&came_from=articles%2Fyour-ai-coding-bill-scales-with-your-repo-not-your-output.md). One required field, and the page you came from is already filled
in. **Got a better number?** [Open an issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml&where=articles%2Fyour-ai-coding-bill-scales-with-your-repo-not-your-output.md&title=%5Bcorrection%5D+Your+AI+Coding+Bill+Scales+With+Your+Repo%2C+Not+Your+Output) — that form knows
which write-up you came from too; corrections and counter-data are the point.
