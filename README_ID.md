# Berapa sebenarnya biaya agen coding AI: 408 angka, masing-masing dengan kalimat asal dan tanggalnya

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · **Bahasa Indonesia**

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Kumpulan data terbuka. Setiap angka dari 49 catatan lapangan — harga, persentase, kelipatan, jumlah token, dan durasi — ditarik menjadi satu baris, **lengkap dengan kalimat asalnya dan tanggal terbitnya**.

## Berapa biaya model agent hari ini

60 model yang masuk peringkat di salah satu kategori *agents* Design Arena, dengan **harga daftar** per juta token — bukan tagihan Anda: cache, batch, dan tiap penyedia menghitung berbeda. Dari katalog publik OpenRouter, terakhir dibaca 2026-08-23. Tiga termurah:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #2 agenticgamedev |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Seluruh 60 model](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Satu angka, dua jawaban berlawanan.** Google dan xAI sama-sama naik ke tarif mahal pada 200,000 token input, tetapi prompt yang tepat 200,000 ditagih dengan tarif murah di Google dan tarif mahal di xAI. Tabel harga lain hanya mencetak angkanya lalu berhenti. Siapa menagih di sisi mana, dikutip dari halaman vendor itu sendiri lengkap dengan tanggal pengecekan: [same number, opposite answer](prices.md#same-number-opposite-answer) (bahasa Inggris).

**Tabel di atas adalah harga daftar. Tidak ada tagihan yang cocok dengannya.** Yang menggerakkan angkanya adalah cache hit, percobaan ulang, dan konteks yang Anda bayar dua kali — tidak satu pun terlihat di katalog. Ada satu tulisan yang mengejar selisih itu: [ke mana tagihan token sebenarnya pergi](https://github.com/xyzs996/llm-api-pricing/discussions/37). Tulisan itu ditutup dengan satu pertanyaan yang tak bisa dijawab tabel ini — **berapa yang Anda bayar bulan lalu, dan berapa bagian yang berupa konteks yang berat Anda kirim ulang?** Halaman itu punya kotak balasan; halaman ini tidak.

## Angkanya dulu

Baris-baris di bawah ini **dikutip apa adanya dalam bahasa Inggris**, tidak diterjemahkan: angka yang dilepas dari kalimatnya tidak bisa diperiksa — `$1.43` bisa berarti per juta token, per bulan, atau per kursi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `20%` | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. | [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md) |
| `$22,000` | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. | [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Claude Code and Codex for Office Automation](articles/claude-code-and-codex-for-office-automation.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |
| `90%` | 90% of developers still rely on manual prompt writing, while top performers use Skill Package to automate 80% of repetitive tasks, saving hours weekly. | [Best Practices for AI Agent Skill Management](articles/best-practices-for-ai-agent-skill-management.md) |
| `80%` | When the Claude Code team decided to slash 80% of their system prompts, most developers expected the model to lose its edge in complex engineering tasks. | [Why Stripping 80% of System Prompts Actually Improved Claude Code's Performance](articles/why-stripping-80-of-system-prompts-actually-improved-claude.md) |
| `$30` | With a budget as low as $30 per day, developers have reached an effective lead cost of $3 to $4. | [Stop Reading SimilarWeb Like a Traffic Dashboard — Read It Like a Feasibility Test](articles/stop-reading-similarweb-like-a-traffic-dashboard-read-it.md) |
| `$1,000` | Instead of chasing a 2.5% consumer conversion rate across unpredictable social channels, you sell a single $1,000 to $5,000 service package directly to one business owner — no massive ad campaigns, no hundreds of low-tier support tickets. | [How Indie Developers Are Building AI-Powered "Digital Landlords" and Renting Them Out for Monthly Cash Flow](articles/how-indie-developers-are-building-ai-powered-digital.md) |
| `40-second` | When an independent developer uses Agency Agents to set up a 40-second response cycle for e-commerce listings, they are building a feedback loop that reads market conditions and adjusts, which is what separates a timed automation from a script on a timer. | [Stop Chatting With AI: How I Use /loop and /hook to Automate My Indie Dev Workflow](articles/stop-chatting-with-ai-how-i-use-loop-and-hook-to-automate.md) |

[Seluruh 408 baris](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Kolom `published` adalah hari catatan itu terbit, **bukan hari harga tersebut masih berlaku**. Harga berubah terus — bacalah tiap baris menurut tanggalnya sendiri.

## Tulisannya

Tulisannya **berbahasa Inggris**, di sini: https://xyzs996.github.io/llm-api-pricing/ — lengkap dengan tabel angka, halaman per topik, dan halaman per penyedia. Kalau hanya butuh datanya, dua `curl` di atas sudah cukup.

## Katakan sesuatu

- **Beri bintang pada repositori ini** untuk mengikuti pembaruan. Datanya CC BY: ada atau tidak ada bintang, yang boleh Anda lakukan dengannya sama saja. Yang berubah adalah apakah **orang berikutnya yang mencari angka-angka ini** menemukannya: GitHub ikut menghitung jumlah bintang saat mengurutkan hasil pencarian dan saat menyarankan repositori sejenis.
- **Ada angka yang salah?** Kalau sebuah harga berubah, atau Anda mengukur sendiri dan hasilnya lain — buka issue. Untuk itulah repositori ini ada. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Angka yang Anda cari belum ada?** Sebutkan metriknya, penyedianya, dan satuannya — cukup satu baris. Formulir ini hanya punya satu isian wajib, dan permintaannya dijadikan baris baru. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: salin, terbitkan ulang, olah, jual. Satu syarat: sebutkan asalnya — tautan balik ke https://xyzs996.github.io/llm-api-pricing/ sudah cukup.
