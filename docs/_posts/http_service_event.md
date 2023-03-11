## http服务端事件推送

* 方案
    - websocket
    - chunk
    - SSE

* SSE 与websocket的区别：
    - SSE 提供单向通信，Websocket 提供双向通信；
    - SSE 是通过 HTTP 协议实现的，Websocket 是单独的协议；
    - 实现上来说 SSE 比较容易，Websocket 复杂一些；
    - SSE 有最大连接数限制；
    - WebSocket可以传输二进制数据和文本数据，但SSE只有文本数据；

* Python SSE库
    - [aiohttp-sse](https://github.com/aio-libs/aiohttp-sse)

* Go SSE库
    - [sse](https://github.com/r3labs/sse)
    - [eventsource](https://github.com/antage/eventsource)
    - [go-sse](https://github.com/alexandrevicenzi/go-sse)
    - [使用Golang实现服务端推送SSE例子](https://github.com/JasonkayZK/go-learn/tree/sse)

* ReactNative
    - [react-native-fetch-stream](https://github.com/react-native-community/fetch)
    - [react-native-sse](https://github.com/binaryminds/react-native-sse)

* Reference
    - [Server-Sent Events 教程](https://www.ruanyifeng.com/blog/2017/05/server-sent_events.html)
