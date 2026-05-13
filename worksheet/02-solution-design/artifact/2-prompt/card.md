---
artifact: 2 — Lớp chỉ dẫn AI
bai-tap: 2 — Thiết kế giải pháp
demo: ./demo.md
---

# card.md — Lớp chỉ dẫn AI

**Tình huống xử lý**: T-01 — Bịa chính sách giảm giá tang lễ.  
Xem `../../1-map-and-format.md` Phần A.

---

## 1. Giải pháp là gì?

Thêm hệ thống luật "Strict Policy Verification" vào System Prompt. AI chỉ được phép trích dẫn thông tin chính sách nếu tìm thấy chuỗi văn bản khớp trong cơ sở dữ liệu (Exact Match or Contextual Match). Nếu không có nguồn, AI bắt buộc phải dùng mẫu câu từ chối chuẩn và thực hiện lệnh chuyển người thật.

---

## 2. Vì sao sửa ở lớp chỉ dẫn AI?

- AI đang trả lời quá tự tin ngay cả khi không có dữ liệu (Hallucination).
- Cần một "phanh" tinh thần (Cognitive guardrail) để AI biết điểm dừng.
- Sửa prompt là cách nhanh nhất để thiết lập hành vi an toàn mà không cần đào tạo lại mô hình.

**Hành động phòng vệ chính**:

- [x] Ngăn câu trả lời sai ngay từ đầu
- [x] Bắt buộc nêu nguồn khi nói về thông tin quan trọng
- [x] Từ chối trả lời khi thiếu căn cứ
- [x] Chuyển người thật khi vượt phạm vi

---

## 3. Demo nằm ở đâu?

**File demo**: [`demo.md`](./demo.md)

Demo cần có:

- System Prompt với các luật nghiêm ngặt.
- Cấu trúc Citations bắt buộc.
- Các tình huống Negative Test (Hỏi chính sách không có thật).
- Kết quả kỳ vọng sau khi áp dụng prompt.

---

## 4. Tác dụng phụ

**Có thể gây vấn đề gì?**

- AI có thể trở nên quá cứng nhắc, từ chối cả những câu hỏi tư vấn thông thường nếu không tìm thấy nguồn văn bản khớp 100%.
- Câu trả lời có thể dài dòng vì phải kèm theo trích dẫn.

**Nhóm giảm vấn đề đó bằng cách nào?**

- Phân loại ý định (Intent Classification): Chỉ áp dụng luật Strict cho các ý định liên quan đến "Chính sách", "Tài chính", "Pháp lý". Các ý định khác vẫn cho phép tư vấn linh hoạt.

---

## 5. Checklist trước khi nộp

- [x] Luật viết đủ cụ thể để AI làm theo.
- [x] Có mẫu câu khi AI không có đủ thông tin.
- [x] Có ví dụ cho tình huống dễ sai.
- [x] Có thử lại bằng tình huống trong Bài 1.
- [x] Không dùng prompt như cách duy nhất nếu lỗi nằm ở dữ liệu hoặc quy trình.

**Người phụ trách**: Lê Hoàng Long - 2A202600095
