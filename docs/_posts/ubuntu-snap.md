## ubuntu snap
snap是一种安全、通用的linux软件包，基于SquashFS文件系统实现。

代理设置
```
$ sudo snap set system proxy.http="http://<proxy_addr>:<proxy_port>"
$ sudo snap set system proxy.https="http://<proxy_addr>:<proxy_port>"
```

查看设置的代理
```
sudo snap get system proxy
```

安装软件
```
sudo snap install telegram-desktop
```
卸载软件
```
sudo snap remove code
```
列出已安装的软件
```
sudo snap list
```
