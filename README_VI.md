# Tác nhân lập trình AI thực sự tốn bao nhiêu: 500 con số, mỗi con số kèm câu gốc và ngày

[English](./README.md) · [中文](./README_CN.md) · [Español](./README_ES.md) · [日本語](./README_JA.md) · [한국어](./README_KO.md) · **Tiếng Việt** · [Français](./README_FR.md) · [Deutsch](./README_DE.md) · [Русский](./README_RU.md) · [Bahasa Indonesia](./README_ID.md)

[![figures](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Ffigures.json)](https://github.com/xyzs996/llm-api-pricing/blob/main/figures.md) [![writeups](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fwriteups.json)](https://xyzs996.github.io/llm-api-pricing/) [![updated](https://img.shields.io/endpoint?url=https%3A%2F%2Fcdn.jsdelivr.net%2Fgh%2Fxyzs996%2Fllm-api-pricing%40main%2Fdata%2Fbadges%2Fupdated.json)](https://github.com/xyzs996/llm-api-pricing/releases) [![license](https://img.shields.io/badge/data-CC%20BY%204.0-blue)](https://github.com/xyzs996/llm-api-pricing/blob/main/LICENSE)

Một bộ dữ liệu mở. Mọi con số xuất hiện trong 54 ghi chép thực đo — giá, phần trăm, bội số, số token, thời lượng — đều được tách thành một dòng, **kèm nguyên câu chứa nó và ngày công bố**.

## Hôm nay chạy agent tốn bao nhiêu

59 mô hình được xếp hạng trong một hạng mục *agents* của Design Arena, kèm **giá niêm yết** cho mỗi triệu token — không phải hóa đơn của bạn: cache, batch và từng nhà cung cấp tính khác nhau. Lấy từ danh mục công khai của OpenRouter, đọc lần cuối ngày 2026-09-02. Ba mô hình rẻ nhất:

| $ in / 1M | $ out / 1M | Model | Best agents rank |
| --- | --- | --- | --- |
| $0.1875 | $0.9375 | Gemini 3.7 Flash `batch` | #4 androidnative |
| $0.25 | $1.50 | Gemini 3 Flash Preview `batch` | #9 agenticslides |
| $0.30 | $1.20 | MiniMax M3 | #10 python-pptxslides |

[Toàn bộ 59 mô hình](prices.md) · [JSON](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.json) · [CSV](https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/prices.csv)

**Cùng một con số, hai câu trả lời trái ngược.** Google và xAI đều chuyển sang mức giá cao ở 200,000 token đầu vào, nhưng một prompt đúng bằng 200,000 lại được tính giá rẻ ở Google và giá đắt ở xAI. Các bảng giá khác chỉ in con số rồi dừng ở đó. Bên nào tính theo cách nào, trích nguyên văn từ trang của chính nhà cung cấp kèm ngày kiểm tra: [same number, opposite answer](prices.md#same-number-opposite-answer) (tiếng Anh).

**Bảng trên là giá niêm yết. Không hóa đơn nào khớp với nó.** Thứ làm con số dịch chuyển là cache hit, lần thử lại, và phần ngữ cảnh bạn trả tiền để gửi đi hai lần — không catalog nào cho thấy những thứ đó. Có một bài đi tìm đúng khoảng chênh ấy: [tiền token thực sự chảy đi đâu](https://github.com/xyzs996/llm-api-pricing/discussions/37). Bài kết lại bằng câu hỏi duy nhất mà bảng này không trả lời được — **tháng trước bạn trả bao nhiêu, và bao nhiêu trong đó là ngữ cảnh bạn tiếc khi phải gửi lại?** Trang đó có ô trả lời; trang này thì không.

## Xem số trước

Những dòng dưới đây là **nguyên văn tiếng Anh**, không dịch: tách khỏi câu gốc thì con số không kiểm chứng được — `$1.43` có thể là mỗi triệu token, mỗi tháng, hoặc mỗi chỗ ngồi.

| Figure | The sentence it came from | Write-up |
| --- | --- | --- |
| `$35M` | Respond.io crossed $35M in annual recurring revenue last quarter by charging businesses for active customer conversations instead of agent seats; that one decision — switching from per-seat to per-customer billing — made the difference between flat growth and explosive scale. | [How Respond.io Built a $35M ARR Business by Billing AI Agents Per Active Customer (Not Per Agent)](articles/how-respond-io-built-a-35m-arr-business-by-billing-ai.md) |
| `$0.81` | Line up 40 models by the price on the card and the Chinese ones look like a rout: the median lists at $0.81 per million input tokens against $2.00 for the American ones, a gap of 2.47x. | [Chinese Models Are Not 2x Cheaper Once Your Agent Starts Caching](articles/chinese-models-are-not-2x-cheaper-once-your-agent-starts.md) |
| `20%` | Developers should build buffer time into their workflows when using Chinese AI coding tools, which is illustrated by the fact that one developer added 20% extra time to their coding sessions when using these tools because of the higher frequency of stability issues. | [The Hidden Costs of AI Coding Tools: What English Developers Don't Know](articles/the-hidden-costs-of-ai-coding-tools-what-english-developers.md) |
| `$22,000` | The organic channel that produced $22,000 a month is running at roughly half the traffic a million-dollar year would need, and it took three months to get there. | [The $22K-a-Month AI Tool That Never Bought a Single Ad](articles/the-22k-a-month-ai-tool-that-never-bought-a-single-ad.md) |
| `$24,000` | One watched competitor prices, one produced ad creative, one answered customer mail, and together they pulled 170,000 yuan a month out of them, somewhere near $24,000. | [Stop Using AI as a Chatbot: How to Build an Indie Workstation with Skills and Automation](articles/stop-using-ai-as-a-chatbot-how-to-build-an-indie.md) |
| `30%` | Agency Agents goes wider still, with 232 structured expert persona files, each carrying an identity, a workflow, delivery criteria and success metrics, compatible with 14 mainstream tools, and claiming an output-quality improvement of over 30%. | [Never Use a Model Where Code Can Decide](articles/never-use-a-model-where-code-can-decide.md) |
| `20%` | Automation of this shape has cut task delivery down to 20% of the manual effort in workflows like WorkBuddy. | [How to Turn Your Obsidian Vault Into an Autonomous AI Research Agent](articles/how-to-turn-your-obsidian-vault-into-an-autonomous-ai.md) |
| `$22,000` | Small and verified beats big and vague, and the comparison case makes the point better than I can: StoryShort, an AI short-video tool, matched in 3 months the cumulative revenue that the B2B tool useArtemis took 2 years to accumulate — around $22,000 in monthly Stripe-verified revenue against nearly $500,000 cumulative. | [Why Vanity Metrics Kill AI Startups: 700 Customers and 60,000 RMB From One Niche Account](articles/why-vanity-metrics-kill-ai-startups-700-customers-and-60.md) |
| `1000-token` | Still, I'd say the Pi base framework's 1000-token limit seems overstated. | [Stop Doing Manual DevOps: How I Use /loop and /hook to Automate My Daily Indie Hacker Tasks](articles/stop-doing-manual-devops-how-i-use-loop-and-hook-to.md) |
| `80%` | For instance, Claude Code's efficient programming capabilities, achieved by removing 80% of system prompts, which show these tools' potential, allow independent developers to automate document processing, data analysis, and other tasks, thus benefiting businesses by improving efficiency. | [Claude Code and Codex for Office Automation](articles/claude-code-and-codex-for-office-automation.md) |
| `$1.43` | The $1.43 and the $9.05 are both frontier models doing a job they were not specifically built for. | [The Two Best AI Code Reviewers Score the Same. One Costs $1.43 a Run, the Other $9.05.](articles/the-two-best-ai-code-reviewers-score-the-same-one-costs-1.md) |
| `$29` | Before writing a contract-comparison tool, one builder handled three to ten comparisons by hand at $29 a document, and only turned the routine into software once the same people kept coming back and paying for it. | [Debunking the Myth of Overnight Success in Micro-SaaS](articles/debunking-the-myth-of-overnight-success-in-micro-saas.md) |

[Toàn bộ 500 dòng](figures.md)

```
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.json
curl -s https://cdn.jsdelivr.net/gh/xyzs996/llm-api-pricing@main/data/figures.csv
```

Trường `published` là ngày bài đó được đăng, **không phải ngày mức giá đó còn hiệu lực**. Giá thay đổi liên tục, hãy đọc mỗi dòng theo đúng ngày của nó.

## Bài viết

Bài viết bằng **tiếng Anh**, ở đây: https://xyzs996.github.io/llm-api-pricing/ — có bảng số, trang theo chủ đề và trang theo nhà cung cấp. Nếu chỉ cần số, hai dòng `curl` bên trên là đủ.

## Nói một câu

- **Gắn sao cho kho này** để theo dõi cập nhật. Dữ liệu là CC BY: có sao hay không cũng không đổi điều bạn được làm với nó. Cái nó đổi là **người tiếp theo tìm những con số này** có tìm ra hay không: GitHub tính số sao khi xếp kết quả tìm kiếm và khi gợi ý các kho tương tự.
- **Số sai?** Nếu một mức giá đã đổi, hoặc bạn tự đo ra số khác — hãy mở một issue. Kho này sinh ra để làm việc đó. ([issue](https://github.com/xyzs996/llm-api-pricing/issues/new?template=correction.yml))
- **Thiếu con số bạn cần?** Nói rõ chỉ số nào, nhà cung cấp nào, đơn vị gì — chỉ một dòng. Biểu mẫu chỉ có một ô bắt buộc, và yêu cầu sẽ được đưa thành dòng mới. ([form](https://github.com/xyzs996/llm-api-pricing/issues/new?template=figure.yml))

---

CC BY 4.0: sao chép, đăng lại, chỉnh sửa, bán lại đều được. Một điều kiện: ghi nguồn, một liên kết về https://xyzs996.github.io/llm-api-pricing/ là đủ.
