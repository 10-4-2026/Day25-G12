---
artifact: 1 — FINAL kế hoạch giải pháp
bai-tap: 2 — Thiết kế giải pháp
phase: Chọn rủi ro + chọn tầng + chọn demo + chốt 3 lớp giải pháp
time: 11:00-11:55
input: 00-context.md + 01-test-set-review/3-FINAL-test-set-eval-plan.md
nop-cuoi: Có — file cuối Bài 2
---

# 1 — FINAL: Kế hoạch giải pháp

File này ghi lại quyết định chính của Bài 2:

- Rủi ro nào được chọn.
- Vì sao rủi ro đó quan trọng.
- Nguyên nhân gốc là gì.
- Nhóm sẽ xây 3 lớp giải pháp nào.
- Mỗi lớp dùng demo gì.

## Thông tin nhóm

- **Chủ đề**: Trợ lý đặt vé và chăm sóc khách hàng hàng không
- **Thành viên**: Nhóm Day25-G12
- **Ngày**: 2026-05-13

---

## Phần A — Chọn rủi ro và tầng giải pháp

### Rủi ro chính được chọn

- **ID tình huống**: T-01
- **Mô tả ngắn**: Khi người dùng hỏi về chính sách giảm giá tang lễ hoặc các trường hợp khẩn cấp, AI có xu hướng bịa ra các ngoại lệ hoặc chính sách không tồn tại (hallucination), gây thiệt hại tài chính và lỡ việc cho khách hàng.
- **Mức độ**: Nặng
- **Điểm rủi ro**: 20
- **Vì sao chọn tình huống này**: Đây là rủi ro có thực tế xảy ra (vụ Air Canada), gây hậu quả pháp lý trực tiếp cho doanh nghiệp và thiệt hại tài chính không thể đảo ngược cho khách hàng nếu họ tin và mua vé dựa trên thông tin sai.

### Tìm nguyên nhân gốc

- [x] AI đoán khi không biết (Hallucination).
- [x] Giao diện khiến người dùng tin quá mức (Chatbot giống người, thiếu cảnh báo).
- [x] Thiếu quy trình kiểm soát khi trả lời về chính sách tài chính nhạy cảm.

### Bảng nối nguyên nhân với tầng sửa

| Nguyên nhân gốc | Tầng ưu tiên sửa | Lớp giải pháp liên quan |
|---|---|---|
| AI đoán bừa | Chỉ dẫn AI (Prompting) | `2-prompt` |
| Người dùng tin quá mức | Giao diện (UI/UX) | `1-uiux` |
| Thiếu nguồn xác thực | Kiến trúc dữ liệu (RAG/Knowledge Base) | `3-architecture` |

### Kết luận Phần A

**Nguyên nhân gốc**: AI tự động tạo ra câu trả lời "có vẻ hợp lý" nhưng sai sự thật khi không tìm thấy dữ liệu chính xác trong bộ nhớ huấn luyện, kết hợp với việc người dùng mặc định tin tưởng vào chatbot của hãng lớn.

**Tầng chính cần sửa**: Kiến trúc dữ liệu (RAG) và Chỉ dẫn AI (Prompting).

**Vì sao cần 3 lớp giải pháp**:

- Lớp giao diện: Cảnh báo người dùng về tính xác thực của thông tin chính sách và dẫn link trực tiếp tới văn bản gốc để đối chiếu.
- Lớp chỉ dẫn AI: Buộc AI phải từ chối trả lời nếu không tìm thấy chính xác từ khóa trong Knowledge Base và yêu cầu dẫn nguồn (Citations).
- Lớp kiến trúc dữ liệu: Sử dụng hệ thống RAG (Retrieval-Augmented Generation) để giới hạn phạm vi trả lời và một lớp giám sát (Guardrails) để phát hiện hallucination.

---

## Phần B — Chọn định dạng demo

| Lớp | Thư mục | Định dạng demo chọn | Thời gian dự kiến |
|---|---|---|---|
| Giao diện | `1-uiux` | HTML/CSS (Giao diện Chatbot cao cấp) | 20 phút |
| Chỉ dẫn AI | `2-prompt` | Markdown (System Prompt + Test Cases) | 15 phút |
| Kiến trúc dữ liệu | `3-architecture` | Mermaid Diagram (Quy trình RAG + Guardrails) | 15 phút |

---

## Phần C — Ba lớp giải pháp

### Lớp 1 — Giao diện (`artifact/1-uiux/`)

- **Cách tiếp cận**: Thêm các thẻ thông tin (Info Cards) hiển thị nguồn trích dẫn rõ ràng và nút "Liên hệ nhân viên" nổi bật khi thảo luận về chính sách.
- **Hành động phòng vệ bao phủ**: Thông báo + Khắc phục.
- **Demo**: HTML/CSS UI demo.
- **Trạng thái**: Đang làm

### Lớp 2 — Chỉ dẫn AI (`artifact/2-prompt/`)

- **Cách tiếp cận**: System prompt yêu cầu "Strict Mode": Không có nguồn = Không trả lời. Yêu cầu định dạng trích dẫn cụ thể.
- **Hành động phòng vệ bao phủ**: Ngăn + Từ chối.
- **Demo**: Markdown prompt file.
- **Trạng thái**: Đang làm

### Lớp 3 — Kiến trúc dữ liệu (`artifact/3-architecture/`)

- **Cách tiếp cận**: Triển khai Self-Correction RAG và LLM Guardrail để so sánh output của chatbot với source data.
- **Hành động phòng vệ bao phủ**: Phát hiện + Ngăn.
- **Demo**: Mermaid flowchart.
- **Trạng thái**: Đang làm

---

## Tổng kiểm tra

| Câu hỏi | Trả lời |
|---|---|
| Rủi ro chính đã chọn là gì? | T-01 |
| Nguyên nhân gốc là gì? | Hallucination + Trust issues |
| 3 lớp giải pháp đã đủ chưa? | Giao diện: X / Chỉ dẫn AI: X / Kiến trúc: X |
| 4 hành động đã bao phủ chưa? | Ngăn: X / Phát hiện: X / Khắc phục: X / Thông báo: X |
