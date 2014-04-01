#Frequently Asked Questions

###Scrapy和BeautifulSoup或者lxml比较怎么样

[BeautifulSoup]()和[lxml]()分别是解析HTML和XML的库。Scrapy是写web爬虫的应用框架，它可以从爬取web站点并且从中提取数据。

对于提取数据（称作 selectors），Scrapy提供了一种内建的机制，但是如果你更习惯于使用BeautifulSoup(或者lxml)，你也可以很容易地使用它们。毕竟，它们只是可以被导入到解析库，可以在任何Python代码中使用。

换句话说，拿BeautifulSoup(或者lxml)和Scrapy比较就好像拿jinja2和Django比较。

###Scrapy支持哪些Python版本呢

Scrapy仅支持Python 2.7版本以下的。从Scrapy 0.20开始就不再支持Python 2.6了。

###Scrapy支持Python 3版本吗

不支持，但是未来会计划支持Python 3.3及以上版本的。现在Scrappy工作于Python 2.7。
