# Bước 1: Cài Đặt Docker Desktop

## 🎯 Docker Desktop Là Gì và Tại Sao Bạn Cần Nó?

**Docker Desktop** là một công cụ giúp chạy các ứng dụng trong môi trường an toàn trên máy tính của bạn. Hãy nghĩ về nó như một "hộp cát" cho phép N8N chạy mà không ảnh hưởng đến các chương trình khác trên máy tính.

### ✅ Bạn Sẽ Có Gì

- Môi trường an toàn để chạy N8N
- Không xung đột với phần mềm hiện có
- Khả năng chạy nhiều ứng dụng cùng lúc
- Công cụ mạnh mẽ cho tự động hóa

## 🛠️ Bạn Cần Gì Trước Khi Bắt Đầu

Đảm bảo bạn có:

- ✅ Máy tính Windows 10/11, Mac, hoặc Linux
- ✅ Khoảng 10-15 phút để cài đặt
- ✅ Quyền quản trị trên máy tính
- ✅ Kết nối internet ổn định

## 📥 Cài Đặt Từng Bước

### Bước 1: Tải Docker Desktop

1. **Mở trình duyệt web**
2. **Đi đến trang Docker**: [Nhấp vào đây để truy cập](https://www.docker.com/get-started/)
3. **Tìm nút "Download for [Hệ Điều Hành]"** - Docker sẽ tự động phát hiện máy tính của bạn
4. **Nhấp nút tải xuống** và chờ tải xuống hoàn tất

### Bước 2: Cài Đặt Docker Desktop

#### Cho Người Dùng Windows:

1. **Tìm tệp đã tải xuống** - Thường trong thư mục Downloads
2. **Nhấp đúp vào tệp** để bắt đầu cài đặt
3. **Làm theo trình hướng dẫn**:
   - Nhấp "Next" khi được nhắc
   - Chấp nhận thỏa thuận giấy phép
   - Chọn vị trí cài đặt mặc định
   - Nhấp "Install"
4. **Chờ cài đặt hoàn tất**
5. **Nhấp "Finish"** khi xong

#### Cho Người Dùng Mac:

1. **Tìm tệp đã tải xuống** - Thường trong thư mục Downloads
2. **Nhấp đúp vào tệp** để bắt đầu cài đặt
3. **Kéo Docker vào thư mục Applications** khi được nhắc
4. **Mở Docker** từ thư mục Applications

#### Cho Người Dùng Linux:

1. **Tìm tệp đã tải xuống** - Thường trong thư mục Downloads
2. **Nhấp đúp vào tệp** để bắt đầu cài đặt
3. **Làm theo hướng dẫn trình cài đặt gói** của hệ thống

### Bước 3: Khởi Động Docker Desktop

1. **Tìm Docker Desktop** trong menu/start menu
2. **Nhấp để mở Docker Desktop**
3. **Chờ Docker khởi động** - Bạn sẽ thấy biểu tượng cá voi trong thanh tác vụ
4. **Đăng nhập hoặc đăng ký** nếu được nhắc

Sau khi cài đặt và đăng nhập, Docker Desktop sẽ trông như thế này:

![Demo docker desktop](../../../assets/setup/docker-desktop.png)

### Bước 4: Xác Minh Cài Đặt

Kiểm tra rằng Docker đã cài đặt đúng cách:

#### Cho Người Dùng Windows:

1. **Nhấn Windows key + R**
2. **Gõ "cmd" và nhấn Enter**
3. **Gõ lệnh này**: `docker --version`
4. **Nhấn Enter** - Bạn sẽ thấy thông tin phiên bản

#### Cho Người Dùng Mac:

1. **Mở Terminal** (sử dụng Spotlight search cho "Terminal")
2. **Gõ lệnh này**: `docker --version`
3. **Nhấn Enter** - Bạn sẽ thấy thông tin phiên bản

#### Cho Người Dùng Linux:

1. **Mở Terminal**
2. **Gõ lệnh này**: `docker --version`
3. **Nhấn Enter** - Bạn sẽ thấy thông tin phiên bản

**Kết quả mong đợi** (đừng lo về số chính xác):

```
Docker version 20.10.x, build xxxxxxx
```

Nếu cài đặt thành công, việc kiểm tra phiên bản sẽ trông như thế này:

![Check version docker](../../../assets/setup/check-version-docker.png)

## ✅ Cách Kiểm Tra Cài Đặt Có Hoạt Động Không

1. **Docker Desktop nên chạy** với trạng thái xanh
2. **Biểu tượng cá voi** nên xuất hiện trong thanh tác vụ
3. **Lệnh `docker --version`** nên hiển thị phiên bản

## 🚨 Khắc Phục Sự Cố

### Docker Không Khởi Động?

- **Khởi động lại máy tính** và thử lại
- **Kiểm tra máy tính có đáp ứng yêu cầu**:
  - Windows 10/11 hoặc mới hơn
  - Mac: macOS 10.14 hoặc mới hơn
  - Linux: Ubuntu 16.04+ hoặc tương tự

### Cài Đặt Thất Bại?

- **Thử tải xuống lại** từ trang web chính thức
- **Tạm thời tắt phần mềm diệt virus** trong quá trình cài đặt
- **Chạy với quyền quản trị** (người dùng Windows)

### Vẫn Có Vấn Đề?

- **Kiểm tra hướng dẫn khắc phục sự cố chính thức của Docker**: [Docker Desktop Troubleshooting](https://docs.docker.com/desktop/troubleshoot/)
- **Yêu cầu giúp đỡ** trong diễn đàn cộng đồng N8N

## 🎉 Bạn Sẵn Sàng Cho Bước Tiếp Theo!

Sau khi Docker Desktop được cài đặt và chạy đúng cách, bạn sẵn sàng chuyển sang bước tiếp theo.

**Tiếp Theo**: [Cài Đặt VSCode](../02-vscode/01-install-vscode.vi.md) - Trình soạn thảo không gian làm việc tự động hóa.

---

_💡 **Mẹo**: Giữ Docker Desktop chạy trong nền. Bạn sẽ cần nó cho các bước tiếp theo._
