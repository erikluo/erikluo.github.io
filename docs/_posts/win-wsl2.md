## WSL2
WSL2底层完全采用虚拟机实现，体验上基本上接近真实的Linux系统。但依然有些不足，记录如下：

* 文件系统性能
* WSL2内如何连接到windows？
    - [这里有介绍](https://superuser.com/questions/1679757/how-to-access-windows-localhost-from-wsl2)
    - 通过 $(hostname).local， 如： telnet  $(hostname).local 1080

* docker通信问题
    - Windows —> docker-server -> linux-docker 这条网路是不通的。
    - 只能采用Windows -> docker-server -> windows-docker
    - 并且windows-docker内监听端口的地址只能是 0.0.0.0 ，而不能是 127.0.0.1.

### WSL2 如何支持图形界面
* [WSLg is short for Windows Subsystem for Linux GUI](https://github.com/microsoft/wslg)

### WSL如何使用代理
wsl1
```
# WSL1
alias www='https_proxy="http://127.0.0.1:8080" http_proxy="http://127.0.0.1:8080"'

# or simply
export https_proxy="http://127.0.0.1:8080"
export http_proxy="http://127.0.0.1:8080"
```

wsl2
```
# WSL2
export hostip=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')
alias www="https_proxy=\"http://${hostip}:8080\" http_proxy=\"http://${hostip}:8080\""

# or set it global
export hostip=$(cat /etc/resolv.conf | grep nameserver | awk '{ print $2 }')
export https_proxy="http://${hostip}:8080" 
export http_proxy="http://${hostip}:8080"
```
### 其它问题
- [解决访问不了域名如github的问题 How do I change the DNS settings for WSL2?](https://superuser.com/questions/1533291/how-do-i-change-the-dns-settings-for-wsl2)

