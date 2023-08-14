## 抓包工具集合


|        工具名称        | 描述                              |官网      |
|:-----------------:|:--------------------------------|:--------------------------------|
|     tcpdump        | 命令行                 |    |
|     wireshark        | GUI，开源，配合tcpdump                 ||
|     Charles        | 商用，Win/Mac/Linux                 |https://www.charlesproxy.com/|
|     Fiddler        | 商用，Win/Mac/Linux                 |https://www.telerik.com/|
|     mitmproxy        | 开源， Python开发                 |https://mitmproxy.org/|
|     Stream        | App              |AppStore|

### mitmproxy
在devcloud上用容器启动
```
sudo docker run -it --rm -p 8081:8081 -p 8080:8080  mitmproxy/mitmproxy mitmweb --web-host 0.0.0.0
```
在pc上用浏览器打开，http://{ip}:8081  
注意，只能用ip，不能用域名。否则页面空白。
