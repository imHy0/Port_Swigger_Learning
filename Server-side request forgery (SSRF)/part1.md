## [Lab 1: Basic SSRF against the local server](https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-localhost)
![Alt text](./image/2.png)

đây là main web của chúng ta

![Alt text](./image/3.png)

đầu tiên test chức năng `View details`, ta sẽ thấy có chức năng mới là `Check stock`

![Alt text](./image/4.png)

quan sát request coi sao

![Alt text](./image/5.png)

ta thấy nó sẽ  gọi đến 1 URL mới để lấy thông tin sản phẩm -> có URL ta nghĩ ngay đến lỗi SSRF

giờ ta sẽ gọi đến `/admin`

![Alt text](./image/6.png)

kết quả là thành công luôn

![Alt text](./image/7.png)

xem đường dẫn đến delete account

![Alt text](./image/8.png)

giờ thì delete `carlos` và solve lab

![Alt text](./image/9.png)

![Alt text](./image/10.png)

thử test bằng tool: chưa biết test

## [Lab 2: Basic SSRF against another back-end system](https://portswigger.net/web-security/ssrf/lab-basic-ssrf-against-backend-system)
![Alt text](./image/11.png)

vẫn lỗi như **lab 1** nhưng URL có chút khác, và yêu cầu của bài chỉ cần quét trong `192.168.0.X` với port `8080`

![Alt text](./image/12.png)

ta sẽ test 1 địa chỉ IP bất kỳ để xem response trả về như thế nào

![Alt text](./image/13.png)

-> lỗi 500 Error

![Alt text](./image/14.png)

giờ ta sẽ test xem URL nào là hợp lệ bằng cách sử dụng Intruder cho nhanh

1. Payload: `Number` `1 - 256`
2. có thể Grep Match với `carlos` hoặc chú ý `Status code`

result tìm được địa chỉ IP thỏa mãn là `192.168.0.122`

![Alt text](./image/15.png)

![Alt text](./image/16.png)

chú ý đường dẫn đến để delete `carlos`

![Alt text](./image/17.png)

delete and solve

![Alt text](./image/18.png)

![Alt text](./image/19.png)

## [Lab 3: SSRF with blacklist-based input filter](https://portswigger.net/web-security/ssrf/lab-ssrf-with-blacklist-filter)
![Alt text](./image/20.png)

vẫn lỗi như **lab 1, 2**
![Alt text](./image/21.png)

khi test các URL `127.0.0.1` hoặc `localhost` thì đều sẽ gặp lỗi 400 vì đã bị block

![Alt text](./image/22.png)

bypass bằng 1 số cách như `127.1` thì vẫn bị lỗi 400 như trên, obfuscate ký tự `a` bằng doubleUrl encode, `%61` là `a`, `%25` là `%`

![Alt text](./image/23.png)

![Alt text](./image/24.png)

![Alt text](./image/25.png)

![Alt text](./image/26.png)

![Alt text](./image/27.png)

## [Lab 5: SSRF with filter bypass via open redirection vulnerability](https://portswigger.net/web-security/ssrf/lab-ssrf-filter-bypass-via-open-redirection)
![Alt text](./image/28.png)

khác những lab trên, lab này có thêm chức năng `Next product` sẽ redirect sang trang khác được đề cập trong `path`

![Alt text](./image/29.png)

quan sát request thấy có `path` và status code khi send request là `302` là redirect

![Alt text](./image/30.png)

![Alt text](./image/31.png)

đổi thành URL coi sao nhé

![Alt text](./image/32.png)

follow redirection, đã chuyển ta đến sang host google thành công

![Alt text](./image/33.png)

--> ta sẽ dùng nó để redirect tới địa chỉ mà chúng ta cần đó là `http://192.168.0.12:8080/admin`

vẫn như các lab trên thì vẫn sẽ là lỗi ở `checkStock`, tuy nhiên ở đây lại dùng `path` thay vì URL như các lab trên

![Alt text](./image/34.png)

thay nó thành URL xem có gì xảy ra không, lỗi `400` và `Invalid URL`

![Alt text](./image/35.png)

giờ ta sẽ thay nó thành endpoint chứa `path` ở phần `Next product` trên

![Alt text](./image/36.png)

and the response trả về đúng sản phẩm có `id=2` và ta phát hiện còn có thêm `Admin panel`

![Alt text](./image/37.png)

change path thành địa chỉ đề cung cấp để thực hiện yêu cầu

![Alt text](./image/38.png)

![Alt text](./image/39.png)

![Alt text](./image/40.png)

delete and solve the lab

![Alt text](./image/41.png)

![Alt text](./image/42.png)

## [Lab 6: Blind SSRF with out-of-band detection](https://portswigger.net/web-security/ssrf/blind/lab-out-of-band-detection)
![Alt text](./image/43.png)

mục đích của lab này đơn giản chỉ là tạo yêu cầu request HTTP tới máy chủ Burp Collaborator

![Alt text](./image/44.png)

Poll now để xem thành công chưa

![Alt text](./image/45.png)

solve the lab

![Alt text](./image/46.png)