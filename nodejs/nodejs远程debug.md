1:在服务端用inspect模式运行nodejs,会出现一串uuid

```sh
node --inspect=0.0.0.0 app.js
node --inspect-brk=0.0.0.0 app.js //第一行就停下来,等待调试
Debugger listening on ws://0.0.0.0:9229/75c9c1f2-fd0a-4239-90a0-03f63cd179eb
```

2: 修改uuid,在chrome地址栏里输入,就可以进入远程debug了
chrome-devtools://devtools/bundled/inspector.html?experiments=true&v8only=true&ws=127.0.0.1:9229/75c9c1f2-fd0a-4239-90a0-03f63cd179eb