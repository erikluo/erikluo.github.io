---
layout: post
title: "编程语言文档及技巧"
subtitle: ""
author: "erikluo"
header-img: ""
header-mask: 0.2
tags:
  - 编程语言
---


## C/C++

- <https://cplusplus.com/>

## Object-C
- [Objective-C教程](https://www.runoob.com/ios/ios-objective-c.html)

**开源webserver**<br>
- [civetweb](https://github.com/civetweb/civetweb)

## Rust
- [Rust教程](https://www.runoob.com/rust/rust-tutorial.html)
- [Rust语言圣经 github](https://github.com/sunface/rust-course)
- [Rust语言圣经](https://course.rs/about-book.html)


## Python
**帮助文档**<br>
- [python builtin functions](https://docs.python.org/3/library/functions.html#func-list)

**启动http服务器** <br>
```
# python2
python2 -m SimpleHTTPServer 8080

# python3
python3 -m http.server 8080
```

**日志方案**<br>
- logging
```
import logging
logging.basicConfig(stream=sys.stdout, level=logging.DEBUG,
                    format='%(asctime)s - %(levelname)s - %(filename)s:%(funcName)s:%(lineno)s - %(message)s')

```

- loguru
```
from loguru import logger
```

### python Web框架
**web框架文档**<br>
- [django](https://www.djangoproject.com/)
- [django github](https://github.com/django/django)
- [flask github](https://github.com/pallets/flask)
- [aiohttp](https://docs.aiohttp.org/en/stable/)

**web框架应用**<br>
- [aiohttp -> ray dashboard实现](https://github.com/ray-project/ray/)
- [flask -> Web自建图床](https://gitee.com/staugur/picbed)

## Golang
- <https://www.runoob.com/go/go-functions.html>  

**调试工具**<br>
- gdb： 通用，不能直接反映go语言的特点，比如gorouting。
- [dlv](https://github.com/go-delve/delve)

**整数字符串互转**<br>
- string转成int:  int, err := strconv.Atoi(string)
- string转成int64: int64, err := strconv.ParseInt(string, 10, 64)
- int转成string: string := strconv.Itoa(int)
- int64转成string: string := strconv.FormatInt(int64,10)


## Java

## JavaScript
- [ES6 入门教程](https://es6.ruanyifeng.com/)
- [ ES6 教程](https://www.runoob.com/w3cnote/es6-tutorial.html)

**闭包**
类是有行为的数据，闭包是有数据的行为。   
- [js闭包](https://www.ruanyifeng.com/blog/2009/08/learning_javascript_closures.html)


### 跨平台框架
#### React-native： 大量使用JS的扩展语法jsx.
- [native框架](https://github.com/facebook/react-native)
- [react-native各类学习资源汇集](https://github.com/reactnativecn/react-native-guide)
- [react-native各类学习资源汇集-English](https://github.com/jondot/awesome-react-native)
- [react-native-热更-react-native-code-push](https://github.com/microsoft/react-native-code-push)
- [code-push-server](https://github.com/lisong/code-push-server)
- [react-native-pushy-热更国内方案](https://github.com/reactnativecn/react-native-pushy/)
- [Android Docker Image for react native-github](https://github.com/react-native-community/docker-android)
- [Android Docker Image for react native-dockerhub](https://hub.docker.com/r/reactnativecommunity/react-native-android)
- [react-native grpc](https://github.com/DaniJG/react-native-grpc)
- [react-native docs中文](https://reactnative.cn/docs/getting-started)
- [react-native docs](https://reactnative.dev/docs/getting-started)

#### Vue：大量使用模板技术.
- [native框架 weex](https://github.com/alibaba/weex)
- [weex应用-网易严选](https://github.com/zwwill/yanxuan-weex-demo)

### Nodejs
**包管理工具**<br>
yarn，npm 都是nodejs的包管理工具，区别
- npm: 不用单独安装，它随 node 一起提供
- yarn: Facebook、Google、Exponent 和 Tilde 联合推出，取代npm,  npm install -g yarn

## TypeScript
- [github](https://github.com/microsoft/TypeScript)
- [typescript教程](https://www.runoob.com/typescript/ts-tutorial.html)
## C#
## Lua
## Markdown
- <https://markdown.com.cn/basic-syntax/>
