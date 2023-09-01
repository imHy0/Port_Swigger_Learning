# **_1. SQLi là gì?_**
- **SQLi** là một lỗ hổng bảo mật web cho phép kẻ tấn công can thiệp vào các truy vấn mà ứng dụng thực hiện đối với cơ sở dữ liệu của nó. Nó thường cho phép kẻ tấn công xem dữ liệu mà thông thường họ không xem được, thậm chí kẻ tấn công có thể sửa đổi hoặc xóa dữ liệu này, gây ra ảnh hưởng nghiêm trọng.
# **_2. Ảnh hưởng_**
- Kẻ tấn công truy cập trái phép vào dữ liệu nhạy cảm, chẳng hạn như mật khẩu, thông tin người dùng, ...
- Trong một số trường hợp kẻ tấn công có thể có được một cửa hậu liên tục xâm nhập vào hệ thống của tổ chức, dẫn đến xâm phạm lâu dài mà có thể không được chú ý trong một thời gian dài.
# **_3. Cách phát hiện lỗ hổng SQLi_**
- Gửi ký tự nháy đơn `'`  và tìm kiếm lỗi hoặc các điểm bất thường khác
- Gửi một số cú pháp dành riêng cho SQL để đánh giá giá trị cơ sở (gốc) và một giá trị khác đồng thời tìm kiếm sự khác biệt mang tính hệ thống trong các phản hồi thu được.
- Gửi các điểu kiện `Boolean` như  `OR 1=1` và `OR 1=2` và tìm kiếm sự khác biệt trong phản hồi
- Gửi các cú pháp kích hoạt độ trễ thời gian khi được thực thi trong truy vấn SQL và tìm kiếm sự khác biệt về thời gian cần thiết để phản hồi
- Gửi tải trọng OAST được thiết kế để kích hoạt tương tác OOB khi được thực thi trong truy vấn SQL và giám sát mọi tương tác phát sinh
# **_4. Các vị trí phổ biến_**
- UPDATE: `WHERE` clause
- INSERT: insert values
- SELECT: table or column name, `ORDER BY` clause
# **_5. Các dạng SQLi phổ biến_**

### [5.1. Ví dụ về SQLi](part1.md)
- Truy xuất dữ liệu ẩn (lab 1)
- Phá vỡ logic ứng dụng (lab 2)
- Truy xuất dữ liệu từ bảng khác
### [5.2. Kiểm tra database](part2.md)
- Syntax
- Comments
- error message...
- Truy vấn loại và phiên bản cơ sở dữ liệu (lab 3, 4)
- Liệt kê nội dung của cơ sở dữ liệu (lab 5, 6)
### [5.3. UNION attacks](part3.md)
- Xác định số cột (lab 7)
- Tìm data (lab 8, 9)
- Truy xuất nhiều giá trị trong 1 cột (lab 10)
### [5.4. Blind SQLi](part4.md)
- **Blind SQLi**__ là gì?
- Khai thác bằng cách kích hoạt các phản hồi có điều kiện (lab 11)
- Error-based
  - Khai thác bằng cách kích hoạt các lỗi có điều kiện (lab 12)
  - Trích xuất dữ liệu nhạy cảm thông qua các thông báo lỗi SQL dài dòng (lab 13)
- Khai thác tính năng chèn SQL mù bằng cách kích hoạt độ trễ thời gian (lab 14, 15)
- OOB (lab 16, 17)
### SQLi in different contexts (lab 18)
