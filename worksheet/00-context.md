---
title: 00 — Bối cảnh sản phẩm của nhóm
section: Day 25 — dùng lại cho mọi cuộc trò chuyện với AI
format: Nhóm
time: Điền 5 phút đầu buổi
---

# 00-context.md — Bối cảnh sản phẩm của nhóm

Điền file này một lần ở đầu buổi. Sau đó, mỗi lần dùng AI, hãy đưa toàn bộ nội dung file này vào đầu cuộc trò chuyện.

Lý do: AI không tự nhớ bối cảnh giữa các cuộc trò chuyện. Nếu mỗi lần đưa bối cảnh khác nhau, câu trả lời cũng sẽ lệch.

---

## 1. Sản phẩm

- **Tên sản phẩm / bot**: [Trợ lý đặt vé và chăm sóc khách hàng hàng không]
- **Sản phẩm giúp ai làm gì**: giúp hành khách tìm kiếm, đặt vé, tra cứu thông tin chuyến bay, làm thủ tục check-in, và hỗ trợ các yêu cầu sau bán hàng (đổi vé, hoàn vé, yêu cầu đặc biệt).
- **Người dùng gặp sản phẩm ở đâu**: [Website của hãng]
- **Giai đoạn hiện tại**: [chuẩn bị ra mắt]

---

## 2. Phạm vi

**AI được làm gì**

- Trả lời câu hỏi về điều kiện hành lý, giờ bay, thủ tục check-in, quy định về vật phẩm cấm mang lên máy bay.
- Cung cấp thông tin cho việc đặt vé (tìm kiếm chuyến bay, so sánh giá).
- Cung cấp thông tin về các chương trình khách hàng thân thiết (loyalty programs).
- Giải đáp các thắc mắc chung về quy định an toàn, thủ tục kiểm soát an ninh, và các dịch vụ trên chuyến bay.

**AI không được làm gì**

- Đưa ra lời khuyên y tế, pháp lý, hoặc tư vấn về các tình huống khẩn cấp cần sự can thiệp của con người.
- Xử lý các giao dịch tài chính nhạy cảm (thanh toán, hoàn tiền lớn) mà không có sự xác thực hoặc giám sát của hệ thống thanh toán chính thức.
- Cung cấp thông tin cá nhân của hành khách khác hoặc truy cập dữ liệu nội bộ không liên quan đến yêu cầu.

**Vì sao có giới hạn này**

[Các quy định của ngành hàng không rất nghiêm ngặt về an toàn, bảo mật thông tin hành khách và tài chính. AI không được phép tự quyết định các thay đổi lớn, vì mọi sai sót có thể gây hậu quả tài chính và uy tín nghiêm trọng.]

---

## 3. Người dùng

- **Là ai**: [Tuổi: 18-65; Vai trò: Hành khách cá nhân hoặc doanh nghiệp nhỏ; Trình độ công nghệ: Từ cơ bản đến nâng cao; Bối cảnh sử dụng: Đang tìm kiếm, đặt vé, tìm kiếm chương trình giảm giá hoặc cần hỗ trợ trước/sau chuyến bay]
- **Họ hỏi AI khi nào**: [Hành khách bắt đầu tương tác với AI ngay khi truy cập trang web hoặc ứng dụng, từ thời điểm tìm kiếm chuyến bay đến sau khi đã đặt vé]
- **Họ cần quyết định gì sau khi hỏi AI**: [Hành khách cần đưa ra các quyết định như: có chọn hãng hàng không hiện tại hay không]
- **Khi nào họ dễ bị tổn thương / dễ hiểu sai**: [Khi có sự thay đổi về giá vé, chuyến bay hoặc các chính sách của hãng hàng không]
- **Họ thường tin AI đến mức nào**: [cần kiểm tra lại]

---

## 4. Bối cảnh ngành

- **Sự cố tương tự đã từng xảy ra**: [Sự cố chậm chuyến bay thường xuyên của hãng hàng không XXXX trong những năm gần đây, gây ảnh hưởng đến hàng chục ngàn hành khách. Nguyên nhân được cho là do lỗi hệ thống và thiếu sự chuẩn bị của nhân viên hỗ trợ khách hàng. AI có thể giúp giảm thiểu rủi ro này bằng cách cung cấp thông tin chính xác và kịp thời cho hành khách, cũng như hỗ trợ nhân viên xử lý các yêu cầu của khách hàng một cách hiệu quả.]
- **Quy định hoặc ràng buộc liên quan**: [Các quy định của ngành hàng không về việc cung cấp thông tin cho hành khách, bao gồm cả thông tin về chuyến bay, giá vé, quy định về hành lý và các dịch vụ khác. Ngoài ra, cần tuân thủ các quy định về bảo mật dữ liệu và quyền riêng tư của hành khách.]
- **Nguồn chính thức nên ưu tiên**: [...]

---

## 5. Ghi chú thêm

[Điền bất kỳ thông tin nào giúp AI hiểu bối cảnh: hạn chót, quy mô nhóm, nguồn dữ liệu, chính sách nội bộ, ví dụ câu hỏi thật.]

**Nguồn chính thức**: Chỉ sử dụng thông tin từ các nguồn sau:
- Nội dung nội bộ trên wiki: `{{WIKI_URL}}`
- Landing page sản phẩm: `{{LANDING_PAGE_URL}}`
- Tài liệu API: `{{API_DOC_URL}}`

**Dữ liệu bổ sung**: Chỉ dùng khi có sự cho phép từ quản lý sản phẩm.

---

## Cách dùng

```text
1. Mở công cụ AI phù hợp với bước đang làm.
2. Đưa toàn bộ nội dung file này vào đầu cuộc trò chuyện.
3. Chọn prompt tham khảo từ thư mục ../prompts/ và chỉnh lại nếu cần.
4. Đọc lại bản nháp AI tạo ra.
5. Sửa lại cho đúng bối cảnh nhóm.
6. Lưu kết quả vào đúng file trong worksheet/.
```

Ghi chú: nội dung trong `[...]` là chỗ cần điền. Sau khi điền xong, xóa dấu ngoặc nếu không cần giữ.
