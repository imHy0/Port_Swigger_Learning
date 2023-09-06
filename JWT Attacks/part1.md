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
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f3036df5-e398-4c7a-a09d-de0e4ad59ac8)

delete `carlos` account and solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ccc1e802-587f-4c83-a3c5-6148f43e77a7)

## [Lab 2: JWT authentication bypass via flawed signature verification](https://portswigger.net/web-security/jwt/lab-jwt-authentication-bypass-via-flawed-signature-verification)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/76abcc29-3293-4be3-8bf1-7079108cc10d)

login

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/742a700e-6d69-4050-9545-1fe6fcb3eb20)

session claim account wiener --> decode

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3c87e0df-c6c7-432e-aa25-6bf5f6531326)

giữ nó go to `/admin`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/95958ebb-b9aa-4418-b7a4-63bc9c9ccfc3)

hãy tìm cách là `administrator`

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/652d783f-0e14-4720-91ef-a143c5e0d8df)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ebab7967-96de-4c50-b02d-c2f582566f3b)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3d83b00c-5551-4a0e-ae6f-d742cd218346)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/132e6426-d910-4635-aa03-fc7ad9c5542e)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/763b0819-c2df-4d78-8309-3f723da84179)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/12c9d1da-4a16-43e0-b103-5cc363ac7cac)

## [Lab 3: JWT authentication bypass via weak signing key](https://portswigger.net/web-security/jwt/lab-jwt-authentication-bypass-via-weak-signing-key)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8803fc6d-e66a-4305-a5ed-15ac6ef1b9c1)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3370e639-2cc6-4de2-bd8a-a0f0a7f588b0)

decode

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/58e964ad-830c-4c0f-b091-2f2c8b1e97b3)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/928747ef-701b-4f62-8fcb-d98f1bf5dfc2)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/89cdcb73-e702-4f70-b1b5-56ba888cacd7)

[jwt.secrets.list](https://github.com/wallarm/jwt-secrets/blob/master/jwt.secrets.list)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/acd9b167-62b0-4811-9f23-414771b1a499)

key: secret1

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9c259b34-43b2-4d8e-97ac-b1c4a0f2d9ee)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3628fcb2-9c99-4f4c-b70a-f479e4d76a7f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7c79a7ff-021f-4bf7-be63-965426f43af9)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2df9eeb2-a29e-41f4-a7fb-be6029bd75f6)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2c0efe26-1bee-4c39-9a48-84113ef9f262)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/12cf8c32-558d-4cfd-9a11-ba88bb42db25)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6dc4bd54-5046-41bc-bffe-e9d727bff88c)

solve the lab

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0b0ed929-9373-4ade-a947-a3b6c765365a)
