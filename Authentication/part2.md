
## [Lab 7: 2FA simple bypass](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-simple-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b8dbfead-3772-4cc5-bf38-4fc7445e32e9)

login with `wiener:peter`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ae723540-53b6-4add-b3c7-c111da85ebad)

sẽ được gửi 1 mã code qua mail

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7a6db2cc-ddc4-453d-8f21-67526e4a4104)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a28b7acc-feea-44ab-9064-88590bd5c28b)

nhập mã và login

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2221082b-18aa-4563-8734-15d3a3afd337)

sau khi login sẽ redirect ta đến `/my-account?id=wiener`, ghi nhớ endpoint này để xem lát nữa có bypass được code không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a09383a4-8be1-4e86-9c23-6fcbd4c50e85)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/544ec09d-83c1-4b4a-896e-ebafb9655b61)

bây giờ ta sẽ đăng nhập với `carlos:montoya` và hiển nhiên là sẽ yêu cầu nhập code, tuy nhiên thì không có email nên code ta không thể lấy được, xác thực 2 yếu tố bài này có thể bypass, giờ ta sẽ truy cập đến endponint `/my-account?id=carlos` xem sao

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6a384194-c137-4dce-bb22-b66374d82bd8)

solve the lab luôn chứ sao

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ae50ace2-57ec-4290-8f62-dc66bd482979)

##
