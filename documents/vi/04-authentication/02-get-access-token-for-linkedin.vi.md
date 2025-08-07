# Kết Nối LinkedIn với N8N

## 🎯 Chúng Ta Đang Thiết Lập Gì?

**LinkedIn** là nền tảng mạng lưới chuyên nghiệp lớn nhất thế giới. Bằng cách kết nối nó với N8N, bạn có thể tự động hóa việc đăng nội dung chuyên nghiệp, chia sẻ bài viết và quản lý sự hiện diện chuyên nghiệp của mình.

### ✅ Bạn Sẽ Có Gì

- Tự động đăng nội dung chuyên nghiệp lên LinkedIn
- Chia sẻ bài viết và cập nhật tự động
- Quản lý hồ sơ chuyên nghiệp
- Theo dõi tương tác và phân tích
- Xây dựng mạng lưới chuyên nghiệp hiệu quả

## 🛠️ Bạn Cần Gì Trước Khi Bắt Đầu

Đảm bảo bạn có:

- ✅ Tài khoản LinkedIn (cá nhân hoặc kinh doanh)
- ✅ Trang công ty LinkedIn (tùy chọn nhưng khuyến nghị)
- ✅ Khoảng 10-15 phút để hoàn thành thiết lập
- ✅ Mật khẩu LinkedIn sẵn sàng

## 📋 Thiết Lập Từng Bước

### Bước 1: Tạo Ứng Dụng LinkedIn

Hãy nghĩ về điều này như tạo một "cầu nối" giữa LinkedIn và N8N:

1. **Mở trình duyệt web**
2. **Đi đến LinkedIn Developers**: [Nhấp vào đây để truy cập](https://www.linkedin.com/developers/apps)
3. **Đăng nhập với tài khoản LinkedIn** nếu được nhắc
4. **Nhấp "Create App"** (thường là nút màu xanh)

### Bước 2: Điền Chi Tiết Ứng Dụng

1. **App name**: "Tự Động Hóa LinkedIn N8N Của Tôi"
2. **LinkedIn Page**:
   - Nếu bạn có trang công ty, chọn nó
   - Nếu không, bạn có thể tạo một hoặc sử dụng hồ sơ cá nhân
3. **App logo**: Tải lên bất kỳ hình ảnh nào (chỉ để nhận dạng)
4. **App description**: "Công cụ tự động hóa cho đăng LinkedIn"
5. **Chọn hộp**: "I have read and agree to these terms"
6. **Nhấp "Create App"**

### Bước 3: Thiết Lập Bảo Mật (Cài Đặt OAuth)

Điều này cho LinkedIn biết rằng tự động hóa của bạn an toàn để sử dụng:

1. **Trong bảng điều khiển ứng dụng**, tìm tab "Auth"
2. **Nhấp vào "Auth"**
3. **Tìm "OAuth 2.0 settings"**
4. **Thêm URL chuyển hướng này**: `http://localhost:5678/rest/oauth2-credential/callback`
5. **Nhấp "Save"**

### Bước 4: Yêu Cầu Quyền

Bước này yêu cầu LinkedIn cho phép đăng thay mặt bạn:

1. **Đi đến tab "Products"**
2. **Tìm các sản phẩm này** và yêu cầu quyền truy cập cho từng cái:

   - **Sign In with LinkedIn using OpenID Connect**
   - **Share on LinkedIn**
   - **LinkedIn Ad Library** (tùy chọn)

3. **Cho mỗi sản phẩm**:
   - Nhấp vào nó
   - Nhấp "Request Access"
   - Điền thông tin bắt buộc
   - Gửi yêu cầu

### Bước 5: Lấy Khóa Truy Cập

Đây là những "chìa khóa" mà N8N sẽ sử dụng để truy cập LinkedIn:

1. **Quay lại tab "Auth"**
2. **Tìm "Client Credentials"**
3. **Ghi chép những số quan trọng này**:
   - **Client ID**: Một chuỗi dài chữ cái và số
   - **Primary Client Secret**: Một chuỗi dài khác (giữ bí mật!)

## ✅ Cách Kiểm Tra Thiết Lập Có Hoạt Động Không

1. **Bạn nên có Client ID và Client Secret** ghi chép
2. **Ứng dụng nên hiển thị là "Active"** trong bảng điều khiển
3. **URL chuyển hướng nên được lưu** trong cài đặt OAuth
4. **Bạn nên đã yêu cầu quyền truy cập** cho các sản phẩm cần thiết

## 🚨 Khắc Phục Sự Cố

### Không Tìm Thấy Nút Create App?

- **Đảm bảo bạn đã đăng nhập** vào tài khoản LinkedIn đúng
- **Thử làm mới trang**
- **Kiểm tra bạn ở trang developers**: linkedin.com/developers/apps

### Tạo Ứng Dụng Thất Bại?

- **Thử tên ứng dụng khác** (có thể đã được sử dụng)
- **Đảm bảo bạn điền tất cả trường bắt buộc**
- **Kiểm tra bạn đồng ý với điều khoản**

### Cài Đặt OAuth Không Lưu?

- **Đảm bảo URL chuyển hướng chính xác**: `http://localhost:5678/rest/oauth2-credential/callback`
- **Thử sao chép và dán** URL thay vì gõ
- **Kiểm tra bạn nhấp "Save"**

### Không Thể Yêu Cầu Quyền Truy Cập Sản Phẩm?

- **Một số sản phẩm có thể mất thời gian** để được phê duyệt
- **Thử yêu cầu từng cái một**
- **Đảm bảo bạn điền tất cả thông tin bắt buộc**

### Vẫn Có Vấn Đề?

- **Thử tạo ứng dụng mới** với tên khác
- **Kiểm tra bạn sử dụng tài khoản LinkedIn đúng**
- **Đảm bảo bạn có quyền quản trị** cho tài khoản LinkedIn

## 🎉 Bạn Sẵn Sàng Cho Bước Tiếp Theo!

Sau khi thiết lập thông tin đăng nhập LinkedIn, bạn có thể:

1. **Kết nối Facebook**: [Thiết lập tự động hóa Facebook](./03-get-access-token-for-facebook.vi.md)
2. **Kết nối Google**: [Thiết lập tự động hóa Google](./01-get-access-token-for-google.vi.md)
3. **Bắt đầu tạo quy trình**: Sử dụng LinkedIn trong tự động hóa N8N

## 📚 Tài Nguyên Bổ Sung

- **Cần giúp đỡ?** Kiểm tra [Tài liệu API LinkedIn](https://developer.linkedin.com/docs)
- **Muốn tìm hiểu thêm?** Thử [Hướng dẫn OAuth LinkedIn](https://developer.linkedin.com/docs/oauth2)
- **Trợ giúp N8N**: [Tích hợp LinkedIn N8N](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.linkedin/)

---

_💡 **Mẹo**: Giữ Client ID và Client Secret an toàn. Bạn sẽ cần chúng khi kết nối với N8N sau này._
