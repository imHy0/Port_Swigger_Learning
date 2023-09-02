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

# [Lab 13: Visible error-based SQLi](https://portswigger.net/web-security/sql-injection/blind/lab-sql-injection-visible-error-based)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/de2fad77-943c-4357-a93d-b2eaa431bda8)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a70c7d8a-15f1-4a80-b2df-5a96b3a7dfb7)

xác định lỗi: Thêm `'`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c26f83f1-348b-4429-8201-63948af0705e)

báo lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/512ed91a-cc08-4d92-90de-e7bafee2e35a)

thêm `--`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4c11cfb1-f44a-4e75-bfde-c18eea6a135d)

hết lỗi

check tiếp `AND`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/88361b01-0ff0-4898-84c7-114409c47b3a)

báo lỗi phải là boolean

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cb5e8937-2b88-4e5d-8294-a4d5ae190a1c)

false

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3fa3e894-5a66-4646-898e-8107e270111f)

true

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d6d636e6-1800-4717-a01f-23a692adad80)

check tiếp

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/37c41bce-fc55-4ad4-933b-706fbafab42b)

báo lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fce55f0c-3d4d-493a-86db-a4c5942e7b0d)

lại check

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/219a9624-9b35-4440-9c26-08f000aa709b)

lại lỗi, chú ý query đã bị giới hạn ký tự

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9fd2c503-7ccb-42ad-bbe6-21e22eb31457)

check tiếp

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e86d99e8-82ad-4c62-a759-cca24552b86c)

lại lỗi, chỉ hiển thị kết quả 1 dòng

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ef0c144e-ab34-4e53-afc6-9977b5117bc6)

lại check

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/394a2fe0-1c4e-4d5f-879b-605e1a15a121)

trả về dữ liệu --> có tài khoản administrator

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d981290d-02a8-424b-8717-58a6371642cb)

tìm password thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d3574c55-e03f-44b2-be8e-dbce30c9ea88)

ok done

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/525e9f69-b8b2-418d-a8ce-2a9ca6e047ac)

login and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a609e932-faaa-4921-ae43-3ff27f1ff0ec)

# [Lab 14: Blind SQLi with time delays](https://portswigger.net/web-security/sql-injection/blind/lab-time-delays)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/805c414d-e28e-4c12-905b-c93b6c17d515)

check lỗi thêm `'`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3f902670-7b2e-4fc4-8d1d-a26d51c788d6)

vẫn duyệt web bình thường

thử đến time delays coi web có phản ứng gì không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/741ea2eb-9176-4f8e-8862-38448138b835)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f66089a6-e5fb-4dce-9fd0-3d29b3548671)

# [Lab 15: Blind SQLi with time delays and information retrieval](https://portswigger.net/web-security/sql-injection/blind/lab-time-delays-info-retrieval)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c3b538c1-0501-4892-ae4a-741454a4f998)

main web
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/524127f2-1823-477b-abcd-ab3dcf135b0a)

check sleep

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bb6728ee-dc91-40b9-b242-d3217b3751e7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/275d24cf-4ad6-4072-b71a-900e1559afb6)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/75300d8e-f5f6-4c6c-b447-62dcae4d737a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0a01063c-bc42-4028-a178-013e4a638432)

pass 20 ký tự

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/03ea50f1-bfa6-4c96-8a11-874097ce0b8e)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8197e03e-715f-424a-be0b-1d811af09029)

check tiếp các ký tự còn lại sẽ ra password

ngoài ra, ta có thể test ngay 2 position

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c7bd3ce8-2879-41f5-b895-d5199e547f80)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/acdd6614-01bb-42ab-a57d-51e1a9d0f63e)

→ pass h6gm0gaxrw9fg3jafejz

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c7c03ef0-0f0a-4f8f-bbd8-fd0eb28f47c4)

# [Lab 18: SQLi with filter bypass via XML encoding](https://portswigger.net/web-security/sql-injection/lab-sql-injection-with-filter-bypass-via-xml-encoding)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/146b140d-0e2c-476e-85ea-1db6f515d71a)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5d3c44c1-54ee-4c60-b60b-483de405a8cc)

lỗi SQLi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a78bae86-297b-498f-b735-dc09ed65d9d2)

1 đoạn XML

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/00c9f6eb-7a7a-43aa-a549-631ee9c62d99)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3de67da5-22c4-4b20-9fe3-7e3019c46487)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/99de5e4d-8401-46f0-aea6-79d524e2f173)

phát hiện tấn công SQLi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/84ed0586-51bf-40f9-b8ab-83ce1f9428fb)

encode nó xem

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5950a245-6857-4a0f-954e-284da14689af)

lại duyệt bình thường

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2c38b4da-150b-40ef-aaf3-5a8767a80dfe)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/aa295eef-20ab-47f4-b298-98a0fdaa8283)

--> có 1 cột

lại phát hiện tấn công SQLi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a026c68a-9d5d-4938-baf2-7cf8b1a452d6)

→ tiếp tục tìm cách encode

Cách 1: Encode bằng

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1f405af1-6f98-4ee5-ac7e-5c5e1f48df85)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e431fdf2-779a-4e5d-b4b0-8372f2d3a3ec)

Cách 2: Sử dụng Hackvertor dùng encode: dec_entities

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/257114c7-fa6e-4511-bced-11dd39e57021)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/03d7e4ac-fff7-4b26-a201-007869694df0)

login and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c00531c9-bdc3-42f8-9146-6c9d654ca453)
