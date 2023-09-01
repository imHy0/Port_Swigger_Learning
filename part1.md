# [Lab 1: Username enumeration via different responses](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-different-responses)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/8c33421e-d7f1-4620-8c3a-682c1c5f54fc)

Đây là trang web chính của bài lab, ta có thể dễ dàng thấy các chức năng:
●	Home: trở về blog
●	My account: thông tin tài khoản
●	View post: xem thông tin bài viết
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/06fda70c-1a60-4c8f-9ae3-ec7a29f961da)

Đến `My account`, khi ta chưa đăng nhập, sẽ chuyển đến trang Login, đây là nơi chúng ta cần brute-force
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2bce6d86-ea51-4441-8f7b-32de0f0a9c91)

Thử đăng nhập với username và password bất kỳ
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/378f9d22-0cb6-4d53-90b8-f195824cf62c)

Message `Invalid username` → tài khoản có username ‘a’ chưa tồn tại → lợi dụng nó để brute-force username
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3f826344-6ff2-41bb-8f3e-ad75b98e701a)

Xác định vị trí cần brute-force và kiểu tấn công
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d1ab4877-6152-4572-8120-57c55b979f07)

Xác định payload: list username đã chuẩn bị
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3e88e29a-f217-4679-be54-5f56ed9b092b)

Grep-match với message `Invalid username` để tìm các tài khoản chưa tồn tại → tìm ra các tài khoản đã tồn tại trên hệ thống
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/769f8138-b862-43fa-a20b-3d429249d448)

Với tài khoản có username ‘agenda’ không thấy có message → đây là tài khoản đã tồn tại
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/695c3124-a561-41a2-ba44-6c2166aa522b)

→ Thử đăng nhập với username ‘agenda’
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4dce1348-1a8a-4007-b4e4-ea84c218c33c)

Message `Incorrect password` → lợi dụng để bypass
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/92ff35b6-a5e2-4495-974e-032010f0c680)


![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9e957e42-8599-4128-a816-7dfee309349a)
 
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ae4f7eb7-67ab-4973-b18d-455eaddb7642)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/672ab900-db38-4c10-b6f3-4f033cb3524b)

→ đã tìm ra password
Note: Ngoài ra ta có thể brute-force cả 2 vị trí cùng lúc, tuy nhiên sẽ mất thời gian hơn rất nhiều
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ec6eb57a-72ed-427c-b7bb-926700abede7)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/5d139415-0b26-47dc-81c8-235bfb1e013c)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/98f21be0-6251-4b9b-8199-faafb98b28c5)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b0538f81-e1b5-4fbe-884c-5cfa7389a190)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/26eb2fd5-31f6-455c-a62c-f7cabb2d4146)

# [Lab 2: Username enumeration via subtly different responses](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-subtly-different-responses)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/4f895faf-82aa-492b-9760-c7cac400eece)

Bài này tương tự như Lab 1 nhưng sự khác biệt là khi đăng nhập thì message khác tuy nhiên làm tương tự thì vẫn ra.
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/25ff0a30-160c-4389-922b-6b7d0f7bd0b0)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/a1d8932c-9d73-49bb-b045-c31e5858ceb3)
tìm được username
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/09a85183-e1ef-4a0b-9af1-e6f394dd6f15)

tìm được password
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/2e6c231e-13a5-44c9-98d2-b4bffe8e92bc)

login and solve the lab
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/fd94df78-af4a-40b2-b425-a2d37c5ac268)

# [Lab 3: Username enumeration via response timing](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-response-timing)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/68a18d03-87b6-4419-b80b-f4f69208757f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d72a420d-0b58-45aa-afe0-60e2f8377e5c)


thông báo vẫn tương tự như các bài lab trên
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/bb94f4ff-f8ea-426b-a716-ab331d03328e)

khi ta cố gắng đăng nhập → đã bị block IP
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d4693c0b-06a6-47a3-bd93-550e887aa484)

chú ý khi đăng nhập thành công sẽ có thông báo 302 (chuyển trang)

Xác định vị trí cần brute-force và kiểu tấn công


 

 

 

 
# [Lab 4: Broken brute-force protection, IP block](https://portswigger.net/web-security/authentication/password-based/lab-broken-bruteforce-protection-ip-block)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/3fa3bae5-9d63-4428-8317-8456830e8035)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7a4e6f0e-73f2-44b1-989e-245f75c39852)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/447ba243-fc03-4dbd-b117-a33d072ec03b)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/50f050e9-dba4-42ad-8ab6-51560f067d30)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/78c6a7fc-e9c9-44ff-bde6-368d23db7e6f)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ac381cd7-722f-4f75-aa20-c0b8b77c9b13)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/92f5786d-7721-4351-96a2-e55ac3603ede)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0a034893-e1a5-41e7-913a-cc664c48adb6)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0453dda1-33b4-45ab-8c3c-9576731364ed)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0ecc0f9a-ef20-4c3d-b869-be4527d58599)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/c245110e-00cd-428e-a9b2-b64f3e701f2d)
# [Lab 5: Username enumeration via account lock](https://portswigger.net/web-security/authentication/password-based/lab-username-enumeration-via-account-lock)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/933a5a32-5cb9-4bb0-9ebd-fbd8059de79f)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f05a6aec-4630-4494-95b3-dc04d33e444e)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7d4c2d62-4a4d-44ef-a1cd-56a2230ca99c)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/1cd895ca-ec10-4cc4-9617-bc5de0c0e982)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/7a09aca0-96e3-4f5c-8b85-c544d5a583fd)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/0a2ccbdd-2a14-488e-96ed-5ef844719873)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/b8771dca-dfa1-4de8-8f20-fd0bfed21b0a)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6db8649f-b3a1-4f10-b17b-2885cc5b73ec)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/27065dc5-9958-4274-bb56-0bd9db26379b)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/08826639-4f9c-4d01-95ae-4d49284220ce)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/9e1d50c3-5026-49c6-8755-36f5e889e156)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ce2b9ab8-3b9a-4ce8-99d4-b1512096aa93)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/6665a59b-b7a1-4a21-a762-fd36bd225a21)
# [Lab 6: Broken brute-force protection, multiple credentials per request](https://portswigger.net/web-security/authentication/password-based/lab-broken-brute-force-protection-multiple-credentials-per-request)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/f6c017aa-a464-4a64-8c03-58436298e823)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/062919ab-0c6e-4a40-8671-ab154b6a6c0b)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/e5dd0e3c-d308-4ac8-a425-bf2a7ef1cdf0)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/ef53b4ee-878e-4441-b942-4a700b0aec8f)

![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/d2dd7a62-c84f-4415-93a3-0695ebe9ad08)
![image](https://github.com/imHy0/Port_Swigger_Learning/assets/88024759/96de3a22-405f-4524-bdd4-05691845d4dc)
