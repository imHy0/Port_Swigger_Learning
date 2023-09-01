# [Lab 1: SQLi vulnerability in `WHERE` clause allowing retrieval of hidden data](https://portswigger.net/web-security/sql-injection/lab-retrieve-hidden-data)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/68fbdac4-f5b0-4b72-a9bf-14f69f6f1881)
Đây là trang web chính của bài lab, ta dễ thấy các chức năng
- `Home`: trở về trang chính
- `Category`: lọc các kết quả tìm kiếm
- `View details`: xem thông tin sản phẩm

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/130b5981-46a9-4db2-b53e-880826786433)

Tìm hiểu các chức năng, ta phát hiện ra lỗi SQLi tại filter
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/57cf9519-1302-461d-9305-4f53276bb11a)
Quan sát response: lỗi 500 Internal Server Error
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/464ad41e-90c1-40c3-8961-14e9ece1b781)
Khi thêm `--` thì lại duyệt web bình thường
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/371a70ca-f9ed-40ff-a9f0-3240cd5dafec)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/915938f1-d46e-4679-87f1-784c107c7044)
Sau khi đã xác định lỗi SQLi, ta sẽ truy xuất các dữ liệu ẩn bằng cách thêm `OR 1=1` (câu lệnh luôn đúng nên sẽ trả về tất cả các dữ liệu do ở câu truy vấn gốc chỉ để hiển thị các dữ liệu đã release `released = 1`)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/40bddce4-38c0-4291-82a7-3b2763640422)
solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c41e576e-bc25-49dd-88c7-61cca77dc9da)

# [Lab 2: SQL injection vulnerability allowing login bypass](https://portswigger.net/web-security/sql-injection/lab-login-bypass)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/418ff7fc-9e31-498c-9eba-1245829a8241)

Đây là trang web chính của bài lab, ta thấy các chức năng
- Home
- View details
- My account: thông tin tài khoản

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/242b1ee8-52e8-42ec-b2fb-6679b27bd7a2)

Go to `My account`, đây là function chứa lỗi SQLi, ta sẽ tìm cách login vào tài khoản `administrator` mà không cần password

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d8c82073-620d-4339-ba9e-05aa76efc05e)
`'` để đóng chuỗi username lại và thêm -- để comment phần passsword ở sau trong câu lệnh query nên ta chỉ cần nhập 1 password bất kỳ (do web bắt buộc ta nhập) thì đều login thành công
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cc95b471-e0ee-40b6-8f53-27adb470bfe7)
solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/54cea845-407d-4586-ab27-3da46eca2210)
