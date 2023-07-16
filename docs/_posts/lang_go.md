
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

**服务器框架**<br>
- [zinx](https://github.com/aceld/zinx) 轻量级tcp长连接框架。
- [easytcp](https://github.com/DarthPestilane/easytcp)

## Go语言嵌入支持
* [Go embed 简明教程](https://colobu.com/2021/01/17/go-embed-tutorial/)
* [Go embed参考代码](https://github.com/soulteary/forever-coolshell)

