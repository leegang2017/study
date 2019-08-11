

开发的时候直接在 ali-rds 的代码里加了个 console.log,可以调试sql

// ali-rds/lib/operator  line 47
proto.query = function* (sql, values) {
  // query(sql, values)
  if (arguments.length >= 2) {
    sql = this.format(sql, values);
  }
  debug('query %j', sql);
  console.log('\nsql: ', sql, '\n')
 // ...
};