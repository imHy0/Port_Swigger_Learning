## [Lab 1: JWT authentication bypass via unverified signature](https://portswigger.net/web-security/jwt/lab-jwt-authentication-bypass-via-unverified-signature)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/beb325a2-e879-45c3-8342-887ed154563d)

main web

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/92d4c06e-1dcd-47ee-ba10-290eb7450a0b)

login with account `wiener:peter`, see request, see JWT 

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2e27ff60-c72b-40c4-9a8c-7ecdc0c53a6b)

decode that use `https://irrte.ch/jwt-js-decode/index.html`, see sub: `wiener`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9430da51-15a9-4b21-88a3-6ead2aa856ea)

go to `/admin`,

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d4f37e5f-7d70-4d00-80b3-ce447f4114d8)

see request, session claim user wienter

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b730711d-df94-4926-ade9-6dd5d417650d)

change this to `administrator` and send request

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/018789d9-895c-4b93-884d-c80edf1ba361)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/860590a8-5903-409d-a149-666fb2de38a5)

ok

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ab5a5d33-de19-4e31-ac36-942c32dc365f)

delete `carlos` account and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ccc1e802-587f-4c83-a3c5-6148f43e77a7)
