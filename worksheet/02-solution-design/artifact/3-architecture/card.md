---
artifact: 3 — Lớp kiến trúc dữ liệu
bai-tap: 2 — Thiết kế giải pháp
demo: ./demo.md
---

# card.md — Lớp kiến trúc dữ liệu

**Tình huống xử lý**: T-01 — Bịa chính sách giảm giá tang lễ.  
Xem `../../1-map-and-format.md` Phần A.

---

## 1. Giải pháp là gì?

Triển khai kiến trúc RAG (Retrieval-Augmented Generation) với hai tầng kiểm soát: 
1. **Knowledge Retrieval**: Chỉ truy xuất từ Wiki nội bộ và PDF chính sách đã được phê duyệt.
2. **Hallucination Guardrail**: Một module LLM độc lập (hoặc Logic check) sẽ so sánh câu trả lời của Chatbot với các đoạn văn bản (chunks) được truy xuất. Nếu mức độ tương đồng thấp, hệ thống sẽ chặn câu trả lời và chuyển sang fallback (người thật).

---

## 2. Vì sao sửa ở lớp kiến trúc dữ liệu?

- Nguyên nhân gốc rễ của hallucination là do AI cố gắng suy luận từ training data cũ hoặc thiếu dữ liệu thực tế.
- Cần một "nguồn chân lý" (Source of Truth) nằm ngoài tham số của mô hình.
- Cần cơ chế phát hiện lỗi tự động (Guardrails) trước khi thông tin đến tay người dùng.

**Hành động phòng vệ chính**:

- [x] Ngăn lỗi bằng nguồn dữ liệu đúng
- [x] Phát hiện khi nguồn thiếu hoặc lỗi
- [x] Khắc phục bằng cách chuyển sang người thật
- [x] Ghi lại lỗi để cải thiện sau

---

## 3. Demo nằm ở đâu?

**File demo**: [`demo.md`](./demo.md)

Demo cần có:

- Sơ đồ Mermaid mô tả luồng dữ liệu từ Query -> RAG -> Guardrail -> User.
- Mô tả các thành phần: Knowledge Base, Vector Database, Evaluator.
- Quy trình Fallback khi Guardrail phát hiện lỗi.

---

## 4. Tác dụng phụ

**Có thể gây vấn đề gì?**

- Trả lời chậm hơn do phải thực hiện nhiều bước kiểm tra và truy xuất (Latency).
- Tăng chi phí vận hành (API costs) vì phải dùng thêm mô hình để kiểm tra chéo.

**Nhóm giảm vấn đề đó bằng cách nào?**

- Sử dụng Cache cho các câu hỏi phổ biến.
- Dùng các mô hình nhỏ, nhanh (như BERT hoặc LLM nhỏ hơn) làm Guardrail để tiết kiệm thời gian và chi phí.

---

## 5. Checklist trước khi nộp

- [x] Sơ đồ cho thấy dữ liệu đi từ đâu đến đâu.
- [x] Có bước kiểm tra nguồn trước khi AI trả lời.
- [x] Có cách xử lý khi không có dữ liệu.
- [x] Có cách chuyển sang người thật với tình huống rủi ro cao.
- [x] Có cách biết lỗi này có đang lặp lại không.

**Người phụ trách**: Trần Xuân Trường - 2A202600321
