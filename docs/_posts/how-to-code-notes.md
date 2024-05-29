# 我是怎么对代码进行注释的

在试着熟悉别人的代码时，你总希望他们留下的代码注释能对你理解代码有所帮助。同理，无论为了自己还是其他人，编写代码时写注释是好习惯。所有编程语言都有专门的注释语法，注释可以是一个单词、一行文字、甚至是一整段话。编译器或解释器处理源代码时会忽略注释。

## 方法一

**Step1 查找相关文章并编号**

如：
```

CodeReview
--------

- [001 UE4网络同步-客户端连接DS的流程](https://zhuanlan.zhihu.com/p/533748683)
- [002《UE4 Notes》Linux端使用fork优化DS启动和内存](https://zhuanlan.zhihu.com/p/628867664)
- [003 Create A Standalone Application in UE4](https://imzlp.com/posts/31962/)
- [004 UE4 Program 类型工程的限制和解决方法](https://zhuanlan.zhihu.com/p/145633340)
- [005 出动200人，已获版号，朝夕光年这款自研UE产品遇到了哪些难题？](https://youxiputao.com/article/24320)
- [006 UE4 DS服务器性能优化](https://zhuanlan.zhihu.com/p/511211805)
- [007 UE4中的Tick机制浅析](https://zhuanlan.zhihu.com/p/538908009)
- [008 Unreal TickFunc调度](https://cloud.tencent.com/developer/article/2033950)
- [009《Exploring in UE4》网络同步原理深入（上）[原理分析]](https://zhuanlan.zhihu.com/p/34723199)
- [010《Exploring in UE4》网络同步原理深入（下）](https://blog.uwa4d.com/archives/USparkle_Exploring1.html)
- [011 UE网络通信(一) 概述](https://cloud.tencent.com/developer/article/2033945)
- [012 UnrealEngine - 网络同步之连接篇](https://www.cnblogs.com/lawliet12/p/17332897.html)
- [013 ue4 网络的最佳实践](https://zhuanlan.zhihu.com/p/433342457)
- [014 UE4-多人游戏框架理解](https://stonelzp.github.io/ue4-multiplay-framework/)
- [015 UE4 复制图快速共享路径起始指南](https://zhuanlan.zhihu.com/p/644496605)
```

**Step2 需要在代码中注释的地方，使用关键字**

注释中可包含关键字 // review[编号]， 如：

```
//review001 Server走InitListen，客户端InitConnect。

bool UIpNetDriver::InitConnect( FNetworkNotify* InNotify, const FURL& ConnectURL, FString& Error )
{
	if( !InitBase( true, InNotify, ConnectURL, false, Error ) )
	@@ -481,6 +483,9 @@ bool UIpNetDriver::InitConnect( FNetworkNotify* InNotify, const FURL& ConnectURL
	return true;
}
```


**Step3 下次阅读代码时，搜索关键字：review[编号]**

## 方法二

使用 代码文档API生成工具生成文档，常用的工具有:

- [doxygen](https://github.com/doxygen/doxygen)
- [Sphinx](https://github.com/sphinx-doc/sphinx)

Sphinx 自身的文档也是该工具生成的，[文档源码](https://github.com/sphinx-doc/sphinx/tree/master/doc)

这里主要介绍 Doxygen 的用法

**Step1 安装**

```
sudo apt-get install doxygen
```

**Step2 生成模板文件**

如果 Doxyfile 文件不存在，你可以用 Doxygen 生成一个标准 Doxyfile 模板文件。切换到项目根目录下，运行：

```
doxygen -g
```

参数 -g 表示 生成(generate)。现在应该会出现一个名为 Doxyfile 的新文件。

**Step2 生成文档**

通过命令调用 Doxygen：

```
doxygen
```

现在应该能会有两个新文件夹：

- html/
- latex/

默认情况下，Doxygen 会同时输出 LaTeX 和 HTML 格式的文档。本文主要关注 HTML 文档。你可以在 Doxygen 官方文档的入门小节中找到关于 LaTeX 格式输出的更多信息

### 配置文件示例

```
# 程序文档输出目录

OUTPUT_DIRECTORY    =  doc/

# 程序文档语言环境

OUTPUT_LANGUAGE    = Chinese

# 如果是制作 C 程序文档，该选项必须设为 YES，否则默认生成 C++ 文档格式

OPTIMIZE_OUTPUT_FOR_C  = YES

# 对于使用 typedef 定义的结构体、枚举、联合等数据类型，只按照 typedef 定义的类型名进行文档化

TYPEDEF_HIDES_STRUCT   = YES

# 在 C++ 程序文档中，该值可以设置为 NO，而在 C 程序文档中，由于 C 语言没有所谓的域/名字空间这样的概念，所以此处设置为 YES

HIDE_SCOPE_NAMES        = YES

# 让 doxygen 静悄悄地为你生成文档，只有出现警告或错误时，才在终端输出提示信息

QUIET   = YES

# 只对头文件中的文档化信息生成程序文档

FILE_PATTERNS          = *.h

# 递归遍历当前目录的子目录，寻找被文档化的程序源文件

RECURSIVE              = YES

# 示例程序目录

EXAMPLE_PATH           = example/

# 示例程序的头文档 (.h 文件) 与实现文档 (.c 文件) 都作为程序文档化对象

EXAMPLE_PATTERNS       = *.c \

                               *.h

# 递归遍历示例程序目录的子目录，寻找被文档化的程序源文件

EXAMPLE_RECURSIVE      = YES

# 允许程序文档中显示本文档化的函数相互调用关系
REFERENCED_BY_RELATION = YES

REFERENCES_RELATION    = YES

REFERENCES_LINK_SOURCE = YES

# 不生成 latex 格式的程序文档

GENERATE_LATEX         = NO

# 在程序文档中允许以图例形式显示函数调用关系，前提是你已经安装了 graphviz 软件包

HAVE_DOT               = YES

CALL_GRAPH            = YES

CALLER_GRAPH        = YES

#让doxygen从配置文件所在的文件夹开始，递归地搜索所有的子目录及源文件

RECURSIVE = YES  

#在最后生成的文档中，把所有的源代码包含在其中

SOURCE BROWSER = YES

$这会在HTML文档中，添加一个侧边栏，并以树状结构显示包、类、接口等的关系

GENERATE TREEVIEW ＝ ALL


EXTRACT_ALL：这个标记告诉 doxygen，即使各个类或函数没有文档，也要提取信息。必须把这个标记设置为 Yes。

EXTRACT_PRIVATE：把这个标记设置为 Yes。否则，文档不包含类的私有数据成员。

EXTRACT_STATIC：把这个标记设置为 Yes。否则，文档不包含文件的静态成员（函数和变量）。
```

### 注释规则

**项目注释**

```
/**@mainpage  
* @section   项目详细描述
*
* @section   功能描述  
* 
* @section   用法描述 
* 

**********************************************************************************
*/
```

项目注释也可以使用markdown文件作为主页，通过指定md文件路径来配置。

```USE_MDFILE_AS_MAINPAGE = doc/readme.md```

若markdown文件里包含图片，可能会出现图片无法显示的情况，这个时候需先检查图片路径是否正确，同时还需要在doxyfile中添加图片路径方可显示。

```IMAGE_PATH             = ./doc/images``` 

**文件注释**

```
/**
 * @file 文件名
 * @brief 简介
 * @details 细节
 * @mainpage 工程概览
 * @author 作者
 * @version 版本号
 * @date 年-月-日
 */
```

**全局常量/变量/宏定义/结构体定义/类定义的注释**

```
/// 缓存大小
#define BUFSIZ 1024*4
#define BUFSIZ 1024*4 ///< 缓存大小
```

**函数注释**

```
/**
 * @brief 函数简介
 *
 * @param 形参 参数说明
 * @param 形参 参数说明
 * @return 返回值说明
*/
```