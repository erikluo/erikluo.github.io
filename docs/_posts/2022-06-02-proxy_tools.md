---
layout: post
title: "梯子/机场方案整理"
subtitle: ""
author: "erikluo"
header-img: ""
header-mask: 0.2
tags:
  - ss
  - proxy
---

## 网关模式
### 硬路由
> 路由器刷openwrt固件 

<https://github.com/hackgfw/openwrt-gfw> 

### 软路由

#### Linux

- openwrt + ss: 
 <https://openwrt.org/> 
 
- shadowsocks + dnsmasq + ipset + iptables + ss-redir 
 <https://github.com/Witee/Note-shadowsocks>
 
- shadowsocks + dnsmasq + route + tuntap   


#### Win
v2rayN 

<https://github.com/2dust/v2rayN> 

<https://gitbook.skicat.io/windows/v2rayn>

clash

<https://gitbook.skicat.io/windows/clash-windows>

#### Mac
ClashX pro: 

<https://docs.cfw.lbyczf.com/contents/ui.html>

<https://gitbook.skicat.io/mac/clash-mac> 

<https://github.com/yichengchen/clashX> 


Surge: 

#### VirtualBox+openwrt
<https://github.com/overcache/VRouter> 

## 软件模式
- [go-shadowsocks2](https://github.com/shadowsocks/go-shadowsocks2)
- [v2ray](https://github.com/v2fly/v2ray-core)

## LocalProxy
### ss
<https://github.com/shadowsocks> 

### netch
<https://github.com/netchx/netch> 

## vpn
- [setup-ipsec-vpn](https://github.com/hwdsl2/setup-ipsec-vpn)

## Proxy客户端
- netch
- proxifier
- shadowlink
- shadowrocket(收费)

## Proxy命令行
- tsocks
- proxychains
- [sthp socks5转http](https://github.com/KaranGauswami/socks-to-http-proxy)

## 代理中转工具
- [gost](https://github.com/ginuerzh/gost)
- [gost2](https://github.com/go-gost/gost)
- [v2ray中转](https://toutyrater.github.io/advanced/vps_relay.html)
- nginx中转
```
stream {
        proxy_connect_timeout 3s;
        upstream node {
                server proxy.xx.com:8443;
       }
        server {
            listen 8443;
            proxy_connect_timeout 3s;
            proxy_timeout 3s;
            proxy_pass node;
        }
}
```
- firewalld/iptables

## 搭建历程
王者海外版（）连接 新加坡服务器，网络延迟超过400ms，导致无法排位。

## 参考资料
- <https://github.com/yangchuansheng/love-gfw>
- [V2Ray 配置指南](https://toutyrater.github.io/)



