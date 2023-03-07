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


### 表格

| Column 1 |开源 |开发语言 |协议|鉴权|routing|限流|负载均衡算法|Metrics/Tracing|
| -------- | -------- | -------- |-------- |-------- |-------- |-------- |-------- |-------- |
|  Kong |yes|xx|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Traefik |yes|xx|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Ambassador |yes|xx|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Tyk  |yes|xx|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|
|  Zuul |yes|xx|http,https,websocket|wechat|host,path,method|yes|轮询，哈希|yes|

### 列表[按字母排列]
* Ambassador 可扩展的API网关
* Apigee 商业级的API网关
* Goku API网关
* Istio 可扩展的服务网格
* Kong
    - 配置 RestApi/nginx.conf
* KongTyk
* KrakenD 可扩展的API网关
* Linkerd 可扩展的服务网格
* Nginx
* Traefik 可扩展的HTTP服务器
* Tyk
* WSO2 API Microgateway
* Zuul
* Gravitee



## 参考
- [微服务五种开源API网关实现组件对比](https://blog.51cto.com/u_11976981/5900465)
