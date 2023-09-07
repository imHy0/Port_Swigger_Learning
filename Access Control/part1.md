![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3c73bc80-7863-4e86-a202-230afea54cf3)## [Lab 1: Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b9d8011f-7278-49ce-a86e-1bae90703623)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3c3dcc63-f88c-4c2b-a091-f9249a244bf1)

tìm kiếm trong HTML cũng không phát hiện được gì

dirsearch xem có đường dẫn nhạy cảm không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/97ab6f51-563c-426d-aad8-d1119e547dcf)

phát hiện thấy có file `robots.txt`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f8e912e4-854f-4ccb-8335-726177e72179)

phát hiện đường dẫn endpoint `/administrator-panel`, go to

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/46f3db67-1838-4c9f-a51b-1b16a29c5c8c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/84ebd117-6ec7-4521-9d1e-ef644c3b30df)

delete `carlos` and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/45d2b532-d841-4123-8006-92c9a9083f32)

## [Lab 2: Unprotected admin functionality with unpredictable URL](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality-with-unpredictable-url)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cde73000-3f45-42e2-beda-bd18caac2968)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/60aa1e38-10eb-48cb-a9c9-49a6c4f6ab67)

tìm kiếm trong HTML thì phát hiện luôn rồi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/aa730386-ae91-40b4-82e3-a78401a5eeba)


go to `/admin-eiev4j`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/87706d74-1672-415f-9206-f1bb029b1d64)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3ada2bac-15bd-4909-9171-67d5bcbe1e66)

delete `carlos` and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bcd75110-b5e4-476d-b367-a2ca6fdb4ae2)

## [Lab 3: User role controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-role-controlled-by-request-parameter)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/68049ffc-0877-4817-a039-f7901ba578a0)

sau khi login with `wiener:peter`, ta thấy session có phần xác nhận là admin `Admin=false`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/63d2d2e3-b2fa-4beb-9106-6b6ef2b2dead)

sử dụng dirsearch ta thấy 1 số đường dẫn `/admin` đã bị cấm truy cập

go to endpoint `/admin`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f0846921-5b5a-4d48-8875-62ca1da48ffd)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/349fa3e5-e32e-43c8-ae77-3176f1ad5a91)

ta vẫn thấy có `Admin=false` và kết quả truy cập thì đã bị từ chối do ta không phải là admin

change false to true

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c0e1e2ef-4f68-4040-b878-fe518224524d)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7f8a7946-513f-4077-8894-cef0d640b076)

delete and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/62d769cc-bae1-4245-bd36-aa62268e2628)

## [Lab 4: User role can be modified in user profile](https://portswigger.net/web-security/access-control/lab-user-role-can-be-modified-in-user-profile)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d84fc907-db1e-4b28-baf2-71cce05a4e4b)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8ec13a71-4b9d-4e5f-a386-ff1d005182c6)

dirsearch thì phát hiện có `/admin` bị cấm truy cập

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/05f76bcf-472f-4495-a5e4-822e61d1a9f4)

sau khi login `wiener:peter`, hiển nhiên khi truy cập `admin` thì sẽ bị đúng là bị cấm rồi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f155d017-6e19-410d-9a7f-33f7649b2eff)

sử dụng function `Update email`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f68afe86-7666-4fa3-9024-0c3adb8b39a0)

quan sát request và response ta phát hiện có trường `roleid`, thử thay đổi các giá trị để có thể trở thành administrator,

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/094a180e-a3ba-4589-8c3a-0f81299fc892)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ec58101d-8585-491a-9aa0-01c044a4c5d2)

send request change roleid to 2

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/19641331-19ba-4cc8-bb2c-db370fedbfb5)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1fc0de9e-d428-4ce0-9c5e-e51e419a8c2e)

vượt quyền thành công

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/482f4554-3674-40cd-a90f-11ed2a1f0364)

delete `carlos` and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/57e585b0-e52f-4f59-8247-3b618aaf2c19)


## [Lab 5: URL-based access control can be circumvented](https://portswigger.net/web-security/access-control/lab-url-based-access-control-can-be-circumvented)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/18eb6402-1c9b-4f38-9f71-905a30e59204)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7c75cb2f-2238-489c-9136-b825a50f9db1)

thấy `Admin panel` và truy cập thì `Access denied`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4b05e08f-7c14-4dba-b692-95473cff72db)

