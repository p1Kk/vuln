# TOTOLINK EX1200T LEAK

## Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

The attacker can get the sensitive information (wifikey, wifiname, etc.) without authorization.

Actually, `getXxxx` functions in *.so* files have sensitive information leakage, I'm not going to list them all…

## PoC

![image-20211101170237066](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211101170237066.png)

```
{"topicurl":"setting/getWiFiApInfo"}
```

