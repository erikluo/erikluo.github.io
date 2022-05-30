---
layout: post
title: "Linux下为sudo命令定义环境变量"
subtitle: ""
author: "erikluo"
header-img: ""
header-mask: 0.2
tags:
  - linux
---

比如加入/usr/local/bin到其中
```
Defaults    secure_path = /sbin:/bin:/usr/sbin:/usr/bin:/usr/local/bin
```
