参考文档： https://www.cnblogs.com/zhang-ke/p/7804007.html

一）语句分析工具explain()
db.getCollection('orders').explain("executionStats").find({"category": "WECHAT_BOOK", "organization._id": "598325700002f49b90e03"}).sort({created: -1}).limit(10)

1) executionStats
executionTimeMillis是执行时间
nReturned、totalKeysExamined、totalDocsExamined分别代表本次查询返回数量，索引扫描数量，文档扫描数量
最理想的情况是nReturned和后两个参数的值相近，则扫描速度最快
nReturned=totalKeysExamined=totalDocsExamined

二) 索引
索引颗粒越小越好，即索引列重复数据越少越好，所以，我们在建立索引时要尽量将数据颗粒小的列放在索引左侧，以保证索引发挥最大的作用