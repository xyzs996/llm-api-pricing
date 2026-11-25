# Tác nhân lập trình AI thực sự tốn bao nhiêu: 950 con số, mỗi con số kèm câu gốc và ngày

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · **Tiếng Việt** · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://spectracodeai.com/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Một bộ dữ liệu mở. Mọi con số xuất hiện trong 78 ghi chép thực đo — giá, phần trăm, bội số, số token, thời lượng — đều được tách thành một dòng, **kèm nguyên câu chứa nó và ngày công bố**.

## Hôm nay chạy agent tốn bao nhiêu

110 mô hình được xếp hạng trong một hạng mục *agents* của Design Arena, kèm **giá niêm yết** cho mỗi triệu token — không phải hóa đơn của bạn: cache, batch và từng nhà cung cấp tính khác nhau. Lấy từ danh mục công khai của OpenRouter, đọc lần cuối ngày 2026-11-25. Ba mô hình rẻ nhất:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.023 | $0.068 | GLM 5.3 Flash `batch` | #23 pdf |
| $0.035 | $0.149 | DeepSeek V4.1 Flash 1017 `batch` | #9 spreadsheet |
| $0.05 | $0.20 | Solar Mini 4 | #47 pdf |

[Toàn bộ 110 mô hình](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Cùng một con số, hai câu trả lời trái ngược.** Google và xAI đều chuyển sang mức giá cao ở 200,000 token đầu vào, nhưng một prompt đúng bằng 200,000 lại được tính giá rẻ ở Google và giá đắt ở xAI. Các bảng giá khác chỉ in con số rồi dừng ở đó. Bên nào tính theo cách nào, trích nguyên văn từ trang của chính nhà cung cấp kèm ngày kiểm tra: [same number, opposite answer](prices.md#same-number-opposite-answer) (tiếng Anh).

**Bảng trên là giá niêm yết. Không hóa đơn nào khớp với nó.** Thứ làm con số dịch chuyển là cache hit, lần thử lại, và phần ngữ cảnh bạn trả tiền để gửi đi hai lần — không catalog nào cho thấy những thứ đó. Có một bài đi tìm đúng khoảng chênh ấy: [tiền token thực sự chảy đi đâu](https://github.com/xyzs996/llm-api-pricing/discussions/37). Bài kết lại bằng câu hỏi duy nhất mà bảng này không trả lời được — **tháng trước bạn trả bao nhiêu, và bao nhiêu trong đó là ngữ cảnh bạn tiếc khi phải gửi lại?** Trang đó có ô trả lời; trang này thì không.

## Xem số trước

Những dòng dưới đây là **nguyên văn tiếng Anh**, không dịch: tách khỏi câu gốc thì con số không kiểm chứng được — `$1.43` có thể là mỗi triệu token, mỗi tháng, hoặc mỗi chỗ ngồi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$0.87` | If you think in dollars, another data point puts DeepSeek V4 at $0.87 per million output tokens, against GLM-5.2 at $4.4 and Kimi K3 at $15, while a third puts V4-Flash at $0.028 per million tokens, which is an order of magnitude off the previous figures. | [I Ran DeepSeek V4-Pro and GLM-4-Flash in the Same Coding Agent. One Took 24 Minutes and Deployed Without Asking.](articles/i-ran-deepseek-v4-pro-and-glm-4-flash-in-the-same-coding.md) |
| `$0.26` | DeepSeek V3.2 under the OpenClaw framework comes in at $0.26 per million input tokens and $0.38 output, the lowest-cost model in that particular comparison, while MiniMax M2.7 sits at $0.30 input and $1.20 output with a 204.8K context window, built for coding and agent workflows. | [The Same Model Costs 2x More at 10am — Three Pricing Cliffs That Blow Up Your Coding Agent's Bill](articles/the-same-model-costs-2x-more-at-10am-three-pricing-cliffs.md) |
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

[Toàn bộ 950 dòng](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Trường `published` là ngày bài đó được đăng, **không phải ngày mức giá đó còn hiệu lực**. Giá thay đổi liên tục, hãy đọc mỗi dòng theo đúng ngày của nó.

## Bài viết

Bài viết bằng **tiếng Anh**, ở đây: https://spectracodeai.com/ — có bảng số, trang theo chủ đề và trang theo nhà cung cấp. Nếu chỉ cần số, hai dòng `curl` bên trên là đủ.

## Nói một câu

- **Gắn sao cho kho này** để theo dõi cập nhật. Dữ liệu là CC BY: có sao hay không cũng không đổi điều bạn được làm với nó. Cái nó đổi là **người tiếp theo tìm những con số này** có tìm ra hay không: GitHub tính số sao khi xếp kết quả tìm kiếm và khi gợi ý các kho tương tự.
- **Số sai?** Nếu một mức giá đã đổi, hoặc bạn tự đo ra số khác — hãy mở một issue. Kho này sinh ra để làm việc đó. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Thiếu con số bạn cần?** Nói rõ chỉ số nào, nhà cung cấp nào, đơn vị gì — chỉ một dòng. Biểu mẫu chỉ có một ô bắt buộc, và yêu cầu sẽ được đưa thành dòng mới. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: sao chép, đăng lại, chỉnh sửa, bán lại đều được. Một điều kiện: ghi nguồn, một liên kết về https://spectracodeai.com/ là đủ.
