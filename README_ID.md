# Berapa sebenarnya biaya agen coding AI: 901 angka, masing-masing dengan kalimat asal dan tanggalnya

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · **Bahasa Indonesia**

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Kumpulan data terbuka. Setiap angka dari 76 catatan lapangan — harga, persentase, kelipatan, jumlah token, dan durasi — ditarik menjadi satu baris, **lengkap dengan kalimat asalnya dan tanggal terbitnya**.

## Berapa biaya model agent hari ini

108 model yang masuk peringkat di salah satu kategori *agents* Design Arena, dengan **harga daftar** per juta token — bukan tagihan Anda: cache, batch, dan tiap penyedia menghitung berbeda. Dari katalog publik OpenRouter, terakhir dibaca 2026-11-21. Tiga termurah:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #16 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.0399 | $0.0784 | GLM 5.3 Flash | #16 pdf |

[Seluruh 108 model](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Satu angka, dua jawaban berlawanan.** Google dan xAI sama-sama naik ke tarif mahal pada 200,000 token input, tetapi prompt yang tepat 200,000 ditagih dengan tarif murah di Google dan tarif mahal di xAI. Tabel harga lain hanya mencetak angkanya lalu berhenti. Siapa menagih di sisi mana, dikutip dari halaman vendor itu sendiri lengkap dengan tanggal pengecekan: [same number, opposite answer](prices.md#same-number-opposite-answer) (bahasa Inggris).

**Tabel di atas adalah harga daftar. Tidak ada tagihan yang cocok dengannya.** Yang menggerakkan angkanya adalah cache hit, percobaan ulang, dan konteks yang Anda bayar dua kali — tidak satu pun terlihat di katalog. Ada satu tulisan yang mengejar selisih itu: [ke mana tagihan token sebenarnya pergi](https://github.com/xyzs996/llm-api-pricing/discussions/37). Tulisan itu ditutup dengan satu pertanyaan yang tak bisa dijawab tabel ini — **berapa yang Anda bayar bulan lalu, dan berapa bagian yang berupa konteks yang berat Anda kirim ulang?** Halaman itu punya kotak balasan; halaman ini tidak.

## Angkanya dulu

Baris-baris di bawah ini **dikutip apa adanya dalam bahasa Inggris**, tidak diterjemahkan: angka yang dilepas dari kalimatnya tidak bisa diperiksa — `$1.43` bisa berarti per juta token, per bulan, atau per kursi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$3` | One user running three agents for email, calendar, and research put their monthly bill at $3–5 on DeepSeek V4 Flash against $200–260 on Opus 4.7, and described the quality gap as small rather than night-and-day. | [The Cheap Model Is 50x Cheaper Until It Gets Banned: Real Per-Token Costs vs. What Actually Breaks](articles/the-cheap-model-is-50x-cheaper-until-it-gets-banned-real.md) |
| `$7` | One developer launched a SaaS and waited 2.5 months for the first paying customer, a $7 sale, and reported that the customer found the product through Google organic search. | [Your Channel Report Is Lying — 1,215 of 1,463 Branded Search Clicks Came From Somewhere Else](articles/your-channel-report-is-lying-1-215-of-1-463-branded-search.md) |
| `$3` | Another framing: Kimi K3 at $3/$15 per million tokens against Fable 5 at $10/$50, with intelligence index scores of 59.7 and 62.1. | [Running DeepSeek V4-Pro Inside Claude Code: A Cost-and-Failure Checklist for Cheap Chinese Coding Models](articles/running-deepseek-v4-pro-inside-claude-code-a-cost-and.md) |
| `$0.181` | Sources are already presenting $0.181 per successful task next to a coding score of 96.0, side by side, which is the shape the conversation is heading toward. | [Your LLM Bill Is 2x the Sticker Price: Peak-Hour Pricing and the 272K Token Cliff](articles/your-llm-bill-is-2x-the-sticker-price-peak-hour-pricing-and.md) |
| `$3` | For scale on what a real month looks like: three agents doing email, calendar, and research ran about $3–5 per month on DeepSeek V4 Flash against $200–260 on Opus 4.7, with what the user described as a small quality gap. | [The Sticker Price Said 9x Cheaper. My Bill at Peak Hour Didn't Move.](articles/the-sticker-price-said-9x-cheaper-my-bill-at-peak-hour-didn.md) |
| `60%` | For rider recruitment, this meant focusing on repetitive actions like resume browsing and initial outreach, which is where the team, using Codex, developed a tool that iterated 28 times before it was able to achieve a 60% efficiency increase in public domain recruitment tasks — the same repetitive work of resume browsing and initial outreach that had been the focus from the start. | [The Hidden Cost of AI Automation: Turning Human Instincts into Rules](articles/the-hidden-cost-of-ai-automation-turning-human-instincts.md) |
| `$10` | OpenCode Go users pay $10/month and receive $60 of DeepSeek V4.1 Flash usage credit that never expires — up from the original $30/month allotment, upgraded in Phase 2 to $60 and kept long-term. | [The Listed Price Is a Lie: What DeepSeek's Peak/Off-Peak Pricing, Rate-Limit Windows, and "Permanent" Credits Actually Cost Per Task](articles/the-listed-price-is-a-lie-what-deepseek-s-peak-off-peak.md) |
| `$80` | In one documented case, a developer spent roughly 4 hours of total human time over 5 days — reviewing, pivoting, and debugging — while an AI agent built the SaaS product, with API token costs for the entire build coming in at $80–120. | [Shipping a SwiftUI App with AI: Where It Shines and Where It Crashes](articles/shipping-a-swiftui-app-with-ai-where-it-shines-and-where-it.md) |
| `$3` | The Reddit forecast was $3-5 a month for three light agents, and GLM-4-Flash's 20M free tokens don't expire, while DeepSeek's sign-up grant of 10M tokens (2026-05-02 article) was valid for only 30 days. | [What DeepSeek V4.1 Flash Really Costs Per Month: A Five-Step Checklist](articles/what-deepseek-v4-1-flash-really-costs-per-month-a-five-step.md) |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |

[Seluruh 901 baris](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Kolom `published` adalah hari catatan itu terbit, **bukan hari harga tersebut masih berlaku**. Harga berubah terus — bacalah tiap baris menurut tanggalnya sendiri.

## Tulisannya

Tulisannya **berbahasa Inggris**, di sini: https://spectracodeai.com/ — lengkap dengan tabel angka, halaman per topik, dan halaman per penyedia. Kalau hanya butuh datanya, dua `curl` di atas sudah cukup.

## Katakan sesuatu

- **Beri bintang pada repositori ini** untuk mengikuti pembaruan. Datanya CC BY: ada atau tidak ada bintang, yang boleh Anda lakukan dengannya sama saja. Yang berubah adalah apakah **orang berikutnya yang mencari angka-angka ini** menemukannya: GitHub ikut menghitung jumlah bintang saat mengurutkan hasil pencarian dan saat menyarankan repositori sejenis.
- **Ada angka yang salah?** Kalau sebuah harga berubah, atau Anda mengukur sendiri dan hasilnya lain — buka issue. Untuk itulah repositori ini ada. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Angka yang Anda cari belum ada?** Sebutkan metriknya, penyedianya, dan satuannya — cukup satu baris. Formulir ini hanya punya satu isian wajib, dan permintaannya dijadikan baris baru. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: salin, terbitkan ulang, olah, jual. Satu syarat: sebutkan asalnya — tautan balik ke https://spectracodeai.com/ sudah cukup.
