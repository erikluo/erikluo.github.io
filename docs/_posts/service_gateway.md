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

| Column 1 |开源 |配置语言 |开发语言 |协议|鉴权|routing|限流|负载均衡算法|Metrics/Tracing|
| -------- | -------- | -------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |
|  Kong |yes|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket||wechat|host,path,method|yes|轮询，哈希|yes|
|  Traefik |yes|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket||wechat|host,path,method|yes|轮询，哈希|yes|
|  Ambassador |yes|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket||wechat|host,path,method|yes|轮询，哈希|yes|
|  Tyk  |yes|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket||wechat|host,path,method|yes|轮询，哈希|yes|
|  Zuul |yes|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket||wechat|host,path,method|yes|轮询，哈希|yes|

### 列表
* Kong
* Traefik
* Ambassador
* Tyk
* Zuul
