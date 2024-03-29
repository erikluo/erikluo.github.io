## Prometheus

**架构如下**</br> 

![](img/prometheus_architecture.png)

[开放指标规范定义规范](https://github.com/OpenObservability/OpenMetrics/blob/98ae26c87b1c3bcf937909a880b32c8be643cc9b/specification/OpenMetrics.md#info-1)

### pull模式

### push模式
虽然说pull模式是官方推荐的，但对于某些情况下，比如我们将prometheus搭建在外网去监控内网应用的情况下，由于内网有诸多安全限制使得无法穿透，这时就要借助push模式来解决问题。prometheus提供了Pushgateway组件来实现，
[pushgateway github](https://github.com/prometheus/pushgateway)

这里仍然通过docker安装：
```
docker pull prom/pushgateway
docker run -d -p 9091:9091 prom/pushgateway "-persistence.file=push_file"
```
-persistence.file=push_file 参数，这是为pushgateway指定的参数，默认pushgateway是不持久化数据的，这意味着如果shutdown，过去的数据将丢失，对于监控系统来说这通常没有什么问题，但如果有需要持久化数据的情况，就需要加入这个参数。

**pushgateway缺点**
- Prometheus拉取状态只针对 pushgateway, 不能对每个节点都有效
- Pushgateway出现问题，整个采集到的数据都会出现问题
- 监控下线，prometheus还会拉取到旧的监控数据，需要手动清理 pushgateway不要的数据。

### 相关类库
* C/C++
    - [prometheus-cpp](https://github.com/jupp0r/prometheus-cpp)
    - [prometheus-client-c](https://github.com/digitalocean/prometheus-client-c)

* Go
    - [Prometheus 监控系统和时间序列数据库](https://github.com/prometheus/prometheus)
    - [node_exporter](https://github.com/prometheus/node_exporter)
    - [client_golang-go应用程序接入类库](https://github.com/prometheus/client_golang)
    - [client_golang guide](https://prometheus.io/docs/guides/go-application/)

## 常见问题
- [Prometheus性能调优-什么是高基数问题以及如何解决?](https://juejin.cn/post/7213171235579543612)
  
## 参考资料 
- [prometheus-book](https://yunlzheng.gitbook.io/prometheus-book/introduction)
- [开放指标规范定义](https://github.com/OpenObservability/OpenMetrics/blob/98ae26c87b1c3bcf937909a880b32c8be643cc9b/specification/OpenMetrics.md#info-1)
- [CLIENT LIBRARIES](https://prometheus.io/docs/instrumenting/clientlibs/)
- [技术分享：Prometheus是怎么存储数据的（陈皓）](https://www.youtube.com/watch?v=qB40kqhTyYM)
