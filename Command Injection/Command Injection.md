## **_1. Định nghĩa_**

OS command Injection (shell injection) là một lỗ hổng bảo mật web cho phép kẻ tấn công có thể inject một lệnh OS tùy ý.
(lab 1)

## **_2. Ảnh hưởng_**

- Rò rỉ dữ liệu trên máy chủ
- Thực thi lệnh hệ thống, khai thác leo quyền máy chủ

## **_3. Phòng chống_**

- Thực hiện kiểm tra Input của người dùng nhập vào, có thể sử dụng Whitelist để kiểm tra
- Giới hạn các kí tự được phép sử dụng như là số hoặc chữ
- Thực hiện kiểm tra Input chỉ chứa các kí tự hoặc số, không có các syntax của command, kí tự đặc biệt hoặc khoảng trắng.
- Sử dụng escape dữ liệu

## **_4. How to test_**

### **_Tìm kiếm_**
- Sử dụng dấu **chấm phẩy** `;` để chạy một câu lệnh thứ hai
- Sử dụng biểu thức
  - **`&&`** (Câu lệnh trước đó phải TRUE)
  - `||` (Câu lệnh trước đó phải FALSE)
- Sử dụng **Pipeline** `|`
- Sử dụng **backticks**
  - \`whoami\`
  - `$(whoami)`
- Sử dụng việc chạy **background** `&`
- Newline (or `0x0a` `\n`)

### **_Tìm kiếm Blind_**

- **Out-Of-Band (OOB)**
  - ping
  - telnet
  - curl
  - wget
  - nslookup
  - dig
  - trace
  - netcat / nc
  - ftp
  - ssh
- Máy chủ không có DNS, thì không phân giải được tên miền, **sử dụng các lệnh làm việc với IP** (ping)
- Máy chủ không có kết nối Internet ra ngoài, thì **sử dụng các hàm làm Sleep**

## **_5. Blind OS Command Injection_**

- Khai thác bằng cách sử dụng time delays: **ping** (lab 2)
- Khai thác bằng cách chuyển hướng đầu ra: `>` (lab 3)
- Khai thác sử dụng OOB (lab 4, 5)
