1:在服务端用inspect模式运行nodejs,会出现一串uuid

```sh
node --inspect=0.0.0.0 app.js
node --inspect-brk=0.0.0.0 app.js //第一行就停下来,等待调试
Debugger listening on ws://0.0.0.0:9229/75c9c1f2-fd0a-4239-90a0-03f63cd179eb
```

2: 修改uuid,在chrome地址栏里输入,就可以进入远程debug了
chrome-devtools://devtools/bundled/inspector.html?experiments=true&v8only=true&ws=127.0.0.1:9229/75c9c1f2-fd0a-4239-90a0-03f63cd179eb

3: 忘了写 --inspect 怎么办？

首先，正常启动脚本
```sh
node app.js
```
然后，在另一个命令行窗口，查找上面脚本的进程号。

```sh
ps ax | grep app.js 

30464 pts/11   Sl+    0:00 node app.js
30541 pts/12   S+     0:00 grep app.js
```
上面命令中，app.js的进程号是30464。

接着，运行下面的命令。
```sh
node -e 'process._debugProcess(30464)'
```
上面命令会建立进程 30464 与调试工具的连接，然后就可以打开调试工具了。

还有一种方法，就是向脚本进程发送 SIGUSR1 信号，也可以建立调试连接。
```sh
kill -SIGUSR1 30464
```


