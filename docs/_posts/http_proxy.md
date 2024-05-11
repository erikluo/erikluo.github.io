# http/https 代理技术原理
注意点：
代理服务器在处理http https代理时原理约有不同： http纯转发， https转发前多一步Connect操作。

## 技术原理介绍文章
- [HTTP、HTTPS代理分析及原理](https://lilywei739.github.io/2017/01/25/principle_for_http_https.html)
- [通过实验认识HTTP代理](https://zhuanlan.zhihu.com/p/349028243)

## 一些代理实现
- [tinyproxy C 语言实现](https://github.com/tinyproxy/tinyproxy)
- [goproxy - An HTTP proxy library for Go， 可用来用go实现自己的http/https代理服务器](https://github.com/elazarl/goproxy)
