## 网关

| Column 1 | 主要用途 | 成本 |配置语言 |开发语言 |协议 |websocket|鉴权|routing|服务发现 |健康检查 |限流|负载均衡算法|Metrics/Tracing|
| -------- | -------- | -------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |-------- |
|  Kong | 企业级API管理|开源/企业版|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket|yes||wechat|host,path,method|yes|yes|yes|轮询，哈希|yes|
|  Traefik  |  企业级API管理|开源/企业版|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket|yes||wechat|host,path,method|yes|yes|yes|轮询，哈希|yes|
|  Ambassador  |  企业级API管理|开源/企业版|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket|yes||wechat|host,path,method|yes|yes|yes|轮询，哈希|yes|
|  Tyk  |  企业级API管理|开源/企业版|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket|yes||wechat|host,path,method|yes|yes|yes|轮询，哈希|yes|
|  Zuul  |  企业级API管理|开源/企业版|Admin Rest api, Text file(nginx.conf 等)|xx|http,https,websocket|yes||wechat|host,path,method|yes|yes|yes|轮询，哈希|yes|
