redis
docker run -p 6379:6379 -d redis

mysql
docker run -p 3306:3306 -e MYSQL_ROOT_PASSWORD=123456 -d mysql

错误：
```sh
Client does not support authentication protocol requested by server; consider upgrading MySQL client
```
先登录：
```sh
mysql -u root -p
```
#接着输入你的密码
解决：
```sh
ALTER USER 'root'@'%' IDENTIFIED WITH mysql_native_password BY '你的密码';
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY '你的密码';
SELECT plugin FROM mysql.user WHERE User = 'root';
```
