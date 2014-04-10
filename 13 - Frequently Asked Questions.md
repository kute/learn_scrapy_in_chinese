#Frequently Asked Questions

###Scrapy和BeautifulSoup或者lxml比较怎么样

[BeautifulSoup]()和[lxml]()分别是解析HTML和XML的库。Scrapy是写web爬虫的应用框架，它可以从爬取web站点并且从中提取数据。

对于提取数据（称作 selectors），Scrapy提供了一种内建的机制，但是如果你更习惯于使用BeautifulSoup(或者lxml)，你也可以很容易地使用它们。毕竟，它们只是可以被导入到解析库，可以在任何Python代码中使用。

换句话说，拿BeautifulSoup(或者lxml)和Scrapy比较就好像拿jinja2和Django比较。

###Scrapy支持哪些Python版本呢

Scrapy仅支持Python 2.7版本以下的。从Scrapy 0.20开始就不再支持Python 2.6了。

###Scrapy支持Python 3版本吗

不支持，但是未来会计划支持Python 3.3及以上版本的。现在Scrappy工作于Python 2.7。

###Did Scrapy “steal” X from Django?

或许我们并不喜欢那个词。我们认为[Django]()是一个庞大的开源项目，是可以遵循的范例，因此我们把它作为Scrapy的核心。

我们相信，如果有些东西已经做的很好，那就没必要去重复发明它。这个理念，除了成为开源和免费软件的奠基之一，不仅仅应用在软件上，而且也应用在文档，生产，政策等等。因此，我们并不独自去解决每个问题，我们选择从这些已经把类似问题处理的很好的项目中汲取思路，这样我们就专注于我们需要去解决的真正问题。

如果Scrapy服务成为了其他项目的核心，我们是相当自豪的。
Feel free to steal from us!

###Scrapy是否支持HTTP代理

是的。从Scrapy 0.8以后就提供了HTTP代理支持，可以通过HTTP Proxy downloader middleware实现。请看[HttpProxyMiddleware]().

###怎样将不同页面的属性抓取在同一个item中

请看[Passing additional data to callback functions]().

###Scrapy crashes with: ImportError: No module named win32api

由于[this Twisted bug]()你需要安装[pywin32]().

###怎样在spider中模仿一个用户登录

看[Using FormRequest.from_response() to simulate a user login]()

###Scrapy抓取是广度优先还是深度优先

Scrapy默认是使用[LIFO]()队列来存储等待处理的请求，这就意味着Scrapy是用的是[DFO order]()。这个顺序在大多数案例中是很方便的。如果你想使用[BFO order]()，你可以通过设置如下setting来实现：

    DEPTH_PRIORITY = 1
    SCHEDULER_DISK_QUEUE = 'scrapy.squeue.PickleFifoDiskQueue'
    SCHEDULER_MEMORY_QUEUE = 'scrapy.squeue.FifoMemoryQueue'

###我的Scrapy crawler有内存泄漏，怎么办

看[Debugging memory leaks]()。

而且Python有个内建的内存泄漏问题在[Leaks without leaks]().

###怎样使Scrapy花费较少的内存

看前一个问题

###我能在spiders中使用Basic HTTP Authentication吗

是的，看[HttpAuthMiddleware]()

###为什么Scrapy下载页使用的是英语而不是我本地的语言

尝试通过覆盖[DEFAULT_REQUEST_HEADERS]设置来改变默认的[Accept-Language ]()请求报头。

###我可以在哪找到一些Scrapy的项目例子

看[Example]()

###在不创建项目的情况下，我可以运行一个spider吗

是的，你可以通过[runspider]()命令。例如，你在一个 my_spider.py文件中写了一个spider，你可以这样运行：

    scrapy runspider my_spider.py
    
更多信息看[runspider]()
