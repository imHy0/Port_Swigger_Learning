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
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ea57f6cd-b04d-47fd-83bb-13631f25b565)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2109e718-05f8-4a31-94f9-92c217d348e8)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/579e0bac-5846-479b-9dde-250c2ddc5515)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/511dacf8-8038-4966-b58d-5bccd5ec09f9)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d340835c-f930-4c08-b18c-07e6d63017a8)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/675c8edf-4984-4d1f-8613-ab82f92ec371)

# [Lab 6: Remote code execution via polyglot web shell upload](https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-polyglot-web-shell-upload)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/60e9b802-1fd3-41f6-a821-a0f6f26cd8ef)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ee320df2-1263-44e6-b504-537c66cc33bd)

`Error: file is not a valid image Sorry, there was an error uploading your file.`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/16db9388-933c-4ef3-a8b0-fd86648d57a3)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a17f040e-0621-42f9-86ba-138c63dfe613)
Nếu không sử dụng công cụ mà tự sửa ảnh
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c1cd834e-6e17-4502-8d96-48681675959c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/84191b4d-6e6b-4cff-ac1c-5fb8384dd6fe)
vẫn ok, tuy nhiên có những trường hợp sẽ khiến file lỗi và không thể thực thi, nên sử dụng công cụ để đảm bảo chính xác
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6b10ec9e-c136-420e-96d0-ca41093b9015)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fbd51740-d168-4456-9f96-26cfa3f79b32)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8b00cd40-e8d8-4eaa-bca2-b29825b9c2b4)
submit and solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a6059f72-a8c5-427e-a10b-231e162ff8a2)
