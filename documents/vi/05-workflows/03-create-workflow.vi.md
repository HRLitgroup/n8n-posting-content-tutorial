# Tạo Quy Trình cho n8n

## Tổng Quan

Trước khi bắt đầu, hãy xem tổng quan quy trình để hiểu cấu trúc và hình dạng của nó.

![overview](../../../assets/workflows/steps/overview.png)

**Lưu ý**: Nếu bạn muốn bắt đầu nhanh chóng, bạn có thể tái sử dụng [quy trình của tôi](../../../exports/N8N%20Auto%20Posting%20Content.json)

- Tải xuống tệp JSON và nhập vào n8n
- Cập nhật thông tin xác thực với thông tin tài khoản của bạn (làm theo [tài liệu trước](../05-workflows/02-create-credentials.vi.md))
- Thế là xong! Quy trình tự động đăng nội dung n8n của bạn đã sẵn sàng thực thi.

## Tổng Quan Các Bước Quy Trình

| Bước | Hành Động                 | Mục Đích                                         | Nền Tảng           |
| ---- | ------------------------- | ------------------------------------------------ | ------------------ |
| 1    | Tạo Quy Trình             | Khởi tạo dự án quy trình mới                     | n8n                |
| 2    | Kích Hoạt Thủ Công        | Bắt đầu thực thi quy trình                       | n8n                |
| 3    | Lấy Dữ Liệu Google Sheets | Lấy nội dung có trạng thái 'ready'               | Google Sheets      |
| 4    | Tải Xuống Hình Ảnh        | Chuyển đổi URL hình ảnh sang định dạng nhị phân  | Google Drive       |
| 5    | Đăng Lên LinkedIn         | Chia sẻ nội dung trên LinkedIn                   | LinkedIn           |
| 6    | Đăng Lên Facebook         | Chia sẻ nội dung trên Facebook                   | Facebook Graph API |
| 7    | Tạo Bài Đăng WordPress    | Tải lên bài đăng không có hình ảnh lên WordPress | WordPress          |
| 8    | Lấy Hình Ảnh cho WP       | Tải xuống hình ảnh cho WordPress                 | Google Drive       |
| 9    | Tải Lên Media lên WP      | Tải lên hình ảnh lên WordPress                   | WordPress          |
| 10   | Cập Nhật Media vào Post   | Liên kết media đã tải lên với bài đăng WordPress | WordPress          |
| 11   | Cập Nhật Trạng Thái Sheet | Đánh dấu nội dung đã đăng và tăng bộ đếm         | Google Sheets      |

## Bước 1

Trên trang chủ, nhấp vào 'Create Workflow'.
![step1.1](../../../assets/workflows/steps/step1.1.png)

Tiếp theo, đặt tên dự án thành 'N8N Auto Posting Content' và nhấp Save.
![step1.2](../../../assets/workflows/steps/step1.2.png)

Sau đó, nhấp vào nút 'Add first step...'.

## Bước 2

Chúng ta sẽ sử dụng node Manual trigger, có nghĩa là n8n sẽ chạy quy trình khi chúng ta nhấp vào 'Execute Workflow'.

![step2](../../../assets/workflows/steps/step2.png)

## Bước 3

Nhấp vào nút +, tìm kiếm 'Google Sheets', và chọn nó.
![step3.1](../../../assets/workflows/steps/step3.1.png)

Chúng ta sẽ sử dụng hành động 'Get row(s) in sheet' để lấy tất cả nội dung có trạng thái 'ready'.
![step3.2](../../../assets/workflows/steps/step3.2.png)

Làm theo hướng dẫn bên dưới (nhớ kết nối node này với node trigger từ Bước 2):

1. Chọn kết nối thông tin xác thực Google Sheets của bạn
2. Chọn tài liệu của bạn (n8n_contents) và chỉ mục sheet (Sheet1)
3. Thêm bộ lọc để lấy bản ghi có trạng thái 'ready':
   - Chọn cột: status
   - Đặt giá trị thành: 'ready'
4. Nhấp vào 'Execute Step'
5. Kết quả thành công hoặc thất bại sẽ xuất hiện ở bên phải
   ![step3.3](../../../assets/workflows/steps/step3.3.png)

## Bước 4

Nhấp vào nút +, tìm kiếm 'Google Drive', và chọn nó.
![step4.1](../../../assets/workflows/steps/step4.1.png)

Chúng ta sẽ sử dụng hành động 'Download file' để chuyển đổi hình ảnh từ URL sang định dạng nhị phân, vì các nền tảng mạng xã hội chỉ chấp nhận hình ảnh ở định dạng nhị phân.
![step4.2](../../../assets/workflows/steps/step4.2.png)

Làm theo hướng dẫn bên dưới (nhớ kết nối node này với node Google Sheets từ Bước 3):

1. Chọn kết nối thông tin xác thực Google Drive của bạn
2. Trong trường File, thay đổi dropdown bên trái thành 'By URL'
3. Kéo và thả trường 'image' vào trường giá trị File bên phải (xem hình để biết chi tiết)
4. Nhấp vào 'Execute Step'
5. Kết quả thành công hoặc thất bại sẽ xuất hiện ở bên phải
   ![step4.3](../../../assets/workflows/steps/step4.3.png)

## Bước 5

Nhấp vào nút +, tìm kiếm 'LinkedIn', và chọn nó.
![step5.1](../../../assets/workflows/steps/step5.1.png)

Chọn hành động 'Create a post'.
![step5.2](../../../assets/workflows/steps/step5.2.png)

Làm theo hướng dẫn bên dưới (nhớ kết nối node này với node Google Drive từ Bước 4):

1. Chọn kết nối thông tin xác thực 'LinkedIn account' của bạn
2. Từ góc trên bên trái, thay đổi tab hiện tại thành 'Schema'
3. Kéo và thả trường 'content' vào trường giá trị Text ở giữa (xem hình để biết chi tiết)
4. Trong 'Input Binary Field', nhập giá trị: 'data'
5. Nhấp vào 'Execute Step'
6. Kết quả thành công hoặc thất bại sẽ xuất hiện ở bên phải
   ![step5.3](../../../assets/workflows/steps/step5.3.png)

## Bước 6

Nhấp vào nút +, tìm kiếm 'Facebook Graph API', và chọn nó.
![step6.1](../../../assets/workflows/steps/step6.1.png)

Làm theo hướng dẫn bên dưới (nhớ kết nối node này với node Google Drive từ Bước 4):

1. Chọn kết nối thông tin xác thực 'Facebook Graph account' của bạn
2. Từ góc trên bên trái, thay đổi tab hiện tại thành 'Schema'
3. Cấu hình các trường:
   - HTTP Request Method: POST (được sử dụng để tạo yêu cầu đăng tin nhắn mới lên Facebook API)
   - Graph API Version: Chọn phiên bản mới nhất (hiện tại là v23.0)
   - Node: me
   - Edge: photos (được sử dụng để đăng tin nhắn mới với hình ảnh)
4. Bật 'Send Binary File' và đặt Input Binary Field thành 'data'
5. Trong Options, tạo một Query Parameter mới với:
   - Name: message
   - Value: Kéo và thả trường 'content' vào trường Value (xem hình để biết chi tiết)
6. Nhấp vào 'Execute Step'
7. Kết quả thành công hoặc thất bại sẽ xuất hiện ở bên phải
   ![step6.2](../../../assets/workflows/steps/step6.2.png)

# Lưu ý: Từ bước 7 ~ 10, vui lòng ghi nhớ tên node vì nó sẽ được tham chiếu trong các trường node con khi tái sử dụng sau này

## Bước 7: Tải lên bài đăng không có hình ảnh vào wordpress

Tìm node **Create a post**, bạn cũng có thể thay đổi tên của node - chỉ cần nhớ tên của node
Trong trường hợp của tôi, tôi sẽ giữ node này với tên **Create a post**

![step7.1](../../../assets/workflows/steps/step7.1.png)

## Bước 8: Tạo node để lấy hình ảnh cho wordpress

Lặp lại [Bước 4](#bước-4) để tạo node tải xuống tệp mới, nhưng nhớ lần này chúng ta thay đổi tên node thành **get_images_wp**

![step8.1](../../../assets/workflows/steps/step8.1.png)

## Bước 9: Tải lên hình ảnh lên wordpress

Tìm và sử dụng node **HTTP Request** sau đó đổi tên thành **Upload media to WP**

![step9.1](../../../assets/workflows/steps/step9.1.png)

Cấu hình giống như hình, chỉ cần lưu ý về URL. Cú pháp của URL sẽ là

```code
${your-url-wordpress} + '/wp-json/wp/v2/media'
```

Trong trường hợp của tôi: `https://litgroup.io/wp-json/wp/v2/media`

![step9.2](../../../assets/workflows/steps/step9.2.png)

- Tham số Header:

```code
[
   {
      name: 'content-disposition',
      value: `attachment; filename={{ $binary.data.fileName }}`
   },
   {
      name: 'content-type',
      value: `{{ $binary.data.mimeType }}`
   }
]
```

## Bước 10: Cập nhật media vào Post WP

Tìm và sử dụng node **HTTP Request** sau đó đổi tên thành **Update media to Post WP**

![step10.1](../../../assets/workflows/steps/step10.1.png)

Cấu hình giống như hình, chỉ cần lưu ý về URL. Cú pháp của URL sẽ là

```code
${your-url-wordpress} + '/wp-json/wp/v2/posts/' + ${posted_id}
```

Trong trường hợp của tôi: `https://litgroup.io/wp-json/wp/v2/posts/{{ $('Create a post').item.json.id }}`

![step10.2](../../../assets/workflows/steps/step10.2.png)

- Tham số Header:

```code
[
   {
      name: 'featured_media',
      value: `{{ $('Upload media to WP').item.json.id }}`
   },
]
```

Lưu ý: **\$('Create a post')** và **\$('Upload media to WP')** là tên của các node ở [bước 7](#bước-7-tải-lên-bài-đăng-không-có-hình-ảnh-vào-wordpress) và [bước 9](#bước-9-tải-lên-hình-ảnh-lên-wordpress)

## Bước 11

Nhấp vào nút +, tìm kiếm 'Google Sheets', và chọn nó.
Chúng ta sẽ sử dụng hành động 'Update row in sheet' để cập nhật trạng thái thành 'posted' và tăng posted_time lên 1.
![step12.1](../../../assets/workflows/steps/step12.1.png)

Làm theo hướng dẫn bên dưới (nhớ kết nối node này với cả node LinkedIn, Facebook và Wordpress từ Bước 5, 6 & 10):

1. Chọn kết nối thông tin xác thực 'Google Sheets account' của bạn
2. Cấu hình các trường:
   - Resource: Sheet Within Document
   - Operation: Update Row
   - Document and Sheet: Chọn tài liệu của bạn (n8n_contents) và chỉ mục sheet (Sheet1)
   - Mapping Column Mode: Map Each Column Manually
   - Column to match on: Chọn trường 'no'
3. Trong trường 'Value to Update':
   - Kéo và thả trường 'no' vào trường **no (using to match)**
     ![step12.2](../../../assets/workflows/steps/step12.2.png)
   - Trong trường status, đặt giá trị thành 'posted'
   - Trong trường posted_time, kéo và thả 'posted_time' vào giá trị của posted_time ở giữa (xem hình để biết chi tiết), sau đó thêm `+ 1` trước cuối `}}`
     ![step12.3](../../../assets/workflows/steps/step12.3.png)
4. Nhấp vào 'Execute Step'
5. Kết quả thành công hoặc thất bại sẽ xuất hiện ở bên phải

---

# Tham khảo tạo kết nối N8N cho Wordpress [tại đây](https://www.youtube.com/watch?v=xioMvEWt-NE)

---

**Trước**: [Tạo Thông Tin Xác Thực](./02-create-credentials.vi.md)  
**Tiếp**: [Quay Lại Tổng Quan Quy Trình](./n8n-workflow.vi.md)
