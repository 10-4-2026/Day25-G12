---
artifact: 1 — Lớp giao diện
bai-tap: 2 — Thiết kế giải pháp
demo: ./demo.html
---

# card.md — Lớp giao diện

**Tình huống xử lý**: T-01 — Bịa chính sách giảm giá tang lễ.  
Xem `../../1-map-and-format.md` Phần A.

---

## 1. Giải pháp là gì?

Giao diện Chatbot sẽ hiển thị các thẻ thông tin (Policy Cards) thay vì chỉ văn bản thuần túy khi thảo luận về chính sách. Mỗi thẻ sẽ đi kèm nhãn "Nguồn xác thực" (Verified Source) có link trực tiếp tới website của hãng. Nếu thông tin không tìm thấy nguồn chính xác 100%, giao diện sẽ tự động hiển thị nút "Yêu cầu nhân viên hỗ trợ" thay vì để AI tiếp tục đoán.

---

## 2. Vì sao sửa ở lớp giao diện?

- Người dùng dễ tin câu trả lời của AI quá mức khi thấy nó trả lời lưu loát.
- Giao diện cần làm rõ ranh giới giữa "Dữ liệu cứng" (Policy) và "Tư vấn mềm" (Hành trình).
- Cung cấp lối thoát (Escalation) ngay lập tức khi rủi ro tài chính xuất hiện.

**Hành động phòng vệ chính**:

- [x] Thông báo rõ giới hạn
- [x] Phát hiện dấu hiệu thiếu nguồn
- [x] Chuyển người thật khi cần
- [x] Giúp người dùng kiểm tra lại nguồn

---

## 3. Demo nằm ở đâu?

**File demo**: [`demo.html`](./demo.html)

**Định dạng demo**:

- [x] Bản HTML đơn giản
- [x] Luồng màn hình (trên giao diện)

**Thành phần cần có trong demo**:

- Thẻ chính sách có nhãn "Verified"
- Cảnh báo khi thông tin mang tính chất tham khảo
- Nút "Talk to Agent" nổi bật
- Liên kết đối chiếu nguồn gốc

---

## 4. Tác dụng phụ

**Có thể gây vấn đề gì?**

- Giao diện có thể trở nên rối mắt hơn với nhiều nhãn cảnh báo.
- Tăng tỷ lệ yêu cầu gặp người thật, gây quá tải cho nhân viên hỗ trợ.

**Nhóm giảm vấn đề đó bằng cách nào?**

- Chỉ hiển thị thẻ Verified và nút Escalate cho các từ khóa nhạy cảm (Tang lễ, Hoàn tiền, Pháp lý). Các câu hỏi thông thường vẫn dùng UI chat đơn giản.

---

## 5. Checklist trước khi nộp

- [x] Giải pháp gắn đúng với một rủi ro chính.
- [x] Demo nhìn vào là hiểu vấn đề được chặn ở đâu.
- [x] Có đủ trạng thái bình thường và trạng thái lỗi.
- [x] Có cách chuyển sang người thật khi AI không nên tự xử lý.
- [x] Câu chữ trong giao diện ngắn, không đổ hết trách nhiệm cho người dùng.

**Người phụ trách**: Nguyễn Tuấn Khải - 2A202600231

