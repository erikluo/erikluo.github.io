## 环境变量配置
```
#p4 env
export P4PORT=xx.p4.com:port
export P4USER=admin
export P4CONFIG=.p4config
export P4TICKETS=.p4tickets
```
## 在项目目录下使用config文件让每个项目使用不同的配置
.p4config内容如下：

```
P4PORT=xx.p4.com:port
P4USER=admin
P4CLIENT=myproj
```

## 拉取代码到本地
```
 CLIENT=myproj
 p4 sync --parallel=0 //${CLIENT}/...
```

## 避免每次输入密码：
```
p4 -E P4TICKETS=.p4tickets login -a
```

## 一次完整的代码提交流程命令
- 查看修改了哪些文件内容
```
p4 diff -du test/aa/...
```

- 修改完代码，将修改的文件添加到changelist
```
p4 diff -se test/aa/... | p4 -x - edit
```

- 修改changelist
```
p4 change
```

- 将changelist添加到shelve，添加完成后可在swarm网页中查看
```
 p4 shelve -c  123
 # 如果此时发现有bug，再次修改了代码，修改完成后，再强制执行一次
 p4 shelve -f -c  123
```
- 提交代码
```
p4 shelve -d -c 123
p4 submit -c 123
```
