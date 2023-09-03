## [Lab 1: Exploiting XXE using external entities to retrieve files](https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-retrieve-files)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fd6417ad-d86e-48dc-8647-b6b1679a1cff)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/58676ee6-0254-4002-b100-e638960ef6b6)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/07336adc-1d60-4743-b48f-a60456436a93)

request gửi XML yêu cầu kiểm tra stock

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/11ccd9d6-7ee7-4216-8497-14ca0f6b778a)

test

- `<!DOCTYPE foo [ <!ENTITY xxe SYSTEM "file:///etc/passwd"> ]>`
- `&xxe;`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7198de69-c543-4cb2-b488-36ef7d099d33)

response

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e4fa4b7a-7c5e-48fc-8184-c545d312d3e9)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0df514d4-93a3-4d1f-a46f-cd3ff251e882)

## [Lab 2: Exploiting XXE to perform SSRF attacks](https://portswigger.net/web-security/xxe/lab-exploiting-xxe-to-perform-ssrf)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/82f0e7fd-2b03-488a-ae0a-958158d4f333)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0e2fa881-54f8-4a55-a08d-a99d6f3982aa)

function lỗi

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/218fa4c4-7442-4234-ac61-290ed59ad935)

request gửi XML yêu cầu kiểm tra stock

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1d81e1a3-66d9-41cf-8458-929b50280c52)

test
- URL mục tiêu: `http://169.254.169.254/`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9cd90b14-078b-49a2-81f9-f8ba36fee5b7)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2a35f7c5-ffe5-459e-80c7-6079e94d2564)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/735a4c22-3860-4659-9e92-aec1f41dc07c)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b7eca82f-04b5-4398-83c5-89e8e44e2f66)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b77966a1-3825-4c2f-9c80-626423b83f66)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/914787b3-e3b5-4931-b5ff-e86ccbae115e)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/815c6ff8-efbe-4d06-9bfd-09105cf394e9)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b2945f70-0e56-4fdd-ae29-e2425066eaf3)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7d0584f9-8f0a-47f2-b4bf-57035c0950bf)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4d157715-d596-4f5b-ae63-cab057c3c593)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/aa622bed-9b7d-4d8f-8902-978da66868d0)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0c040b4d-9cc5-497a-a495-8e28f01bc1db)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b12d8770-e71a-448d-b662-16c61b0deb47)
