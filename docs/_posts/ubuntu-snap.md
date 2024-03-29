## ubuntu snap 简介
snap是一种安全、通用的linux软件包，基于SquashFS文件系统实现。snap包括安装包、依赖项、运行环境，因此可以在支持snap的linux环境中保证以相同的方式运行（类似docker）。
Linux中类似的软件发行方式还包括：
- [appimage](https://appimage.org/)
- [flatpak](https://flatpak.org/)

## AppImage
- [appimage github.io](https://appimage.github.io/apps/)
- [AppImage hub](https://www.appimagehub.com/)

## snap系统组件
- snapd（类似dockerd）
- snap （类似docker）
- snap store（类似docker hub）

## 常用命令
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
