# Bước 3: Thiết Lập N8N - Không Gian Làm Việc Tự Động Hóa Của Bạn

## 🎯 N8N Là Gì và Chúng Ta Đang Thiết Lập Gì?

**N8N** là không gian làm việc tự động hóa của bạn - hãy nghĩ về nó như một xưởng kỹ thuật số nơi bạn có thể tạo các quy trình tự động. Nó giống như có một trợ lý thông minh có thể tự động đăng lên mạng xã hội, gửi email và quản lý nội dung của bạn.

### ✅ Bạn Sẽ Có Gì Sau Bước Này

- Không gian làm việc N8N của riêng bạn chạy trên máy tính
- Giao diện web để tạo tự động hóa
- Nền tảng để kết nối tài khoản mạng xã hội

## 🛠️ Bạn Cần Gì Trước Khi Bắt Đầu

Đảm bảo bạn đã hoàn thành các bước này trước:

- ✅ [Docker Desktop đã cài đặt](../01-setup/01-docker-desktop.vi.md)
- ✅ [VSCode đã cài đặt](../02-vscode/01-install-vscode.vi.md)
- ✅ Docker Desktop đang chạy (trạng thái xanh)

## 📥 Thiết Lập Từng Bước

### Bước 1: Lấy Tệp Dự Án

Bạn có hai tùy chọn để tải xuống tệp dự án:

#### Tùy Chọn A: Tải Xuống Dễ Dàng (Khuyến Nghị Cho Người Mới)

1. **Mở trình duyệt web**
2. **Đi đến liên kết này**: [Dự Án Hướng Dẫn N8N](https://github.com/HRLitgroup/n8n-posting-content-tutorial.git)
3. **Tìm nút "Code" màu xanh** (thường ở góc trên bên phải)
4. **Nhấp vào nút "Code"**
5. **Nhấp "Download ZIP"**
6. **Chờ tải xuống hoàn tất**
7. **Tìm tệp ZIP** trong thư mục Downloads
8. **Nhấp chuột phải vào tệp ZIP** và chọn "Extract All" hoặc "Extract Here"
9. **Chọn vị trí** (như Desktop) và nhấp "Extract"

Bây giờ bạn sẽ có một thư mục tên `n8n-posting-content-tutorial` trên máy tính.

![Download repo](../../../assets/setup/clone-setup-n8n.png)

#### Tùy Chọn B: Sử Dụng Git (Cho Người Dùng Có Kinh Nghiệm)

Nếu bạn quen thuộc với Git, bạn có thể sử dụng phương pháp này:

1. **Mở Terminal/Command Prompt**
2. **Điều hướng đến nơi bạn muốn dự án**
3. **Chạy lệnh này**:
   ```bash
   git clone https://github.com/HRLitgroup/n8n-posting-content-tutorial.git
   ```

### Bước 2: Mở Dự Án Trong VSCode

1. **Mở VSCode** (biểu tượng màu xanh)
2. **Đi đến menu File** → **Open Folder**
3. **Điều hướng đến thư mục** bạn đã giải nén ở Bước 1
4. **Chọn thư mục** và nhấp "Select Folder"
5. **Bạn sẽ thấy tệp dự án** trong thanh bên trái

### Bước 3: Khởi Động N8N (Cách Dễ Dàng)

1. **Trong VSCode, nhấn `Ctrl + J`** (Windows/Linux) hoặc `Cmd + J` (Mac)
   - Điều này mở terminal ở dưới VSCode
2. **Gõ lệnh này** và nhấn Enter:
   ```bash
   docker-compose up -d
   ```
3. **Chờ nó hoàn tất** - Bạn sẽ thấy một số văn bản cuộn
4. **Khi xong**, bạn sẽ thấy thông báo như "Done"

### Bước 4: Truy Cập Không Gian Làm Việc N8N

1. **Mở trình duyệt web**
2. **Đi đến**: [http://localhost:5678](http://localhost:5678)
3. **Bạn sẽ thấy màn hình chào mừng N8N**

Nếu bạn thấy giao diện N8N, xin chúc mừng! Không gian làm việc tự động hóa của bạn đang chạy.

### Bước 5: Tạo Tài Khoản N8N

1. **Trên màn hình chào mừng N8N**, nhấp "Get Started"
2. **Điền thông tin của bạn**:
   - **Email**: Địa chỉ email của bạn
   - **Password**: Chọn mật khẩu mạnh
   - **Name**: Tên của bạn
3. **Nhấp "Create Account"**

![Signup N8N](../../../assets/setup/signup-n8n.png)

4. **Chọn tùy chọn miễn phí**: Chọn "Send me a free license key"
5. **Nhấp "Continue"**

![Send activate key](../../../assets/setup/send-activate-key.png)

### Bước 6: Kích Hoạt Tài Khoản

1. **Kiểm tra email** để tìm tin nhắn từ N8N
2. **Nhấp vào liên kết kích hoạt** trong email
3. **Hoặc sao chép khóa giấy phép** và dán vào N8N
4. **Nhấp "Activate License"**

![Active](../../../assets/setup/mail-active-n8n.png)

### Bước 7: Bạn Đã Sẵn Sàng!

Sau khi kích hoạt, bạn sẽ thấy bảng điều khiển N8N. Đây là không gian làm việc tự động hóa nơi bạn có thể:

- Tạo quy trình
- Kết nối tài khoản mạng xã hội
- Thiết lập tác vụ tự động

## 🚨 Khắc Phục Sự Cố

### Không Thể Truy Cập N8N Tại localhost:5678?

1. **Đảm bảo Docker Desktop đang chạy** (trạng thái xanh)
2. **Kiểm tra lệnh đã hoàn tất** trong terminal VSCode
3. **Thử làm mới trang trình duyệt**
4. **Nếu vẫn không hoạt động**:
   - Đóng VSCode
   - Khởi động lại Docker Desktop
   - Mở VSCode lại
   - Chạy lệnh lại

### Lệnh Docker Thất Bại?

1. **Đảm bảo bạn ở đúng thư mục** trong VSCode
2. **Kiểm tra Docker Desktop đang chạy**
3. **Thử chạy lệnh lại**
4. **Nếu bạn thấy lỗi**, thử:
   ```bash
   docker-compose down
   docker-compose up -d
   ```

### Vấn Đề Tạo Tài Khoản?

- **Sử dụng địa chỉ email hợp lệ**
- **Chọn mật khẩu mạnh** (8+ ký tự)
- **Kiểm tra thư mục spam** để tìm email kích hoạt
- **Thử trình duyệt khác** nếu trang không tải

## 🎉 Thành Công! Bước Tiếp Theo Là Gì?

Bây giờ bạn có:

- ✅ N8N chạy trên máy tính
- ✅ Không gian làm việc tự động hóa của riêng mình
- ✅ Giao diện web để tạo quy trình

**Bước Tiếp Theo**: [Kết Nối Tài Khoản Mạng Xã Hội](../04-authentication/get-access-token.vi.md) - Đây là nơi niềm vui bắt đầu! Bạn sẽ học cách kết nối tài khoản Google, LinkedIn và Facebook để bắt đầu tự động hóa việc đăng nội dung.

---

_💡 **Mẹo**: Giữ N8N chạy trong trình duyệt. Bạn sẽ sử dụng nó rất nhiều trong các bước tiếp theo!_
