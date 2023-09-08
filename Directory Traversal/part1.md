
## [Lab 1: File path traversal, simple case](https://portswigger.net/web-security/file-path-traversal/lab-simple)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8efb7b07-a85b-4e73-b8f1-495cdd90cae4)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d1e1880e-3aa6-47fe-9123-2294f61abe4a)

hãy bật Images để xem các path đến image nữa vì trang có rất nhiều image và sẽ có directory lưu trữ nó
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/07f05aa5-6e0c-4cec-96b3-85c405f49334)

Request xem ảnh bất kỳ, đã thấy có `filename`
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/36b6e6cd-4452-4c09-a180-c2495b79d3f3)

test thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e81d9966-6d63-4030-912c-f9ae7cc8fdd4)

response trả về `No such file` --> directory hiện không có thư mục --> lùi thư mục đến chỗ đọc được thì thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c806a993-80c4-4fc5-9192-88879fdd4121)

đã tìm ra

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3d26255b-e217-435c-8df7-d65e1089b38f)

xem trên web lỗi không thể hiển thị nên ta sẽ xem bằng Response trên burp suite

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f0706588-b314-442f-a7af-ff2847600869)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fc9efc44-ad1a-4cd1-86ce-d97fe5647b23)

ok solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/556de88b-6b55-4d1d-b536-f410dd6c52c4)

## [Lab 2: File path traversal, traversal sequences blocked with absolute path bypass](https://portswigger.net/web-security/file-path-traversal/lab-absolute-path-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2565685a-756e-4186-9726-378027fbd4a8)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/aa10bd6d-594d-4acb-9204-28567c7c62be)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b5fa3c69-82a8-4910-8e7a-7a0786dba568)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4b377033-4681-4fb7-87f7-0f8e5e478040)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e993f1d6-786e-4adb-b145-ccf0dbd831b6)

## [Lab 3: File path traversal, traversal sequences stripped non-recursively](https://portswigger.net/web-security/file-path-traversal/lab-sequences-stripped-non-recursively)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d57b2cfb-0e8c-4e47-86d4-f036fee0a567)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/747772ed-4210-4eaf-b570-566930e7a3dc)

filename

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/03ff4087-5d15-43b7-9a46-a4d59ba93b8c)

test, lùi bao nhiêu cũng vẫn thấy `No such file`, có thể ../ đã bị replace hoặc gì đó

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/62e38af4-feea-4d38-b907-cbf711ec64aa)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/55c33abb-082c-4251-af3a-e45e08fc5806)

thử test bị replace thành `''`, ta sẽ đổi thành `....//` để khi mất 1 `../` ta vẫn còn 1 `../`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b16efae3-4cd1-453f-a4fb-9e10da18ecfe)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c509d26d-c666-4bdd-8b0d-1201e5039a3b)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/64ff5437-a51f-433f-88f8-3c34ca1f178f)

## [Lab 4: File path traversal, traversal sequences stripped with superfluous URL-decode](https://portswigger.net/web-security/file-path-traversal/lab-superfluous-url-decode)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3b2e9e85-fb58-4b0c-8776-126bb3daa6ee)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4cad3bc3-dc59-4150-838e-c2593c0768a1)

filename

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/42f0862a-2fde-412f-bd0f-46236ee5a860)

tương tự như lab 3

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/655475a0-dd11-4401-9605-8e1382ba683f)

test hoài vẫn no such file

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3b3df537-b5f6-48d9-974f-efb4e801a87e)

nên ngoài bị replace, ta có thể bypass bằng encode `../`, tuy nhiên encode 1 lần vẫn chưa pass, thử 2 lần encode

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ed55a9df-3ce1-4a6a-9364-20b7ba8330b8)

ok solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/680bff0b-504c-4dbf-9243-f6adfd4d524e)

## [Lab 5: File path traversal, validation of start of path](https://portswigger.net/web-security/file-path-traversal/lab-validate-start-of-path)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/662cb40e-550d-429f-a74e-af900bf3ffba)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4b03c0cd-4be9-4131-87ab-95761ff6d626)

filename

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d9f2be17-66ad-4a4c-9021-c9f49335643b)

vẫn là lùi thôi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e69d8934-0109-4118-b029-b435c8b7f651)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/37e906d9-f1a9-42f4-8520-996fde731020)

## [Lab 6: File path traversal, validation of file extension with null byte bypass](https://portswigger.net/web-security/file-path-traversal/lab-validate-file-extension-null-byte-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/20139689-1313-4ec0-87e4-61a4d00710ad)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/16c73bad-319e-4442-aa94-c88b36aa6a93)

filename

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a19243b9-a603-4a5d-aa00-ee6eeeeaa9c7)

test hoài không ra, có thể web đã tự động chèn thêm extension file ảnh `.png` nên ta sẽ dùng `NULL BYTE` để bỏ nó đi và đương nhiên là vẫn phải lùi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0c9bfabc-ec25-4a07-a782-6729db83a91e)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4be4f8ce-7a51-4025-b618-6e397f2ac2fd)
