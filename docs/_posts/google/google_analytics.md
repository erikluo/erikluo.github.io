# 使用Google Analytics分析网站流量

  
## 关于 universal analytics 和 google analytics  

universal analytics 是老的产品名，谷歌将在2023年停止，取而代之的是google analytics。

细节比较：

|     |     |     |
| --- | --- | --- |
|     | universal analytics | google analytics |
| js脚本 | analytics.js | gtag.js |
| 跟综Id术语 | Track Id | 衡量 Id |
| 跟综Id的取值 | UA-XXXXXXX | G-XXXXXXX |

## universal analytics[老产品] 

使用案例参考：[erikluo.github.io](https://erikluo.github.io)

使用方式如下：

```
<script>
      // prettier-ignore
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
    (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
    m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
    })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

      ga('create', 'UA-153180559-1', 'auto');
      if (location) {
        ga('send', 'pageview', location.hash);
      }
    </script>
```

这段代码的作用是异步加载Google Analytics的JavaScript库，并设置一个全局ga()函数，即使在脚本完全加载之前调用ga()命令，也能将这些命令排队，待脚本加载完成后执行。

这种模式确保了跟踪代码不会阻塞页面加载，同时保证所有跟踪事件都能被正确记录。

关于 https://www.google-analytics.com/analytics.js 的代码注释，参考：https://gist.github.com/zmmbreeze/ddb4b3a619187b923dc2c009b4323a42


## 如何使用 google analytics  


需要先在google analytics网站，开通google analytics服务， 开通过程是：

创建媒体资源，然后再创建数据流，每个数据流对应一个衡量Id， 有了衡量Id才能使用 gtag.js 跟综网页的访问情况。

使用方式如下：

```
//请将全局网站代码复制到 HTML 的 <head> 部分。或者，如果您使用的是网站开发工具（例如 GoDaddy、Shopify 等），请按照相应说明为您的网站添加代码。

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-Your_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', 'G-Your_ID);
</script>
```