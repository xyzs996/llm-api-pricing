# Berapa sebenarnya biaya agen coding AI: 709 angka, masing-masing dengan kalimat asal dan tanggalnya

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · [Tiếng Việt](./README_VI.md) · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · **Bahasa Indonesia**

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Kumpulan data terbuka. Setiap angka dari 67 catatan lapangan — harga, persentase, kelipatan, jumlah token, dan durasi — ditarik menjadi satu baris, **lengkap dengan kalimat asalnya dan tanggal terbitnya**.

## Berapa biaya model agent hari ini

83 model yang masuk peringkat di salah satu kategori *agents* Design Arena, dengan **harga daftar** per juta token — bukan tagihan Anda: cache, batch, dan tiap penyedia menghitung berbeda. Dari katalog publik OpenRouter, terakhir dibaca 2026-11-08. Tiga termurah:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.006 | $0.50 | DeepSeek V4.1 Flash 1017 | #5 spreadsheet |
| $0.006 | $6.80 | GLM 5.2 | #7 pdf |
| $0.011 | $0.20 | DeepSeek V4.1 Flash 1017 `batch` | #5 spreadsheet |

[Seluruh 83 model](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Satu angka, dua jawaban berlawanan.** Google dan xAI sama-sama naik ke tarif mahal pada 200,000 token input, tetapi prompt yang tepat 200,000 ditagih dengan tarif murah di Google dan tarif mahal di xAI. Tabel harga lain hanya mencetak angkanya lalu berhenti. Siapa menagih di sisi mana, dikutip dari halaman vendor itu sendiri lengkap dengan tanggal pengecekan: [same number, opposite answer](prices.md#same-number-opposite-answer) (bahasa Inggris).

**Tabel di atas adalah harga daftar. Tidak ada tagihan yang cocok dengannya.** Yang menggerakkan angkanya adalah cache hit, percobaan ulang, dan konteks yang Anda bayar dua kali — tidak satu pun terlihat di katalog. Ada satu tulisan yang mengejar selisih itu: [ke mana tagihan token sebenarnya pergi](https://github.com/xyzs996/llm-api-pricing/discussions/37). Tulisan itu ditutup dengan satu pertanyaan yang tak bisa dijawab tabel ini — **berapa yang Anda bayar bulan lalu, dan berapa bagian yang berupa konteks yang berat Anda kirim ulang?** Halaman itu punya kotak balasan; halaman ini tidak.

## Angkanya dulu

Baris-baris di bawah ini **dikutip apa adanya dalam bahasa Inggris**, tidak diterjemahkan: angka yang dilepas dari kalimatnya tidak bisa diperiksa — `$1.43` bisa berarti per juta token, per bulan, atau per kursi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$3` | Kimi K3 is often cited as a premium model, yet at $3 input / $15 output per million tokens its API cost is only 30% of Anthropic Fable 5's $10 / $50, while its intelligence index of 59.7 sits within 3 points of Fable 5's 62.1 <!-- [doc_41a4c25e26655d9dc1ddafedda28748b] -->. | [The "10x Cheaper" Trap: How to Read AI Coding Costs](articles/the-10x-cheaper-trap-how-to-read-ai-coding-costs.md) |
| `$15` | Kimi K3 charges $15 per million output tokens, DeepSeek V4 at $0.87, and GLM-5.2 at $4.40—far below Anthropic Fable 5’s $50. | [This Open-Source Code Review Tool Beats Claude — With 1/9 the Tokens](articles/this-open-source-code-review-tool-beats-claude-with-1-9-the.md) |
| `$1,000` | But this only works because there’s still demand for Pinterest as a traffic source—especially in niches like home decor, DIY, and personal finance—where one content site, Home Office Setup Guide, earned $1,000 in AdSense in 30 days using only Pinterest and YouTube to drive 5,000 visits, which shows that even with limited channels, targeted traffic from platforms like Pinterest can be monetized effectively when aligned with high-engagement niches that attract consistent user interest and advertiser support. | [How a One-Feature Tool Hit $16K MRR by Automating Pinterest Posts](articles/how-a-one-feature-tool-hit-16k-mrr-by-automating-pinterest.md) |
| `$7,600` | An AI crypto trading bot reportedly made $7,600 in a week.” That line gets clicks. | [How a Multi-Agent AI System Made $7,600 in 7 Days for Under $100 in API Costs](articles/how-a-multi-agent-ai-system-made-7-600-in-7-days-for-under.md) |
| `$5` | The tool runs on a $5/month VPS using Docker. | [How Alibaba’s Open Code Review Slashed AI Code Review Costs by 90% — And What It Means for Independent Developers](articles/how-alibaba-s-open-code-review-slashed-ai-code-review-costs.md) |
| `$0.028` | With DeepSeek V4 Flash priced at just $0.028 per million tokens, developers can assign lightweight tasks like boilerplate generation or syntax checking to this model, reserving higher-cost models for nuanced logic or debugging. | [Bypass Codex Rate Limits: The Local Proxy Path to 70% Cost Savings](articles/bypass-codex-rate-limits-the-local-proxy-path-to-70-cost.md) |
| `40%` | 40% of review tasks needed manual backfill, costing about 15 extra minutes each time. | [Your AI Didn't Misread Your Code by Accident. You Handed It the Wrong Context.](articles/your-ai-didn-t-misread-your-code-by-accident-you-handed-it.md) |
| `$1.43` | The price spread is wide even among the Western flagships, which becomes obvious on ReactBench, where one run with GPT 5.6 Sol costs about $1.43 while one run with Fable 5 costs $9.05, which means that a single Fable 5 run comes to a bit more than six times as much as the GPT 5.6 Sol run does. | [Stop Hitting the 5-Hour Limit: Routing Your IDE’s AI Requests to Local Models](articles/stop-hitting-the-5-hour-limit-routing-your-ide-s-ai.md) |
| `20%` | I’d argue that building these decoupling layers is the only way to survive the shift toward platforms like ChatGPT Work, where non-programming users are expected to jump from 20% to 60% of the total user base within a year. | [Four Circuit Breakers Every Unattended AI Pipeline Needs (Learned the Expensive Way)](articles/four-circuit-breakers-every-unattended-ai-pipeline-needs.md) |
| `$170,000` | In contrast to one-off projects, micro-automation tools excel at addressing single, high-frequency pain points A former Alibaba P8, after facing three months of unsuccessful job applications, pivoted to building AI software that has five core features—including scheduled automation and skill packages—to generate $170,000 in monthly revenue The data from these 27 successful cases reveals that the most effective tools prioritize "scheduled automation," which can reduce manual task time from several hours each day to zero minutes. | [Stop Building Custom AI Agents: How to Earn $63K/Month with Micro-Automation](articles/stop-building-custom-ai-agents-how-to-earn-63k-month-with.md) |
| `80%` | The machine runs for about 11 minutes, and human review takes 10–20 minutes, leading to a total time reduction of ~80%–90%. | [I built a WeChat Official Account writing Agent that cuts work time by 80% — here’s the workflow filter and tool combo I used](articles/i-built-a-wechat-official-account-writing-agent-that-cuts.md) |
| `54%` | Through its internal multi-agent system, Sol achieves 54% higher token efficiency on agentic coding tasks compared to peer models, showing how strategic design choices can transform from a development challenge into a cost-saving advantage. | [The Hidden Costs of Over-Prompting in AI Coding: Lessons from Claude Code's Optimization](articles/the-hidden-costs-of-over-prompting-in-ai-coding-lessons.md) |

[Seluruh 709 baris](figures.md)

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
