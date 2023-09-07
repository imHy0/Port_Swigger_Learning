## **_1. Định nghĩa_**

- **Access control (hoặc Authorization)** là việc áp dụng các ràng buộc về ai (hoặc cái gì) có thể thực hiện các hành động đã cố gắng hoặc truy cập tài nguyên mà họ đã yêu cầu. Trong ngữ cảnh của ứng dụng web, kiểm soát truy cập phụ thuộc vào xác thực và quản lý phiên:
  - Xác thực xác định người dùng và xác nhận rằng họ đúng như họ nói.
  - Quản lý phiên xác định những yêu cầu HTTP tiếp theo nào đang được thực hiện bởi cùng một người dùng.
  - Kiểm soát truy cập xác định xem người dùng có được phép thực hiện hành động mà họ đang cố gắng thực hiện hay không.

- **Broken access control** là một lỗ hổng bảo mật thường gặp và thường nghiêm trọng. Thiết kế và quản lý các biện pháp kiểm soát truy cập là một vấn đề phức tạp và năng động, áp dụng các ràng buộc về kinh doanh, tổ chức và pháp lý vào việc triển khai kỹ thuật. Các quyết định thiết kế kiểm soát truy cập phải được thực hiện bởi con người chứ không phải công nghệ và khả năng xảy ra lỗi là rất cao.

- Từ góc độ người dùng, kiểm soát truy cập có thể được chia thành các loại sau:
  - **Quản lý truy cập theo chiều dọc**: giới hạn quyền truy cập vào các chức năng hoặc dữ liệu nhạy cảm theo đặc quyền tối thiểu. Các nhóm đặc quyền (nhóm người dùng) khác nhau thì có quyền truy cập vào các chức năng khác nhau
  - **Kiểm soát truy cập theo chiều ngang**: giới hạn quyền truy cập vào tài nguyên đối với những ai được phép hoặc 
sở hữu cụ thể tài nguyên đó. Tức là chỉ có tôi mới xem và cập nhật dữ liệu của tôi, nếu tôi xem hoặc sửa đổi được dữ liệu của người khác thì đó là lỗi Ví dụ, một ngân hàng sẽ cho phép người dùng xem lịch sử giao dịch và thanh toán từ
tài khoản của họ chứ không phải từ một người khác.
  - **Kiểm soát truy cập theo vào ngữ cảnh**: việc hạn chế truy cập vào chức năng và tài nguyên dựa trên trạng thái của ứng dụng. Điều này để ngăn chặn người dùng thực hiện một hành động sai logic. Ví dụ, trang web bán hàng không cho phép người dùng sửa đổi số lượng hàng trong hoá đơn sau khi đã thanh toán.


![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ee1f8fd1-34a7-4918-a683-1d9df9c3ae94)

## **_2. Broken Access Control_**

2.1. Leo thang đặc quyền theo chiều dọc: người dùng có quyền truy cập vào chức năng mà học không được phép truy cập

- Chức năng không được bảo vệ (lab 1, 2)
  - Trong một số trường hợp, URL quản trị có thể được tiết lộ ở các vị trí khác, chẳng hạn như tệp `robots.txt` hay tệp `sitemap.xml`
  - Ví dụ: các chức năng quản trị có thể được liên kết từ trang chào mừng của quản trị viên nhưng không được liên kết từ trang chào mừng của người dùng. Tuy nhiên, người dùng có thể chỉ cần truy cập các chức năng quản trị bằng cách duyệt trực tiếp đến URL quản trị viên có liên quan. --> tìm kiếm các `endpoint` trong js, tìm kiếm trong HTML Comment

- Phương pháp kiểm soát truy cập dựa trên tham số (lab 3, 4)
  - Sau khi đăng nhập, một số ứng dụng sử dụng các Hidden Fields, Cookie hoặc Query Parameter để kiểm soát đặc 
quyền.
  - Những giá trị này có thể dễ dàng quan sát và sửa đổi trong Burp Suite

- Kiểm soát truy cập bị hỏng do cấu hình sai nền tảng (lab 5, 6)

2.2. 
