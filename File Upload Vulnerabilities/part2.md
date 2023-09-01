# [Lab 2: Web shell upload via Content-Type restriction bypass](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-content-type-restriction-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e6f79527-a963-46ad-8fa8-503bde488f05)

vẫn là đăng nhập và thử update 1 file webshell
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/62d89ca6-54cd-46da-b5f3-1061f76c3374)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ec72e803-00b6-45d0-94e7-7d416f9730b3)

tuy nhiên chú ý đến thông báo nhận được ta dễ dàng thấy rằng type application/octet-stream đã thấy ở trong Content-Type đã bị chặn và chỉ cho phép type là image/jpeg
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ee866f1b-bd97-4617-b03e-c3eebe1a36c2)

vẫn request đó ta sẽ sửa Content-Type về image/jpeg và thấy đã upload thành công
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7cf5cde2-a4bb-4616-ba6c-609b48b33dc3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0ee0bfeb-ce37-4236-8f2c-13f7fe233238)

lấy content nhận được submit và solve thôi
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/54a5e8f0-2006-4db3-a739-e799313d8d91)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1e48fea7-829c-436d-973c-0d7a7cb50792)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4addb8e5-1ab3-4aed-96d2-c566fd80890f)

# [Lab 3: Web shell upload via path traversal](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-path-traversal)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/188a3667-5a78-4a12-81d8-c7fc66167cce)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c69dda52-9901-4e95-8f90-171f6ce32dae)

Chú ý response trả về `The file avatars/port.php has been uploaded.`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bc847313-9b43-4ea8-ac43-3bedf6b4570a)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/05608e83-752a-4f1a-95f7-3014ce9dc882)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/beeaa0b9-75e1-43d9-a864-c74e7dfa876c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c93bfb32-3a56-47e0-a152-67710b47b68b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5366559c-7d44-44e2-99e6-0d7160bbbc95)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f30c2256-d62e-4e6f-a663-0046c1bc79a8)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/32790161-a756-41d1-8168-b3324511c968)

# [Lab 4: Web shell upload via extension blacklist bypass](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-extension-blacklist-bypass)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/da706ae5-d35e-42ac-a200-09fe42587995)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c702bf01-e8ed-460e-80db-4c727838eca5)
`Sorry, php files are not allowed Sorry, there was an error uploading your file.`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7966a56c-f0fe-441a-90a1-f533c3882fb4)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7e9dee2b-5198-4f62-a27f-3ab7cc7b8b2a)
`.htaccess` `AddType application/x-httpd-php .gicungduoc`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ea270e4a-06eb-4122-8646-4154ac123245)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/423ab3cc-8414-412b-ac50-ec4d59b4e510)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/654397ef-4a34-4c76-98b4-db8c70bd7483)

# [Lab 5: Web shell upload via obfuscated file extension](https://portswigger.net/web-security/file-upload/lab-file-upload-web-shell-upload-via-obfuscated-file-extension)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a888e833-0f61-4294-b7dc-b7de6ce6db3e)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5e459e5d-0fcb-40ac-ad07-2dfacc9ab726)
`Sorry, only JPG & PNG files are allowed Sorry, there was an error uploading your file.`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/be47777d-299a-4483-8223-590f7ed8984d)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cc8c8252-3442-4e95-a935-b679d579cd6c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/92ee7454-033e-45df-ba0a-444d1163ef33)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/db743e05-6d63-46f5-b5f0-ec4b1cdc7509)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/675c8edf-4984-4d1f-8613-ab82f92ec371)
