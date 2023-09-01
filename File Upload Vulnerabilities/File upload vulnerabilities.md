# _1. File upload vulnerabilities là gì?_
- File upload vulnerabilities (Lỗ hổng tải lên tệp) là khi máy chủ web cho phép người dùng tải tệp lên hệ thống tệp của nó mà không xác thực đầy đủ tên, loại, nội dung hoặc kích thước của chúng.
→ gây nguy hiểm, người dùng có thể tải lên tập tùy ý thậm chí có thể là các tệp tập lệnh phía máy chủ cho phép thực thi mã từ xa.
# _2. Ảnh hưởng: phụ thuộc vào 2 yếu tố chính_
* trang web không xác thực đúng cách: tên, loại,...
* những hạn chế được áp dụng khi tải tệp thành công
# _3. Một số loại phổ biến_
## [**3.1. Khai thác tải lên tệp không hạn chế để triển khai web shell**](part1.md)
* Web shell là một tập lệnh độc hại cho phép kẻ tấn công thực hiện các lệnh tùy ý trên máy chủ web từ xa chỉ bằng cách gửi các yêu cầu HTTP đến đúng điểm cuối.
Nếu bạn có thể tải lên thành công một web shell, bạn có toàn quyền kiểm soát máy chủ một cách hiệu quả. Điều này có nghĩa là bạn có thể đọc và ghi các tệp tùy ý, trích xuất dữ liệu nhạy cảm, thậm chí sử dụng máy chủ để xoay các cuộc tấn công chống lại cả cơ sở hạ tầng nội bộ và các máy chủ khác bên ngoài mạng.
## [**3.2. Khai thác xác thực thiếu sót của tệp tải lên**](part2.md)
3.2.1. Xác thực loại tệp bị thiếu sót

3.2.2. Ngăn chặn việc thực thi tệp trong các thư mục mà người dùng có thể truy cập

3.2.3. Danh sách đen không đầy đủ các loại tệp nguy hiểm
* Ghi đè cấu hình máy chủ
* Làm xáo trộn phần mở rộng tập tin

3.2.4. Xác thực sai sót nội dung của tập tin

3.2.5. Khai thác các điều kiện tải lên tệp (Race conditions)

# **_4. Phòng chống_**
