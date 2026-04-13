# Tổng hợp Câu hỏi và Đáp án Claude Code & MCP

### 1. Hạn chế cơ bản của các mô hình ngôn ngữ (LLM) trong lập trình là gì?
- [ ] Chúng chỉ có thể tạo mã bằng các ngôn ngữ lập trình cụ thể.
- [ ] Chúng có dung lượng bộ nhớ hạn chế đối với các cơ sở mã nguồn lớn.
- [ ] Họ không thể hiểu được các khái niệm lập trình phức tạp.
- [x] **Chúng chỉ có thể xử lý đầu vào/đầu ra văn bản và không thể tương tác trực tiếp với các hệ thống bên ngoài.**

### 2. Cần cấu hình quyền hạn như thế nào khi tích hợp máy chủ MCP với Claude Code trong GitHub Actions?
- [x] **Mỗi công cụ máy chủ MCP phải được liệt kê riêng trong phần quyền truy cập.**
- [ ] Không cần cấp quyền đặc biệt nào nếu chạy trong GitHub Actions.
- [ ] Quyền truy cập được tự động kế thừa từ cài đặt kho lưu trữ GitHub.
- [ ] Một giấy phép chung duy nhất cho tất cả các hoạt động MCP.

### 3. Sự khác biệt chính giữa Chế độ Lập kế hoạch và Chế độ Tư duy trong Claude Code là gì?
- [ ] Chế độ Lập kế hoạch dùng để viết mã, trong khi Chế độ Tư duy dùng để gỡ lỗi.
- [ ] Chế độ Lập kế hoạch nhanh hơn, trong khi Chế độ Tư duy chính xác hơn.
- [ ] Chế độ Lập kế hoạch sử dụng ít token hơn, trong khi Chế độ Tư duy sử dụng nhiều token hơn.
- [x] **Chế độ Lập kế hoạch xử lý phạm vi rộng (các nhiệm vụ nhiều bước) trong khi Chế độ Tư duy xử lý chiều sâu (logic phức tạp).**

### 4. Mô tả chính xác ba loại tệp CLAUDE.md và cách sử dụng chúng?
- [ ] Cấp độ dự án (gỡ lỗi), Cấp độ cục bộ (kiểm thử), Cấp độ máy (sản xuất)
- [ ] Cấp độ dự án (sử dụng cá nhân), Cấp độ cục bộ (chia sẻ nhóm), Cấp độ máy (dành riêng cho kho lưu trữ)
- [x] **Cấp độ dự án (chia sẻ với nhóm, đã cam kết), Cấp độ cục bộ (cá nhân, chưa cam kết), Cấp độ máy (toàn cầu cho tất cả các dự án)**
- [ ] Cấp độ dự án (cấu hình), Cấp độ cục bộ (tài liệu), Cấp độ máy (tự động hóa)

### 5. Làm thế nào để tạo một lệnh tùy chỉnh trong Claude Code chấp nhận các tham số khi chạy?
- [ ] Sử dụng decorator `@parameters` trong tệp lệnh.
- [ ] Xác định các tham số trong tệp cấu hình settings.json.
- [ ] Thêm các tham số dòng lệnh khi thực thi lệnh.
- [x] **Bao gồm phần giữ chỗ $ARGUMENTS trong tệp lệnh markdown**

### 6. Loại hook nào có thể ngăn chặn việc gọi công cụ nếu đáp ứng được một số điều kiện nhất định?
- [ ] Móc PostToolUse
- [ ] Móc nối dự án
- [ ] Móc toàn cầu
- [x] **Móc PreToolUse**

### 7. Ngăn Claude đọc các tệp .env nhạy cảm, nên thiết lập loại hook và công cụ nào?
- [ ] Hook PostToolUse, khớp với Write và Edit
- [ ] Móc PreToolUse, khớp với Write và Create
- [x] **Móc PreToolUse, khớp với Read và Grep**
- [ ] Hook PostToolUse, khớp with Read và Delete

### 8. Mục đích chính của các hook trong Claude Code là gì?
- [ ] Để quản lý các mối phụ thuộc của dự án.
- [ ] Tự động tạo các đoạn mã mới.
- [x] **Chạy các lệnh trước hoặc sau khi Claude thực thi một công cụ.**
- [ ] Cung cấp giao diện người dùng cho Claude.
