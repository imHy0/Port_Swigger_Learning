## [Lab 1: Unprotected admin functionality](https://portswigger.net/web-security/access-control/lab-unprotected-admin-functionality)
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


## [Lab 7: User ID controlled by request parameter](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/43dc8fa0-030c-4ce4-ad35-469ac06ec957)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8e6314d9-af2f-4704-b3a3-e5ba926dda0f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/11283505-a01d-4a11-a90b-85027b807f90)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e878f06b-409a-4b26-8148-3bc4f3a626ff)

change id to `carlos` xem có thể xem thông tin của `carlos` không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/35ebafd3-41c2-4fa9-83e0-191cfe01fa79)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/42fc5d3a-664a-44fc-a5a4-0e78e8eb8e30)

lấy được API Key, submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c2175b77-cb9d-48e2-b58e-6db02cb26b8e)

## [Lab 8: User ID controlled by request parameter, with unpredictable user IDs ](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-unpredictable-user-ids)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bfcd0740-20ff-4237-8e3a-327dea9f2c30)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5c5c887c-00fe-4b5a-b57f-32e959592986)

login with `wiener:peter`, ta thấy id đã thay đổi không còn là username mà là một chuỗi khó đoán hơn

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2f0e8dd7-d514-4895-a55c-65e8ce85cfd8)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/67b54861-9ef8-4f16-ab7e-3801c635f5ad)

ta thấy có chức năng View post, ta thấy có bài viết của author `wiener`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/19db5cde-768a-46a9-8931-ff11c581f575)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cd3a00dd-9e94-416d-9af0-9d7dfe26c161)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3503e1d3-1393-477d-8ad8-f13734a3a36c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a9042861-649b-4d72-8e04-2b37bacc7f13)

ta thấy là chuỗi id ở userid giống với id tại my-account --> đây chính id của người dùng

tìm bài viết của author `carlos`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/26127e7b-aa98-4aa3-b9fc-6d0510f98793)

click vào `carlos`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/71f8f728-eda7-4e93-ab7a-8142567bdf81)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cf94f489-d53f-478f-a6fb-9b1072b4b464)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b54eb3d2-514f-49c8-a901-dc8e7f70e487)

lộ userid, change id ở my-account to this, 

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e13881a1-0aca-403e-a98b-ab1f3aac5854)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6dbe9dae-148b-4581-9cb7-aaee00265cc7)

submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4e44f997-d2d5-4fef-9759-6f8d8401a119)

## [Lab 9: User ID controlled by request parameter with data leakage in redirect](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-data-leakage-in-redirect)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a5402848-8488-46d1-84b8-0d7f1d0cbace)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a9f3b0cd-6edd-4c06-8a87-4bc9ac7c6e04)

login

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e4273f5c-a577-4aa0-b3e4-5de300b25886)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4fdb92f7-8676-4f1f-a05c-d96addbb13aa)

change to `carlos`, trang web sẽ ngay lập tức redirect sang trang `login`, tuy nhiên sử dụng Burp Suite xem Request truyền đi thì thấy trước khi redirect thì đã hiển thị thông tin của `carlos` rồi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e29b3010-9af0-4fab-a23e-f4580f44272f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8b43e313-8448-4e5f-b6dd-866174f677fe)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/375f67f9-6c1e-43e3-b731-dfd193fab65a)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cbaf0e6f-04a6-4d1e-8583-9a09e1afa221)

## [Lab 10: User ID controlled by request parameter with password disclosure](https://portswigger.net/web-security/access-control/lab-user-id-controlled-by-request-parameter-with-password-disclosure)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bcd21c6d-6a00-4d4f-a18e-6b24d4869983)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cd7340a0-f999-4068-a4cc-79e13aaae337)

`wiener:peter`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3273f338-13a3-4962-aafa-78698bd1bf55)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/aa90e623-a1ce-4741-80b1-95ae161fbb66)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a3e5cd7c-fc91-489e-a7d9-5c263d2689d2)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/46dccbda-a556-4fb3-9bef-8dcc41720920)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/082be0c9-7ed7-4e20-8e51-5e50ebbd0f35)

login thành công

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c401b545-a317-4702-9d9d-0d9132f8a6f3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a3ecd837-1a9c-4224-8421-bdecb3307f05)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b4964d1a-7cfb-40ee-8a74-b99eb7d734d6)

## [Lab 11: Insecure direct object references](https://portswigger.net/web-security/access-control/lab-insecure-direct-object-references)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5306e352-775a-4856-8df4-095b9fdcc38b)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ccc3aaef-14ea-4048-b432-2287744aa559)

test chức năng Live chat, thấy có View transcript

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/394cd38b-a311-49f0-b538-684c636776b6)

nó sẽ download cho ta 1 file

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/dfa39979-265a-4bb9-a5c3-08400af8c044)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4286bc98-10b5-45e6-a956-aa33aae8beb0)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/09c4e700-0eae-42db-a4b2-b58079b2c008)

ta nhận thấy filename được đánh số từ 2. Vậy file `1.txt` thì ??? xem thử thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c74614c5-61df-44f0-b5d8-6244e85a4c69)

lộ password rồi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7a3a983e-9a81-4e10-9ed9-02d9a028423d)

login and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/caed2139-530a-40a3-a1a2-4ca91b65b761)

## [Lab 12: Multi-step process with no access control on one step](https://portswigger.net/web-security/access-control/lab-multi-step-process-with-no-access-control-on-one-step)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d2cb80c9-128c-4890-8f2c-2d21722d2fdf)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3e8d484d-cfc0-4152-9ed2-214643d1d5ea)

login `administrator:admin`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6eafc26b-95d1-440c-8d00-c646acae9239)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/958d8a0e-6a0a-4364-9554-a22fbfe15cec)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a73ae9fe-0da3-4a7e-9727-2542a8f3e593)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a5bbcd12-2181-487d-a6ed-fdc10320a7ac)

nâng cấp thành công

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2941faf5-5b9c-4152-ba4c-2f3969ddad29)

logout, login `wiener:peter`, tự thăng cấp

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8cb03411-85e0-4dc9-9955-af1b570c66a3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/86062caa-58cb-494f-bc9d-e88b817e0fa7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ee4abfda-c2c2-4482-b8c9-d0e042504e97)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5d68e343-b665-4f0f-aa9d-9cf21d8f4845)

but not success bởi session đã thay đổi nên nó không thể xác nhận

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9f8f663c-1436-435f-a1f2-72400197aab7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d5a00beb-30eb-4888-a100-4eb0144b771b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/156ba5e1-85c5-457e-b566-0ab781bc5cb7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/850c76f6-5f23-46f9-957a-b85ee4a64b9f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f362ec01-5484-47db-a1a9-72c784c1c56a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0c261daa-ef58-4e9b-8373-17694802c18d)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6dd9bb18-6757-487e-925c-9b195c589b02)

## [Lab 13: Referer-based access control](https://portswigger.net/web-security/access-control/lab-referer-based-access-control)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9903de50-cc4e-4dd0-9df7-2f6e19f1a99d)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2ff64611-4cd9-4d77-af24-56fdc11c0b3c)

login `administrator:admin`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1c1250cf-a081-44e1-a5c4-0375a7e02590)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bc2ade7f-d05c-4030-9a00-7641bba36314)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a8c2591e-8b1a-4ded-8586-07d4d1ed37dc)

logout, login `wiener:peter`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/784e32f8-c290-4b94-8518-6e3f991c3030)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9b125533-b97b-4122-a742-b81183a93305)

cũng vẫn do session đã thay đổi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/660f95c7-36b0-4c42-ad06-0a51b63eecac)

change

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cb214546-1ad7-422f-afae-6b24be067f11)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c0c5f300-ee02-418f-be55-208d5acd533b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fc7dfeaf-1b8b-462e-808a-2846cc3e7d15)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/69233b5f-54ce-4eb4-9658-0fcc5efcbd00)
