## 进程管理

对于后台开发，当有多个服务进程需要启动编排时，需要使用进程管理工具，常见的有这些

- systemd：一个在Linux系统上管理系统进程和服务的系统管理器，可以自动启动和停止进程，并提供了其他高级功能。
- Docker：一个用于创建，部署和运行容器化应用程序的平台，可以管理应用程序的进程和资源。
- Kubernetes：一个用于自动化部署，扩展和管理容器化应用程序的开源平台，可以管理多个进程和实例。
- supervisor：一种用于管理和监控后台进程的工具，支持Linux和Unix系统。
- PM2：一个用于管理Node.js应用的进程管理工具，可以启动，停止，重启和监控应用程序进程。
- Foreman： 用于管理应用程序中的后台进程。它使用一个单独的Procfile文件来定义需要运行的进程，并可以并行启动和停止它们。Foreman还提供了日志记录功能和监控进程的能力。

### foreman
forman原本是Ruby实现的用来管理进程的工具, 它需要使用Procfile来定义运行的进程。
- [ruby forman](https://github.com/theforeman/foreman)
- [ruby forman 另一种实现](https://github.com/ddollar/foreman)
- [forman doc](https://theforeman.org/manuals/3.8/quickstart_guide.html)
- [一个使用forman的例子](https://mattstauffer.com/blog/using-a-procfile-to-streamline-your-local-development/)
- [procfile intro](https://devcenter.heroku.com/articles/procfile)

Procfile 是一个文本文件，用于定义在应用程序中启动的各个进程。它的格式为每行一个进程定义，包括进程的名称和启动命令。以下是一个 Procfile 的示例：
```
web: bundle exec rails server
worker: bundle exec sidekiq
```
在这个示例中，Procfile 定义了两个进程：web 和 worker。web 进程会通过运行 bundle exec rails server 命令来启动 Rails 服务器，而 worker 进程会通过运行 bundle exec sidekiq 命令来启动 Sidekiq 任务队列。

用 Foreman 运行这些进程时，可以使用以下命令：
```
foreman start
```
可能是由于foreman比较简单好用吧，相比于supervisor来说。 其它各语言也实现了foreman的翻版。如：
- [Honcho: a python clone of Foreman. For managing Procfile-based applications.](https://github.com/nickstenning/honcho)
- [Foreman in Go](https://github.com/ddollar/forego)
