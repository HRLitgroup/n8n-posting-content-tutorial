# Lấy Token Truy Cập Google API cho N8N

## Tổng Quan

Hướng dẫn này cung cấp hướng dẫn từng bước để lấy token truy cập Google API có thể được sử dụng trong quy trình N8N cho các dịch vụ như Gmail, Google Sheets, Google Drive và Google Calendar.

## Yêu Cầu Trước Khi Bắt Đầu

Trước khi bắt đầu, đảm bảo bạn có:

- Tài khoản Google
- Hiểu biết cơ bản về khái niệm xác thực API

## Bước 1: Tạo Dự Án Google Cloud

1. Đi đến [Google Cloud Console](https://console.cloud.google.com/)
   ![Google Console](../../../assets/google/google-console.png)
2. Trong modal mở ra, nhấp → "New Project"
   ![Google Create Project](../../../assets/google/google-create-project.png)
3. Nhập tên dự án (ví dụ: "N8N Integration")
4. Nhấp "Create"

## Bước 2: Bật Các API Cần Thiết

1. Trong dự án của bạn, đi đến "APIs & Services" → "Library"
2. Tìm kiếm và bật các API bạn cần:
   - **Google Sheets API** - Cho các thao tác bảng tính
   - **Google Drive API** - Cho quản lý tệp

### Để bật một API:

1. Tìm kiếm tên API trong thư viện
2. Nhấp vào API
3. Nhấp "Enable"

## Bước 3: Tạo Thông Tin Xác Thực OAuth 2.0

1. Đi đến "APIs & Services" → "Credentials"
2. Lưu ý nếu bạn thấy thông báo này:
   `Remember to configure the OAuth consent screen with information about your application.`
   ![Config consent screen](../../../assets/google/google-config-consent-screen.png)
   => Vui lòng nhấp vào `Config consent screen` để tạo cấu hình trước khi thực hiện bước tiếp theo. Sau khi tạo cấu hình thành công, nhấp [đây](https://console.cloud.google.com/apis/credentials) để chuyển hướng lại trang Credentials.
3. Nhấp "Create Credentials" → "OAuth 2.0 Client IDs"
   ![Create credentials](../../../assets/google/google-create-credentials.png)
4. Điền vào biểu mẫu theo hướng dẫn này:
   - Application type: `Web application`
   - Name: `n8n-posting-content`
   - Authorized redirect URIs: `http://localhost:5678/rest/oauth2-credential/callback`
     ![OAuth](../../../assets/google/google-create-oauth.png)
     sau đó nhấp nút `Create`.
5. Sau khi tạo, bạn sẽ nhận được modal mở ra với thông tin `Client ID` và `Client secret`. Để sử dụng lại thông tin thông tin xác thực này sau này, vui lòng nhấp vào `Download JSON` để lưu tệp thông tin xác thực.

## Bước 4: Thêm người dùng thử nghiệm để cho phép truy cập Google API

1. Truy cập [Google Audience](https://console.cloud.google.com/auth/audience)
2. Đảm bảo bảng `Test users` đã có ít nhất 1 người dùng (tốt nhất là địa chỉ email bạn đang đăng nhập)
3. Nếu không, nhấp nút `Add users` để thêm người dùng mới.

## Bước Tiếp Theo

Sau khi bạn đã cấu hình thành công quyền truy cập Google API:

**Tiếp Tục Nền Tảng Tiếp Theo**: Tiếp tục với [Thiết Lập LinkedIn API](./02-get-access-token-for-linkedin.vi.md)

## Tài Nguyên Bổ Sung

- [Tài Liệu Google OAuth 2.0](https://developers.google.com/identity/protocols/oauth2)
- [Google APIs Explorer](https://developers.google.com/apis-explorer/)
- [Tích Hợp Google N8N](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.google/)
- [Google Cloud Console](https://console.cloud.google.com/)
