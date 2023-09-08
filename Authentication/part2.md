
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

## [Lab 8: 2FA broken logic](https://portswigger.net/web-security/authentication/multi-factor/lab-2fa-broken-logic)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8fd0fa78-9848-4196-a0b3-e6481dbe2af9)

login

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d1fd9e46-5e90-44ec-9584-82c87ad51cba)

phải nhập code

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a65be9f4-7428-4d25-9a79-7a32a2a1b776)

chú ý request có xác nhận username

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1133f443-a12a-4de8-8a33-0c6fb53e3f42)

vào gmail lấy code

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/75f699c6-975a-4879-9d7f-31284fe81d13)

nhập code và login thành công, redirect sang `/my-account?id=wiener`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d7cecaf9-c1bf-4be3-a40e-a2374890c19e)

nhập mã code cũng verify

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/646e9355-1849-4d46-8944-c5b118de4e82)

nhớ logout `wiener` trước khi test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4dc799cd-cffa-4ea9-b453-9cb8b9b5b3a0)

send request get login2 của account `carlos` để lấy mã code

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3f86342f-7c2a-42fe-8fdb-15f1b1286ee2)

sau khi đã có code gửi về mail, chắc chắn là ta không có mail để lấy rồi, brute force thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d1fb0d7c-baa4-4c8f-8505-f543d9701445)

ok đã tìm được code

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cd2395d5-6a1b-4315-9522-0557bdb101b0)

login và solve thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6480ff10-bd77-4620-8e27-3e4ef56c0e22)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d0d96db0-20f0-4185-b277-b2b6c3192823)
