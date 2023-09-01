# ***1. Authentication (xác thực) là gì?:***
- xác minh danh tính của người dùng
___
# ***2. Sự khác biệt Authentication (xác thực) và Authorization (ủy quyền)***

| Authentication (xác thực)  | Authorization (ủy quyền)         |
| ----- | ------------- |
| xác thực danh tính người dùng (có thực sự là người mà họ tuyên bố không) | xác thực quyền của người dùng (có được phép làm điều gì đó hay không) |
| **VD:** xác thực người dùng có tài khoản abcxyz có thực sự chính là người tạo tài khoản này không  | **VD:** sau khi được xác thực, liệu anh ta có được ủy quyền ?? chẳng hạn như xem hoặc xóa thông tin người dùng khác, … |
___
# ***3. Lỗ hổng Authentication được phát sinh như thế nào?***
- Cơ chế xác thực yếu
- Lỗi logic hoặc mã hóa kém trong quá trình triển khai → kẻ tấn công có thể bỏ qua cơ chế xác thực
___
# ***4. Ảnh hưởng***
- Kẻ tấn công có quyền truy cập vào dữ liệu và chức năng mà tài khoản bị xâm nhập.
  - ***Nghiêm trọng:*** Nếu tài khoản bị xâm nhập là tài khoản có đặc quyền cao như `administrator` thì họ có thể có toàn quyền kiểm soát hệ thống
  - ***Nhẹ:*** Còn nếu là tài khoản có đặc quyền thấp hơn thì rất dễ lộ thông tin người dùng cung cấp thêm thông tin để dễ bề tấn công…
___
# ***5. Một số lỗ hổng phổ biến***
[5.1. Lỗ hổng trong đăng nhập dựa trên mật khẩu](part1.md)
- Brute-force Attacks
  - brute-forcing usernames → tên người dùng dễ đoán, phổ biến
  - brute-forcing passwords → mật khẩu yếu, dễ đoán, phổ biến
  - username enumeration:
    - Status codes
    - Error messages
    - Response times
  - Flawed brute-force protection
    - 2 cách phổ biến ngăn chặn brute-force
      - khóa tài khoản mà người dùng từ xa đang cố đăng nhập quá nhiều lần không thành công
      - chặn địa chỉ IP của người dùng từ xa nếu thực hiện nhiều lần liên tục
    - Account locking
    - User rate limiting
- HTTP basic authentication
___
# ***6. Ngăn chặn***
- Sử dụng Captcha cho tất cả Form
- Giới hạn số lần đăng nhập sai cho một địa chỉ IP
- Giới hạn số lần đăng nhập sai cho endpoint `/login`, `/register`
- Đào tạo lập trình an toàn
- Đào tạo nhận thức bảo mật cho nhân viên để không chia sẻ tài khoản email, username lên MXH
- Chỉ trả về thông báo lỗi chung chung, ví dụ `Wrong username & password`
- Triển khai 2FA
- Tắt chức năng List Users (Disable WP JSON API)
- Slow Down Repeat Logins
- Giám sát các hoạt động đăng nhập bất thường. Ví dụ đăng nhập ngoài giờ hành chính
- Sử dụng các mật khẩu mạnh
- Không sử dụng các mật khẩu mặc định
- Thường xuyên thay đổi các mật khẩu mặc định của tổ chức
- Sử dụng OAuth bằng Google, Microsoft,..
