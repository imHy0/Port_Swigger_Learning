# [Lab 1: Remote code execution via web shell upload](https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-web-shell-upload)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/36becddd-1e44-43db-b4b8-37a180826a3a)
Sau khi đã đăng nhập, sử dụng function Upload avatar để tải lên 1 file
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/22405f76-5f74-4479-8896-648e1935a875)

Thử update 1 file webshell có nội dung `<?php echo file_get_contents('/home/carlos/secret');?>`
→ thông báo đã update thành công
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/94c2c861-0d65-4aee-b872-1a39c2fb378b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0c9f92c5-d776-4ccf-bd1e-a739ef4a3b0c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/42f2af3f-f50b-49da-b8fb-43a6e2c07b97)

Xem nội dung file vừa update → đã lấy được content
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f79d3c46-4399-4755-9378-804128af84fa)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/711a4383-628c-422c-9b18-16b6679b19b9)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/01c8d60a-ad8f-4e62-bd17-403a83a7157b)

submit and solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5cc528d5-ca04-44c1-aecc-5459bed75a62)

