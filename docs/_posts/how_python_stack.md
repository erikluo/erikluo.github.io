## 如何实时查看运行着的python程序的堆栈
两种方案：

### 方案一
gdb attach
由于gdb只能显示底层函数的堆栈，无法解析到python函数层面，所以需要用一个~/.gdbinit 脚本辅助查看堆栈，
测试过程中发现，其实不用脚本，显示的堆栈可读性也相当友好了。但需要安装python的debuginfo包。

### 方案二
信号 + showstack
使用程序语言自身打印堆栈的功能，在收到信号时打印出来。
参考代码
```
import code, traceback, signal

def debug(sig, frame):
    """Interrupt running process, and provide a python prompt for
    interactive debugging."""
    d={'_frame':frame}         # Allow access to frame object.
    d.update(frame.f_globals)  # Unless shadowed by global
    d.update(frame.f_locals)

    i = code.InteractiveConsole(d)
    message  = "Signal received : entering python shell.\nTraceback:\n"
    message += ''.join(traceback.format_stack(frame))
    i.interact(message)

def listen():
    signal.signal(signal.SIGUSR1, debug)  # Register handler
```

## 参考文档
- [](https://stackoverflow.com/questions/132058/showing-the-stack-trace-from-a-running-python-application)

- [](https://wiki.python.org/moin/DebuggingWithGdb)