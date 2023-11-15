## Starlark语言

Starlark是一门配置语言，设计之初是为了作为 Bazel 的配置语言，Starlark语法类似 Python，但不是Python，保持语言类似于 Python 可以减少学习曲线，使语义对用户更加明显。
与 Python 显著不同的地方在于，独立的 Starlark 线程是并行执行的，因此 Starlark 工作负载在并行机器上可以很好地伸缩。

## 相关库
- [Go实现的starlark解释器](https://github.com/google/starlark-go)
- [Rust实现的starlark解释器](https://github.com/facebookexperimental/starlark-rust)
- [starlark语言规范](https://github.com/bazelbuild/starlark)
