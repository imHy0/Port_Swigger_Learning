## [Lab 10: Brute-forcing a stay-logged-in cookie](https://portswigger.net/web-security/authentication/other-mechanisms/lab-brute-forcing-a-stay-logged-in-cookie)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/233403f7-712a-4fb1-9839-f0cb9921297d)

login `wiener:peter`, chú ý có `stay logged in`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3d57f420-3dfa-4450-8295-e3beb3979ede)

sau khi login sẽ redirect sang `/my-account?id=wiener`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3f46a75d-be4e-4171-925c-867968d77904)

chú ý có value `stay-logged-in`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c5783423-de19-4f03-9ab4-fad4ca6c6e88)

decode ta sẽ nhận được chuỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/67412a82-ea6c-4075-be42-fe05a11e0a98)

dự đoán nó sẽ là `username:hashed_password`

decode tiếp, sử dụng `[CrackStation](https://crackstation.net/)`

vậy là đã đoán đúng rồi, và lưu ý là hàm băm được sử dụng là hàm băm MD5

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a4e44ec0-74ba-4180-86bc-bc934aaafb9e)

giờ ta sẽ brute-force cho account `carlos` dựa vào quy tắc trên

1. hashed password: sử dụng hàm băm MD5
2. thêm prefix: `username:`
3. base64-url encode

NOTE: trước khi brute-force cứ logout cho chắc nhé.

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6113aa29-9919-481f-bb34-d283c60cd6e4)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/94931d14-f074-4c71-b234-8cf88b52470d)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9597b7cd-1adf-4881-b58c-b412441d3151)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/384bec80-0afe-41cc-b655-5bcf687b162c)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/313eec1b-fdd0-4b4c-a9b7-2ca9e7c9d76b)

## [Lab 11: Offline password cracking](https://portswigger.net/web-security/authentication/other-mechanisms/lab-offline-password-cracking)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/20b31a88-9ca5-4f96-a976-26c23b6d5f3b)

khi test các chức năng của web, ta phát hiện website đã bị lỗi XSS ở `Comment`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3ba0ac5c-cc3d-4d9b-9ed0-b0ae6172ebe7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0b35d85c-a38b-4dfd-b4d1-3976f38f01f8)

back to blog ta sẽ thấy hộp thoại cảnh báo xuất hiện

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/eabe445c-a3cc-4dbf-99b4-31903b36d221)

vẫn như bài trên, nhưng không thể brute-force được vì không đoán được list password, nghĩ cách khác thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3e12d9bc-769b-4a31-a2c6-c3d0ab9636f8)

khi delete thì cũng phải yêu cầu password nên phải tìm thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e5cbb1b4-2c04-4718-b4eb-59f5fe2b0d8a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/353faf9d-9c59-44c0-aa3b-10b90f7b97c2)

chú ý 

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/725a262c-4276-45fd-95bc-0eeb9e71707d)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/86ac7a08-c1fa-45d0-9336-b4a1bec3fb25)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d2ebaa6f-8873-4385-8625-461d30e5acb7)

ta chú ý rằng mã này nằm ở cookie, ta có thể tìm cách để trộm cookie vì  bài này bị lỗi XSS ở function `Commment`

giờ đi trộm cookie thôi bởi js có `document.cookie`, gửi nó về exploit server của chúng ta để quan sát access log

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5ec059fd-0047-454c-904d-7f822e1c277f)

get it and decode

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/838872a3-cd99-4640-9888-deba0631b24b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/57f1c4e6-79fd-4159-9e5c-0006e623cb0a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/991b4bd2-58c7-4a88-a90a-95195e1c8dc8)

login thành công

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/599e4c7d-bc20-436d-b133-6d9cda992b29)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3c2f084f-84f8-4ae1-b91a-bd1c98f54f3b)

sovle the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/692d3cd7-546f-4b18-9263-877a2ad23919)

## [Lab 12: Password reset broken logic](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-broken-logic)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b473dc8f-2ece-4575-8618-05cff2d565ad)

login `wiener:peter`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/04171050-f1db-43c4-a911-b5f4295c690e)

function `Forgot password`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5505e73f-b346-429d-bf49-9b6cb5f5a7aa)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e5b459e7-4cb7-4ecd-80b3-767821756aa1)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bb5c859b-65d5-4fa6-94de-98590f1c5db2)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ae20b96d-5c1b-466b-9429-d66c46480462)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fe0262c0-e077-4197-9564-e6d60304bb87)

cũng không yêu cầu nhập password cũ, rất dễ để thay đổi password mà không cần biết password cũ là gì

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/efc059a1-4a1b-482a-9437-0ef5e3a4e9a4)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9817c849-64fd-4237-b34e-c345099ded81)

có thể nó sẽ không kiểm soát token, nên ta thử change `wiener` thành `carlos` trên request change password coi được không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/879dbafc-747a-4016-9948-4559a2437ac1)

login thử xem đúng không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/580a135d-b281-4dbf-97b6-75d2a57041d3)

đã change password thành công, solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f559ab23-b479-43d8-960e-403c5effaf73)

## [Lab 13: Password reset poisoning via middleware](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-reset-poisoning-via-middleware)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e53f7bbe-0bdb-4086-9ed3-a9ad1a760235)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8e81a97d-67e2-4911-827f-f53071022792)

có tài khoản thật

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/81930ae5-d828-43c1-afbd-32e581043c00)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e1037e1a-e589-45ca-9728-f5a4b56f5882)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1c0e5698-acc5-4648-96f7-94b8f1e1cc04)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/927c8101-bb4f-422c-b2a0-01dfc87b0581)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3037c33f-00ec-4e19-8eb9-a99c06433371)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d248a612-2354-4ea8-9861-3ddb1ff17266)

change password mà không cần nhập password cũ

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7f917977-d1ec-4f86-bcb5-3f5c6b728fc5)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7e0410b3-55e8-40b6-a71d-ee42f721d1ae)

bài này change password request không yêu cầu username rồi, vậy là token của nó có thể đã xác nhận username rồi

còn cách khác, ta sẽ chuyển request đến host của chúng ta và quan sát trong accesslog, xem có token nào được gửi đến không

trước tiên send Request Forgot password đã, và đương nhiên send đến Host của chúng ta rồi sử dụng header `X-Forward-Host`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c4aaa723-b688-493e-99e8-1249ff70626a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ea82a336-45ef-48eb-8bd7-7c03c183816a)

dổi token ở request cũ rồi change password thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e5de9c7a-fa9e-4e06-9605-42094231b6fb)

login and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f9d7e7aa-9409-4130-8017-9ba6b78e2f3a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c039d8ed-7868-4563-b20c-5f86eff29516)

## [Lab 14: Password brute-force via password change](https://portswigger.net/web-security/authentication/other-mechanisms/lab-password-brute-force-via-password-change)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e961ba0a-a74d-49c0-a621-cb5585807d10)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2651326e-999b-49f5-9f0a-f1d115340d80)

`change password` function, test thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/756165be-b108-45f2-9bce-9e8fc745965e)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3aab25c4-fab9-445e-b2d1-d93cb1e8e1b6)

change success

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c0eb7501-4a66-40c3-a994-8901f26da50d)

thử nhập sai password now

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6155c512-6e8a-4a90-b28a-62b54d51af89)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7a6a3006-4ee8-46bf-9eb9-aee2ce402d38)

login tiếp sẽ bắt gặp

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/58734bcf-686e-4fa8-ad7b-41cd5d999db3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/146e7113-43b8-4761-839c-104543067fb4)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/be82238a-3ee1-458d-9b95-5cf98b8a0d36)

test tiếp

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b356b125-fe42-4d95-85c4-b8990d5d72b7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f0c4994e-50ac-4e6d-b7ab-c13b6ca84133)

sẽ sử dụng nó để brute-force password cho `carlos`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0434fe40-42db-4c08-9e39-c49141ad215a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ce882b48-85f5-4768-a9fc-6cb7829a53ed)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/87997408-509f-4e6b-8f37-2d53361ad911)

login and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4c84d6a6-531f-4cad-9f72-6acd336a1253)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/032f6678-3393-4af4-8a81-a2df19ade38f)
