# N8N Auto Flow - Hướng Dẫn Tự Động Hóa Hoàn Chỉnh

## 🎯 N8N Là Gì và Tại Sao Bạn Nên Quan Tâm?

**N8N** là một công cụ tự động hóa mạnh mẽ giúp bạn kết nối các ứng dụng và dịch vụ khác nhau để hoạt động tự động cùng nhau. Hãy nghĩ về nó như một trợ lý kỹ thuật số có thể:

- **Tự động đăng nội dung** lên nhiều nền tảng mạng xã hội
- **Gửi email** khi có sự kiện nhất định xảy ra
- **Cập nhật bảng tính** với dữ liệu mới
- **Tiết kiệm thời gian** bằng cách tự động hóa các tác vụ lặp lại
- **Giảm lỗi** bằng cách loại bỏ công việc thủ công

### 🚀 Bạn Sẽ Học Được Gì

Theo hướng dẫn này, bạn sẽ học cách:

1. Thiết lập không gian làm việc tự động hóa của riêng mình
2. Kết nối tài khoản mạng xã hội của bạn (Google, LinkedIn, Facebook)
3. Tạo các quy trình tự động tiết kiệm hàng giờ làm việc
4. Quản lý việc đăng nội dung tự động

## 🌐 Chọn Ngôn Ngữ

- [🇺🇸 English](./README.md)
- [🇻🇳 Tiếng Việt](./README.vi.md) (Hiện tại)

## 📚 Hướng Dẫn Bắt Đầu Nhanh

### Cho Người Mới Hoàn Toàn

Nếu bạn mới làm quen với tự động hóa, hãy bắt đầu từ đây:

1. **[Những Gì Bạn Cần Cài Đặt](./01-setup/01-docker-desktop.vi.md)** - Các công cụ đơn giản để bắt đầu
2. **[Thiết Lập Không Gian Làm Việc](./02-vscode/01-install-vscode.vi.md)** - Tạo môi trường tự động hóa
3. **[Cài Đặt N8N](./03-n8n-setup/01-clone-setup-n8n.vi.md)** - Khởi chạy công cụ tự động hóa
4. **[Kết Nối Tài Khoản](./04-authentication/get-access-token.vi.md)** - Liên kết mạng xã hội
5. **[Tạo Tự Động Hóa Đầu Tiên](./05-workflows/01-create-n8n-workflow.vi.md)** - Xây dựng quy trình đầu tiên

### Cho Người Dùng Có Kinh Nghiệm

Nếu bạn quen thuộc với các công cụ phát triển:

- [Hướng Dẫn Thiết Lập Nhanh](./01-setup/01-docker-desktop.vi.md)
- [Cấu Hình Nâng Cao](./03-n8n-setup/01-clone-setup-n8n.vi.md)

## 🛠️ Bạn Sẽ Cần Gì

### Công Cụ Thiết Yếu (Đừng Lo - Chúng Tôi Sẽ Hướng Dẫn Từng Bước)

- **Docker Desktop** - Công cụ giúp chạy N8N trên máy tính
- **VSCode** - Trình soạn thảo văn bản giúp thiết lập dễ dàng hơn
- **Trình Duyệt Web** - Chrome, Firefox, hoặc Safari

### Tài Khoản Của Bạn

- **Tài Khoản Google** - Cho Gmail, Google Sheets, Google Drive
- **Tài Khoản LinkedIn** - Cho tự động hóa mạng lưới chuyên nghiệp
- **Tài Khoản Facebook** - Cho tự động hóa mạng xã hội

## 📁 Cấu Trúc Dự Án

```
n8n_auto_flow/
├── assets/                    # Hình ảnh và hướng dẫn hữu ích
├── documents/                 # Tài liệu này
│   ├── en/                  # Hướng dẫn tiếng Anh
│   ├── vi/                  # Hướng dẫn tiếng Việt
│   └── README.md            # Bộ chọn ngôn ngữ
├── docker-compose.yml        # Tệp cấu hình (đừng lo về cái này)
└── README.md                 # Tệp này
```

## 🎯 Bạn Sẽ Đạt Được Gì

Sau khi hoàn thành hướng dẫn này, bạn sẽ có:

- ✅ Không gian làm việc N8N tự động hóa của riêng mình
- ✅ Tài khoản mạng xã hội đã kết nối
- ✅ Khả năng tạo quy trình tự động
- ✅ Kiến thức để tự động hóa các tác vụ lặp lại
- ✅ Tiết kiệm thời gian cho dự án kinh doanh hoặc cá nhân

## 🔧 Yêu Cầu Hệ Thống

- **Windows 10/11, Mac, hoặc Linux** - Bất kỳ máy tính hiện đại nào
- **Tối thiểu 4GB RAM** - Hầu hết máy tính đều có
- **2GB dung lượng ổ cứng trống** - Yêu cầu rất nhỏ
- **Kết nối internet** - Để tải xuống và kết nối dịch vụ

## 📖 Tài Nguyên Bổ Sung

- [Tài Liệu Chính Thức N8N](https://docs.n8n.io/) - Cho người dùng nâng cao
- [Tài Liệu Docker](https://docs.docker.com/) - Tham khảo kỹ thuật
- [Tài Liệu VSCode](https://code.visualstudio.com/docs) - Trợ giúp trình soạn thảo

## 🤝 Cần Giúp Đỡ?

- **Bị kẹt ở một bước?** Mỗi hướng dẫn đều có mẹo khắc phục sự cố
- **Có gì không hoạt động?** Kiểm tra phần khắc phục sự cố trong mỗi hướng dẫn
- **Muốn tìm hiểu thêm?** Ghé thăm diễn đàn cộng đồng N8N

## 🚀 Sẵn Sàng Bắt Đầu?

Chọn ngôn ngữ và bắt đầu hành trình tự động hóa:

1. **English**: [Bắt đầu với tài liệu tiếng Anh](./documents/en/README.md)
2. **Vietnamese**: [Bắt đầu với tài liệu tiếng Việt](./documents/vi/README.md)

---

_Hướng dẫn này được thiết kế để thân thiện với người mới bắt đầu. Mỗi bước đều bao gồm giải thích rõ ràng và hình ảnh hữu ích để hướng dẫn bạn qua quá trình._
