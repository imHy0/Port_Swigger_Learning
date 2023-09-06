## **_1. Định nghĩa_**

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c0331a36-3e82-47d2-b181-54a587a56475)

- Mã thông báo web JSON (JWT) là một định dạng được chuẩn hóa để gửi dữ liệu JSON được ký bằng mật mã giữa các hệ thống. Về mặt lý thuyết, chúng có thể chứa bất kỳ loại dữ liệu nào, nhưng được sử dụng phổ biến nhất để gửi thông tin ("khiếu nại") về người dùng như một phần của xác thực, xử lý phiên và cơ chế kiểm soát truy cập.

- Định dạng JWT: 3 phần
  - Header: chứa metadata về token
  - Payload: chứa thông tin xác thực người dùng
    --> chỉ là các đối tượng JSON được mã hóa base64url
  - Signature:
 
  ## **_Khai thác_**

  [Khai thác xác minh chữ ký JWT thiếu sót](part1.md)

  - Chấp nhận chữ ký tùy tiện (lab 1)
  - 
