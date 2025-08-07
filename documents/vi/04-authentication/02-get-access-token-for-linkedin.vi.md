# Lấy Token Truy Cập LinkedIn API cho N8N

## Tổng Quan

Hướng dẫn này cung cấp hướng dẫn từng bước để lấy token truy cập LinkedIn API có thể được sử dụng trong quy trình N8N cho marketing LinkedIn, tự động hóa networking và quản lý mạng xã hội.

## Yêu Cầu Trước Khi Bắt Đầu

Trước khi bắt đầu, đảm bảo bạn có:

- Tài khoản LinkedIn
- Trang công ty LinkedIn
- Hiểu biết cơ bản về khái niệm xác thực API

## Bước 1: Tạo Ứng Dụng LinkedIn

1. Đi đến [LinkedIn Developers Apps](https://www.linkedin.com/developers/apps)
2. Nhấp "Create App"
3. Điền vào chi tiết ứng dụng:
   - **App name**: "n8n-posting-content"
   - **LinkedIn Page**: Chọn trang công ty của bạn (hoặc tạo một trang)
   - **App logo**: Tải lên logo cho ứng dụng của bạn
   - **App description**: Mô tả ngắn gọn về mục đích ứng dụng
   - Đánh dấu vào checkbox `I have read and agree to these terms`
4. Nhấp "Create App"

## Bước 2: Cấu Hình Cài Đặt OAuth 2.0

1. Trong dashboard ứng dụng, đi đến tab "Auth"
2. Dưới "OAuth 2.0 settings", thêm redirect URLs: `http://localhost:5678/rest/oauth2-credential/callback`
3. Nhấp "Save"

### Cấu Hình Quyền Ứng Dụng

1. Đi đến tab "Products"
2. Yêu cầu quyền truy cập vào các sản phẩm bạn cần:
   - **Sign In with LinkedIn using OpenID Connect**
   - **Share on LinkedIn**
   - **LinkedIn Ad Library**

## Bước 3: Lấy Thông Tin Xác Thực Khách Hàng

1. Trong dashboard ứng dụng, đi đến tab "Auth"
2. Ghi chú thông tin xác thực của bạn:
   - **Client ID**: Định danh duy nhất của ứng dụng
   - **Primary Client Secret**: Khóa bí mật của ứng dụng (giữ an toàn)

## Bước Tiếp Theo

Sau khi bạn đã cấu hình thành công quyền truy cập LinkedIn API:

**Tiếp Tục Nền Tảng Tiếp Theo**: Tiếp tục với [Thiết Lập Facebook API](./03-get-access-token-for-facebook.vi.md)

## Tài Nguyên Bổ Sung

- [Tài Liệu LinkedIn API](https://developer.linkedin.com/docs)
- [Hướng Dẫn LinkedIn OAuth 2.0](https://developer.linkedin.com/docs/oauth2)
- [Tích Hợp LinkedIn N8N](https://docs.n8n.io/integrations/nodes/n8n-nodes-base.linkedin/)
- [LinkedIn Developers Portal](https://www.linkedin.com/developers/)
