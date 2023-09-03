## [Lab 1: OS command injection, simple case](https://portswigger.net/web-security/os-command-injection/lab-simple)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/08c6d2fe-54b0-4c60-aeb5-3d79644a4e7c)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/346c04c3-abc7-4ece-b053-64fdbba4448e)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/78fecd84-4a22-4541-a48d-f8cdbcbe9ee0)

test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3abe2226-de7c-442f-adac-0608a6b12d4f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/917ab0c9-e582-41ed-8fc5-38f25f89e16c)

ngoài ra có thể F12 rồi sửa giá trị và `Check stock`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2ce4f9c0-7187-4d91-a6cc-4125e68aae73)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/676e0cbc-e6ca-497d-9f31-38127bce32d0)

## [Lab 2: Blind OS command injection with time delays](https://portswigger.net/web-security/os-command-injection/lab-blind-time-delays)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/088059fe-3e06-4399-ae37-7d5ce2362e25)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1f53b162-885f-4033-a18a-3351e69ef399)

function chứa lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/16e3fc17-cded-49df-a419-79da447b550f)

test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b63c5743-0b95-48eb-ac32-9ef55fd9d676)

submit thành công, tuy nhiên kết quả trả về ta chưa thấy command có được thực hiện thành công hay không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/dc455d65-022e-46e3-834a-414a423b72cb)

kích hoạt time delays

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6747f1c5-3b11-44bf-a94a-dc9df5fc3940)

ok, solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/411b585a-4746-46c1-ac5c-7d98d9af3cff)

## [Lab 3: Blind OS command injection with output redirection](https://portswigger.net/web-security/os-command-injection/lab-blind-output-redirection)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/66148b29-62b5-422b-8823-3535be4a2d22)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/198c3dc7-fd50-463d-9e5c-0ce532d280cd)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ae49863e-434d-41bc-9b3d-fbd7af1beac6)

test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/006aeea6-a94e-41cd-b716-28131ff547f1)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b7475f6f-cd36-44de-b71e-5454a82f58c9)

kích hoạt thời gian trễ

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e49c4238-c4ab-430e-a9ce-c3f5c0c6ba02)

phản hổi trễ OS command injection

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/011b39f3-c3fc-4415-9b06-ee5082ff2da3)

chú ý trang web có những file ảnh, ta sẽ chuyển hướng ouput của command `whoami` vào file trong path chứa các image là `var/www/images/`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e3518c75-72bb-40a9-ae60-37abe705c071)

xem file

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3f86cf77-7f15-4bb6-a351-f5c745fd6cf7)

get 

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4f4f4427-ca8e-4a50-90bc-f9a55d6452bb)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3b9bf122-19e5-4d8f-9118-430b4dbf1277)

## [Lab 4: Blind OS command injection with out-of-band interaction](https://portswigger.net/web-security/os-command-injection/lab-blind-out-of-band)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c13f03d4-c961-46d6-9547-885b3da65713)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6adc7d06-b2cd-4f5e-a68a-00dccc0bed1d)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/14671f0e-ed7f-49ba-9f42-840c909c3f8e)

test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/510a58e1-2c68-4992-be30-9b73acc561f0)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ac239dc5-9179-49aa-b9be-4905e62f9f22)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9019f895-f6d9-405a-9334-69f958a5e2a5)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9fd3a1c0-4aed-465d-9a3b-8958c396cf75)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b0bd03ed-8887-4683-b88d-c8cd7d8ca15e)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b0012aed-e0d5-47a8-b4aa-8d46d55b9732)

## [Lab 5: Blind OS command injection with out-of-band data exfiltration]()
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8d1bc5fd-56aa-4274-a30a-2d8801944d47)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5ce8e9b8-5269-486d-9b68-9f6e554f3508)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4748a52d-f162-4b39-b3fd-2b80c6f7df27)

test

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ffde0678-885b-4f68-a579-1cc6e3a9e3ec)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c8ec37b5-2ab8-4f08-9aaa-b056c887c76d)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cafd7887-1f92-44c9-8c4b-cf4e295a1c91)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c8b1a82d-fc24-4ec8-b444-386ffa4c09ee)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4cf94373-2935-4f42-abb2-46c91a5d9fd4)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1b647989-eacb-4e91-b341-8c975e9b0509)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/adf1dcfd-e454-4513-a76a-b79bfea441fa)

submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/de0efe52-0b85-4b7b-98d3-42f73fdfe045)
