# Berapa sebenarnya biaya agen coding AI: 559 angka, masing-masing dengan kalimat asal dan tanggalnya

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · **Bahasa Indonesia**

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Kumpulan data terbuka. Setiap angka dari 61 catatan lapangan — harga, persentase, kelipatan, jumlah token, dan durasi — ditarik menjadi satu baris, **lengkap dengan kalimat asalnya dan tanggal terbitnya**.

## Berapa biaya model agent hari ini

66 model yang masuk peringkat di salah satu kategori *agents* Design Arena, dengan **harga daftar** per juta token — bukan tagihan Anda: cache, batch, dan tiap penyedia menghitung berbeda. Dari katalog publik OpenRouter, terakhir dibaca 2026-09-19. Tiga termurah:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.09 | $0.36 | Solar Pro 4 | #33 webapps |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #8 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #11 htmlslides |

[Seluruh 66 model](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Satu angka, dua jawaban berlawanan.** Google dan xAI sama-sama naik ke tarif mahal pada 200,000 token input, tetapi prompt yang tepat 200,000 ditagih dengan tarif murah di Google dan tarif mahal di xAI. Tabel harga lain hanya mencetak angkanya lalu berhenti. Siapa menagih di sisi mana, dikutip dari halaman vendor itu sendiri lengkap dengan tanggal pengecekan: [same number, opposite answer](prices.md#same-number-opposite-answer) (bahasa Inggris).

**Tabel di atas adalah harga daftar. Tidak ada tagihan yang cocok dengannya.** Yang menggerakkan angkanya adalah cache hit, percobaan ulang, dan konteks yang Anda bayar dua kali — tidak satu pun terlihat di katalog. Ada satu tulisan yang mengejar selisih itu: [ke mana tagihan token sebenarnya pergi](https://github.com/xyzs996/llm-api-pricing/discussions/37). Tulisan itu ditutup dengan satu pertanyaan yang tak bisa dijawab tabel ini — **berapa yang Anda bayar bulan lalu, dan berapa bagian yang berupa konteks yang berat Anda kirim ulang?** Halaman itu punya kotak balasan; halaman ini tidak.

## Angkanya dulu

Baris-baris di bawah ini **dikutip apa adanya dalam bahasa Inggris**, tidak diterjemahkan: angka yang dilepas dari kalimatnya tidak bisa diperiksa — `$1.43` bisa berarti per juta token, per bulan, atau per kursi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `54%` | Through its internal multi-agent system, Sol achieves 54% higher token efficiency on agentic coding tasks compared to peer models, showing how strategic design choices can transform from a development challenge into a cost-saving advantage. | [The Hidden Costs of Over-Prompting in AI Coding: Lessons from Claude Code's Optimization](articles/the-hidden-costs-of-over-prompting-in-ai-coding-lessons.md) |
| `$10` | An AI image generation tool used Google Ads to boost its monthly paying subscribers from approximately 80 to over 500, maintaining a customer acquisition cost of around $10 per paying user. | [63 Billion Tokens in One Month, Spent Writing Google Ads for Amazon Sellers](articles/63-billion-tokens-in-one-month-spent-writing-google-ads-for.md) |
| `$1.43` | One GPT-5.6 Sol run might cost $1.43, while other models could cost upwards of $9.00 for the same task. | [Claude Code Can Model a Flange but Not a Freeform Surface: A Six-Step Handoff Checklist for Non-Code Agent Output](articles/claude-code-can-model-a-flange-but-not-a-freeform-surface-a.md) |
| `70%` | In that WeChat publication, 70% of the solo workflow was repetitive: organizing source material, checking drafts for AI-sounding prose, making covers, converting to HTML layout and publishing. | [How to Turn the Workflows You Won't Document Into Agent Skills](articles/how-to-turn-the-workflows-you-won-t-document-into-agent.md) |
| `72%` | Mobile developers report 72% of AI-generated code fails initial verification on real devices, and frontend developers waste 45% of their time debugging visual inconsistencies that only appear in production. | [The Real Pitfalls of AI Agent Development: From Code Generation to Functional Verification](articles/the-real-pitfalls-of-ai-agent-development-from-code.md) |
| `60%` | The recruitment automation tool hit a 60% efficiency gain after 28 rounds of iteration, but I’d argue that figure glosses over the real cost: dynamic page elements like shifting button positions and pop-ups demanded extra layers for state recognition and result verification. | [The AI Automation Ceiling: Why 60% Efficiency Doesn't Equal 20% Conversion](articles/the-ai-automation-ceiling-why-60-efficiency-doesn-t-equal.md) |
| `$35M` | Respond.io crossed $35M in annual recurring revenue last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to per-customer billing — made the difference between flat growth and explosive scale. | [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md) |
| `$0.81` | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. | [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) |
| `$63,000` | Jordan's success with Resellbot, a Micro-SaaS that automates Poshmark sharing, is a notable example: he earns $63,000 a month with just 30 lines of JavaScript. | [Automating Short Video Marketing with AI: A Low-Cost Growth Strategy for Developers](articles/automating-short-video-marketing-with-ai-a-low-cost-growth.md) |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `$22,000` | The organic channel that produced $22,000 a month is running at roughly half the traffic a million-dollar year would need, and it took three months to get there. | [The $22K-a-Month AI Tool That Never Bought a Single Ad](articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.md) |
| `$24,000` | One watched competitor prices, one produced ad creative, one answered customer mail, and together they pulled 170,000 yuan a month out of them, somewhere near $24,000. | [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](articles/stop-using-ai-as-a-chatbot-how-to-build-an-indie.md) |

[Seluruh 559 baris](figures.md)

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
