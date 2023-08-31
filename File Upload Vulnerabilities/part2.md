# [Lab 2: Web shell upload via Content-Type restriction bypass](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-content-type-restriction-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e6f79527-a963-46ad-8fa8-503bde488f05)

vẫn là đăng nhập và thử update 1 file webshell
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/62d89ca6-54cd-46da-b5f3-1061f76c3374)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ec72e803-00b6-45d0-94e7-7d416f9730b3)

tuy nhiên chú ý đến thông báo nhận được ta dễ dàng thấy rằng type application/octet-stream đã thấy ở trong Content-Type đã bị chặn và chỉ cho phép type là image/jpeg
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ee866f1b-bd97-4617-b03e-c3eebe1a36c2)

vẫn request đó ta sẽ sửa Content-Type về image/jpeg và thấy đã upload thành công
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7cf5cde2-a4bb-4616-ba6c-609b48b33dc3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0ee0bfeb-ce37-4236-8f2c-13f7fe233238)

lấy content nhận được submit và solve thôi
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/54a5e8f0-2006-4db3-a739-e799313d8d91)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1e48fea7-829c-436d-973c-0d7a7cb50792)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4addb8e5-1ab3-4aed-96d2-c566fd80890f)

# [Lab 3: Web shell upload via path traversal](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-path-traversal)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c69dda52-9901-4e95-8f90-171f6ce32dae)


