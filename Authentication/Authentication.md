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
  - username enumeration: (lab 1, 2, 3)
    - Status codes
    - Error messages
    - Response times
  - Flawed brute-force protection (lab 4)
    - 2 cách phổ biến ngăn chặn brute-force
      - khóa tài khoản mà người dùng từ xa đang cố đăng nhập quá nhiều lần không thành công
      - chặn địa chỉ IP của người dùng từ xa nếu thực hiện nhiều lần liên tục
    - Account locking (lab 5)
    - User rate limiting (lab 6)
- HTTP basic authentication

[5.2. Lỗ hổng trong xác thực đa yếu tố](part2.md)

- Bỏ qua xác thực hai yếu tố (lab 7)

Nếu người dùng được nhắc nhập mật khẩu lần đầu tiên, sau đó được nhắc nhập mã xác minh trên một trang riêng, thì người dùng thực sự ở trạng thái "đăng nhập" trước khi họ nhập mã xác minh. Trong trường hợp này, bạn nên kiểm tra xem liệu bạn có thể trực tiếp chuyển sang trang "chỉ đăng nhập" sau khi hoàn thành bước xác thực đầu tiên hay không. Đôi khi, bạn sẽ thấy rằng một trang web không thực sự kiểm tra xem bạn có hoàn thành bước thứ hai trước khi tải trang hay không.

- Logic xác minh hai yếu tố thiếu sót (lab 8)

Đôi khi logic thiếu sót trong xác thực hai yếu tố có nghĩa là sau khi người dùng hoàn thành bước đăng nhập ban đầu, trang web không xác minh đầy đủ rằng chính người dùng đó đang hoàn thành bước thứ hai.

- Brute forcing mã xác minh 2FA (lab 9) [EXPERT]

[5.3. Lỗ hổng trong các cơ chế xác thực khác](part3.md)

- Keeping users logged in (lab 10, 11)

- Resetting user passwords
  - using URL (lab 12, 13)

- Changing user passwords (lab 14)

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
