## 网关模式
- [Mac 电脑使用 ClashX Pro 作为网关旁路由](https://qust.me/post/clashxProMac/)

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

## Proxy UI 客户端
* ClashX
    - [ClashX](https://github.com/Dreamacro/clash)
    - [ClashX Pro-无源码](https://install.appcenter.ms/users/clashx/apps/clashx-pro/distribution_groups/public)
* V2rayU
    - [V2rayU-伪全局模式](https://github.com/yanue/V2rayU/tree/rm)
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


## 工具
* [IP地址分数查询](https://scamalytics.com/)
* 查看ip地址信息：curl ipinfo.io
## 参考资料
- <https://github.com/yangchuansheng/love-gfw>
- [V2Ray 配置指南](https://toutyrater.github.io/)
- [左耳朵耗子-科学上网](https://github.com/haoel/haoel.github.io)
- [ProxyTool](https://github.com/githubvpn007/ProxyTool)
- [Clash Premium 规则集](https://github.com/Loyalsoldier/clash-rules)



