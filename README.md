golang爬虫实战项目

实现了 `单机版爬虫`和`分布式爬虫`

分布式爬虫中，节点之间使用jsonrpc进行通讯和调用

架构简介：
engine - 主控中心
worker - 根据链接获取网页内容
itemsaver - 将解析出来的用户数据保存到数据库中(elasticsearch)

解析器Parser - 从抓取到的对应页面中解析出指定的数据 (城市列表解析器 用户列表解析器 用户数据解析器)
redis查重   - 避免重复抓取相同的url页面

前端展示，提供了用户数据的列表显示，并提供多条件搜索功能 (使用elasticsearch搜索引擎)

注意：crawler_distributed项目中会依赖crawler项目中的部分代码，比如解析器