
### 1. 修改启动参数/etc/mongod.conf：

```bash
dbPath: /data/mongodb/mongodb  //修改数据库文件夹地址

port: 8808      //端口

```

### 2. 修改数据库文件夹拥有者为mongodb

```bash
sudo chown mongodb:mongodb /data/mongodb/mongodb -R
```


### 3. 创建管理员：

```bash
use admin
db.createUser(
  {
    user: "myUserAdmin",
    pwd: "abc123",
    roles: [ { role: "userAdminAnyDatabase", db: "admin" } ]
  }
)

```

### 4. 修改启动参数/etc/mongod.conf,加上auth：

```bash
security:
  authorization: enabled
```

### 5. 重启mongodb：

```bash
sudo service mongod restart
sudo service mongod status  //查看启动状态
```

### 6. 用管理员帐号登录：

```bash
mongo --port 8808 -u "myUserAdmin" -p "abc123" --authenticationDatabase "admin"
```
或者
```bash
mongo --port 8808

use admin
db.auth("myUserAdmin", "abc123" )
```

### 7. 为生产库数据库创建专门的用户：用户myTester在db test里有读写权限, db reporting里只有读权限
```bash
use test
db.createUser(
  {
    user: "myTester",
    pwd: "xyz123",
    roles: [ { role: "readWrite", db: "test" },
             { role: "read", db: "reporting" } ]
  }
)

```

### 8. 获取用户权限：

```bash
use reporting
db.getUser("myTester")

```

### 9. 修改用户权限：
撤销用户myTester在db accounts里的读写权限
```bash

db.revokeRolesFromUser(
    "myTester",
    [
      { role: "readWrite", db: "accounts" }
    ]
)
```
给用户myTester在db accounts里添加只读权限
```bash

db.grantRolesToUser(
    "myTester",
    [
      { role: "read", db: "accounts" }
    ]
)

```