## 网关整理
评价标准
- 主要用途
- 成本
- 配置语言
- 开发语言
- 协议
- websocket
- 鉴权
- routing
- 服务发现 
- 健康检查
- 限流|
- 负载均衡算法
- Metrics/Tracing

纵观业内各个开源的网关实现方案，从语言层面来看，大概可以分成三类：
- C/C++派系，如Nginx、haproxy，通常有着极致的性能，常用于流量网关。
- Java派系，如Zuul
- Go派系，如Traefik
- 基于C/C++其进行Lua扩展的派系

根据具体的业务需求，流量网关通常选择C/C++派系，业务/API 网关选择其它派系。


### 表格

| Column 1 |开源 |开发语言 |协议|鉴权|routing|限流|负载均衡算法|Metrics/Tracing|
| -------- | -------- | -------- |-------- |-------- |-------- |-------- |-------- |-------- |
|  Nginx |yes|C|tcp/http,https|插件扩展|port,host,path,method|yes|轮询/weight/ip_hash/url_hash/fair|yes|
| Haproxy |yes|C|http,https,websocket|wechat|host,path,method|yes|roundrobin/static-rr/WLC/ip_hash/url_hash/cokkie_hash|yes|
|  Envoy |yes|C++|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Kong |yes|Lua|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
| apisix |yes|Lua|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Traefik |yes|Go|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
| Linkerd |yes|Go|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
| BFE |yes|Go|http,https,SPDY,HTTP/2|wechat|host,path,method|yes|轮询，哈希|yes|
|  Ambassador |yes|Python/Go|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Tyk  |yes|Go|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
| gateway |yes|Go|http,grpc|wechat|host,path,method|yes|轮询，哈希|yes|
| Apinfo |yes|Go|HTTP/HTTPS、gRPC、Dubbo2、SOAP|wechat|host,path,method|yes|轮询，哈希|yes|
|  Zuul |yes|java|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  spring-cloud-gateway |yes|java|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|

### 列表[按字母排列]
* Ambassador 可扩展的API网关
    - [github](https://github.com/emissary-ingress/emissary)
    - 是一个开源的微服务 API 网关，建立在 Envoy 代理之上，为用户的多个团队快速发布，监控和更新提供支持.
    - 支持处理 Kubernetes ingress controller 和负载均衡等功能，可以与 Istio 无缝集成。
* Apigee 商业级的API网关
* apinto 基于 Golang 开发的微服务网关
    - [github](https://github.com/eolinker/apinto)
* apisix- Apache Cloud-Native API Gateway
    - [github](https://github.com/apache/apisix)
    - 是一个高性能、可扩展的微服务API网关，基于 nginx（openresty）和 Lua 实现功能
    - 借鉴了Kong的思路，将Kong底层的关系型数据库（Postgres）替换成了NoSQL型的 etcd，这使得 APISIX 相较于 Kong 在性能上有了很大提升，在启用各类插件的情况下，Apache APISIX 的性能据说是 Kong 的 10 倍。
* bfe 百度开源的现代化、企业级的七层负载均衡系统
    - [github](https://github.com/bfenetworks/bfe)
* Goku API网关
* gateway API网关
    - [github](https://github.com/go-kratos/gateway)
* Haproxy
    - 是一款提供高可用性、负载均衡以及基于TCP（第四层）和HTTP（第七层）应用的代理软件
    - 支持虚拟主机，它是免费、快速并且可靠的一种解决方案。 HAProxy特别适用于那些负载特大的web站点.
    - 冗余协议（VRRP）来实现高可用.
* Istio 可扩展的服务网格
* Kong
    - Kong是一个在 Nginx 中运行的Lua应用程序，并且可以通过lua-nginx模块实现，Kong不是用这个模块编译Nginx，而是与 OpenResty 一起发布
    - OpenResty已经包含了 lua-nginx-module， OpenResty 不是 Nginx 的分支，而是一组扩展其功能的模块。
    - 配置 RestApi/nginx.conf
    - [kong-dashboard](https://github.com/PGBI/kong-dashboard)
* KongTyk
* KrakenD 可扩展的API网关
* Linkerd 可扩展的服务网格
    - [github](https://github.com/linkerd/linkerd2)
* Nginx
    - [cookie会话保持模块](https://github.com/michaelneale/nginx-sticky-module)

* spring-cloud-gateway 基于Spring Framework的Gateway
    - [github](https://github.com/spring-cloud/spring-cloud-gateway)
* Traefik 可扩展的HTTP服务器
    - 是一个现代 HTTP 反向代理和负载均衡器，可以轻松部署微服务
    - Traeffik 可以与您现有的组件（Docker、Swarm，Kubernetes，Marathon，Consul，Etcd，…）集成，并自动动态配置。
* Tyk
* WSO2 API Microgateway
* Zuul
    -  是一种提供动态路由、监视、弹性、安全性等功能的边缘服务。Zuul 是 Netflix 出品的一个基于 JVM 路由和服务端的负载均衡器。
* Gravitee



## 参考
- [微服务五种开源API网关实现组件对比](https://blog.51cto.com/u_11976981/5900465)
- [Nginx限流配置](https://www.cnblogs.com/biglittleant/p/8979915.html)
- [Nginx 的两种限流方式](https://toutiao.io/posts/r9wf3f/preview)
- [nginx-prometheus-exporter](https://github.com/nginxinc/nginx-prometheus-exporter)
- [Nginx 会话保持](https://www.jianshu.com/p/b97d276b8f6d)
