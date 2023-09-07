## 网络性能测试工具

### iperf
* iperf
    - Iperf是一个网络性能测试工具。Iperf可以测试TCP和UDP带宽质量
    - [code下载地址](https://code.google.com/archive/p/iperf/downloads)

* 使用方法
    - 服务端运行iperf，输入命令，在本机端口12345上启用iperf, 1s 打印一次信息。
      ```
      iperf3  -s -p 12345 -i 1
      ```
    - 客户端运行iperf，输入命令
      ```
      iperf3  -c dev180 -p 12345 -i 1 -t 10 -w 20k
      ```

* 参数说明  
    - -c：客户端模式，后接服务器ip
    - -p：后接服务端监听的端口
    - -i：设置带宽报告的时间间隔，单位为秒
    - -t：设置测试的时长，单位为秒
    - -w：设置tcp窗口大小，一般可以不用设置，默认即可
