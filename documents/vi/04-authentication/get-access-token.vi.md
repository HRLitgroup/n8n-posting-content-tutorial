# Lấy Token Truy Cập cho Quy Trình N8N

## Tổng Quan

Tài liệu này cung cấp tổng quan về việc lấy token truy cập từ ba nền tảng chính thường được sử dụng trong quy trình N8N:

1. **Google APIs** - Cho Gmail, Google Sheets, Google Drive và các dịch vụ Google khác
2. **LinkedIn API** - Cho tự động hóa marketing và networking LinkedIn
3. **Facebook API** - Cho tự động hóa marketing và mạng xã hội Facebook

## Hướng Dẫn Bắt Đầu Nhanh

Để có hướng dẫn chi tiết từng bước, tham khảo các hướng dẫn nền tảng riêng lẻ:

- **[Thiết Lập Google API](./01-get-access-token-for-google.vi.md)** - Thiết lập OAuth Google hoàn chỉnh
- **[Thiết Lập LinkedIn API](./02-get-access-token-for-linkedin.vi.md)** - Thiết lập OAuth LinkedIn hoàn chỉnh
- **[Thiết Lập Facebook API](./03-get-access-token-for-facebook.vi.md)** - Thiết lập OAuth Facebook hoàn chỉnh

## Yêu Cầu Trước Khi Bắt Đầu

Trước khi lấy token truy cập, đảm bảo bạn có:

- Tài khoản Google (cho Google APIs)
- Tài khoản LinkedIn (cho LinkedIn API)
- Tài khoản Facebook (cho Facebook API)
- Hiểu biết cơ bản về khái niệm xác thực API

## So Sánh Nền Tảng

| Nền Tảng     | Trường Hợp Sử Dụng                           | Tính Năng Chính                    | Thời Hạn Token            |
| ------------ | -------------------------------------------- | ---------------------------------- | ------------------------- |
| **Google**   | Tự động hóa email, Bảng tính, Quản lý tệp    | Sheets, Drive                      | 1 giờ (có thể làm mới)    |
| **LinkedIn** | Networking chuyên nghiệp, Marketing nội dung | Quản lý hồ sơ, Đăng bài, Phân tích | Thay đổi (có thể làm mới) |
| **Facebook** | Marketing mạng xã hội, Trang doanh nghiệp    | Quản lý trang, Quảng cáo, Thống kê | Thay đổi (có thể làm mới) |
