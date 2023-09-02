# [Lab 1: Information disclosure in error messages](https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-in-error-messages)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b0935473-a3c8-4fc1-bee7-b3863e222149)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/be00f846-edf6-483a-98ae-18440577477b)

view details 1 sản phẩm bất kỳ, id là 1 số

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/782b827a-19be-4095-9b1a-eacc87ca136e)

sửa thành 1 chữ coi sao

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/66d91c59-65b7-4213-80b4-6b2c7868fdac)

lỗi chắc luôn

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/38e90bb1-92f6-4c70-9525-4db572b2e290)

submit version number and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e43a240d-ce29-48c6-b147-4fa701582ae8)

# [Lab 2: Information disclosure on debug page](https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-on-debug-page)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/99a10c31-9972-4fe3-8e0c-1335b899e194)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/97eeceef-0f4d-4173-974f-3302771e9529)

quan sát code của trang web ta thấy dòng code đã bị comment dẫn tới Debug page `<!-- <a href=/cgi-bin/phpinfo.php>Debug</a> -->`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a7ffe614-ff2b-40a8-a7e5-fadc9c7f2d4a)

ngoài ra ta có thể sử dụng `dirsearch` xem có thư mục nào mà ta có thể truy cập không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/358b076d-46b5-488d-8fa1-5cebef57c3c7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4814b9dd-1a71-44d8-a148-e8e30aa818ab)

go to that endpoint

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ab588e40-8b20-4de9-8200-7e8d1e949b23)

find `SECRET_KEY`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/09c50d25-4c5b-4185-8edc-c90415c1166b)

submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c2c492ff-83a3-4856-9202-05bcc1659df4)

# [Lab 3: Source code disclosure via backup files](https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-via-backup-files)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5a590bb1-4d2b-4698-9a89-f876aaa33073)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c3195337-3628-478a-9ccc-4f7f3641b335)

sử dụng `dirsearch` để tìm xem có thư mục nào mà ta có thể truy cập không

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6dd276c2-c515-4137-9c64-6639c76cec04)

go to that site

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bb1f30fc-14d9-4bb7-9d61-cefbd8d908fb)


![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/35ad07c9-9ac0-4963-ac63-1259b443ae26)

submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/495d2dc5-6139-4117-a711-a892f3d4f889)

# [Lab 4: Authentication bypass via information disclosure](https://portswigger.net/web-security/information-disclosure/exploiting/lab-infoleak-authentication-bypass)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c3315744-0136-41e3-aa54-0124ec452c8d)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/14ad9bf0-6662-43cc-bb0e-2f965b40e95c)

dirsearch ta thấy /admin đã bị cấm truy cập

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cc6b331b-0e10-484d-b173-996ac8731dd9)

access admin interface

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f64fb8f6-c2e4-4269-812a-bea2a07e8065)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0cd451b1-0f94-4254-99d1-c24a7d6c708b)

ta thấy có header author IP

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/cb841aa2-ccaf-4851-8265-709f4ef50f2b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/86617b60-a369-432f-ac36-cb4594d50065)

đều IP riêng

giờ ta sẽ đổi thành `127.0.0.1` để gửi request

Cách 1: Proxy → Options : cách này giúp ta load lại web với header như hình

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b80c0d63-8456-43b1-a33c-930ba03d7e0c)

Trở lại trình duyệt, ta đã thấy xuất hiện admin panel

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/38c75ee5-91b8-4ae5-840b-cce8f2e7aec7)

Truy cập và solve

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/35e9b64e-9189-4f52-8ad7-830a60d4bf89)

Cách 2: 

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b31f1d3f-17b4-4723-bc71-47515075b7ad)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/24116ec0-782a-4296-bf72-d0a6a0ed389d)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/dad047f4-6c55-43cd-b52c-cdeccb10c958)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7acb5e43-b3d8-46f5-8429-864fc2aa0978)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ce79d030-214a-4db3-89f7-ce42876592df)

# []()
