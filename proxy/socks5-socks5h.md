# Socks5 and Socks5h differences

## 情景

设置好了proxy，浏览器可以正常访问。但是 Curl 等终端类工具无法访问。

```
1) curl https://www.google.com -x 127.0.0.1:1081
2）curl https://www.google.com -x http://127.0.0.1:1081
3）curl https://www.google.com -x socks://127.0.0.1:1080
4）curl https://www.google.com -x socks4://127.0.0.1:1080
5）curl https://www.google.com -x socks5://127.0.0.1:1080
6）curl https://www.google.com -x socks4a://127.0.0.1:1080
7）curl https://www.google.com -x socks5h://127.0.0.1:1080
```

如上所示，在 curl 中可以用 `-x` 指定 curl 通过某个隧道来连接网络。  
默认情况，curl 用 http 隧道（1、2），即使使用 socks，也是默认使用的 socks4 隧道。  
只有显式声明使用 socks5 时，才会真正走 socks5 隧道。

## 代理域名解析机制
1. socks（默认为 socks4）, socks4 和 socks5 隧道都是由本机进行目标域名的 DNS 解析的。

2. http，socks4a 和 socks5h 都是由代理端服务器完成 DNS 解析的.

即是通过修改本机 hosts 是可以影响 socks4 与 socks5 代理后的目标 IP 地址。

说明 socks4 和 socks5 在 DNS 受污染区域谁呀很大可能会导致访问失败的。

## 结论
1. 修改本机 DNS 服务器， 直接用 Google 等 DNS。（速度和可靠性很难保障）

2. 直接用 http, socks4a 和 socks5h 

