1.查看索引： 
db.COLLECTION_NAME.getIndexes()

2.创建索引： 
数字 1 表示按索引升序存储，-1 表示按索引降序方式存储 
1）.创建单索引 
db.COLLECTION_NAME.ensureIndex({name:1})
2）.创建复合索引 
db.COLLECTION_NAME.ensureIndex({name:1,age:1})
3）.创建唯一索引： 
db.COLLECTION_NAME.ensureIndex({name:1,age:1},{unique:true})


3.删除索引： 
1）.根据索引的 name 字段名称删除，比如如上显示删除第二个索引 
db.COLLECTION_NAME.dropIndex("name_1_age_1_unique_true") 
2）.根据创建时指定的索引的 key 删除，比如如上显示删除第二个索引 
db.COLLECTION_NAME.dropIndex({name:1,age:1}) 
3）.删除所有索引 
db.COLLECTION_NAME.dropIndexes()

