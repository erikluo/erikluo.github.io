## WSL2
WSL2底层完全采用虚拟机实现，体验上基本上接近真实的Linux系统。但依然有些不足，记录如下：

### 文件系统性能

### docker通信问题
Windows —> docker-server -> linux-docker 这条网路是不通的。

只能采用
Windows -> docker-server -> windows-docker

并且windows-docker内监听端口的地址只能是 0.0.0.0 ，而不能是 127.0.0.1.
