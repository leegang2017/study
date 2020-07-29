
### 什么是nodejs
简单的说 Node.js 就是运行在服务端的 JavaScript。
Node.js 是一个基于Chrome JavaScript 运行时建立的一个平台。
Node.js是一个事件驱动I/O服务端JavaScript环境，基于Google的V8引擎，V8引擎执行Javascript的速度非常快，性能非常好
- npm
- package.json

### nodejs可以干什么
目前，Node.js在大部分领域都占有一席之地，尤其是I/O密集型的
在web前端，h5app，小程序，后端，桌面应用。。。

### 怎么学习
- 用好github
- 用好chrome
Node.js用的就是Google的V8引擎，所以语法绝大多是通用的，看文章的时候，可以在console里面就敲代码尝试
- 多读代码，多写代码

### 1) 安装
- 使用 nvs 管理本地 Node 版本
https://www.yuque.com/egg/nodejs/nvs
```node
nvs ls #列出所有已经安装的node版本
nrm add lts  #安装最新的lts版本
```

- 用nrm一键切换npm源
```node
npm i -g nrm

nrm ls #列出所有的源
nrm use taobao  #使用taobao源
```
- IDE推荐用vscode

### 2) let和const
- 不存在变量提升
```node
// var 的情况
console.log(foo); // 输出undefined
var foo = 2;

// let 的情况
console.log(bar); // 报错ReferenceError
let bar = 2;
```

- 块级作用域
### 2) 变量的解构赋值 *****
- 数组的解构赋值
```node
let [a, b, c] = [1, 2, 3];
```
- 对象的解构赋值
```node
const obj = { foo: 'aaa', bar: 'bbb' };
let { foo, bar } = obj;
```
- 函数参数的解构赋值
```node
[[1, 2], [3, 4]].map(([a, b]) => a + b);
```
- 默认值
```node
[1, undefined, 3].map((x = 'yes') => x);

function move({x = 0, y = 0} = {}) {
  return [x, y];
}

move({x: 3, y: 8}); // [3, 8]
```
### 模板字符串
```node
console.log('Hello,\n'+ name + ' greeting');
console.log(`Hello,
 ${name} greeting`);
```
### 函数的扩展
- 函数参数的默认值
```node
function log(x, y = 'World') {
  console.log(x, y);
}

log('Hello') // Hello World
log('Hello', 'China') // Hello China
log('Hello', '') // Hello
```

- 与解构赋值默认值结合使用
```node
function foo({x, y = 5} = {}) {
  console.log(x, y);
}

foo() // undefined 5
```
- rest 参数
```node
function add(name, ...values) {
  let sum = 0;

  for (var val of values) {
    sum += val;
  }
  console.log(name, sum)
}

add('lee', 2, 5, 3) // lee 10
```
### 箭头函数
```node
var f = v => v;

// 等同于
var f = function (v) {
  return v;
};
```
使用注意点
- 函数体内的this对象，就是定义时所在的对象，而不是使用时所在的对象。

- 不可以当作构造函数，也就是说，不可以使用new命令，否则会抛出一个错误。

- 不可以使用arguments对象，该对象在函数体内不存在。如果要用，可以用 rest 参数代替。

### 尾调用优化
尾调用（Tail Call）是函数式编程的一个重要概念，本身非常简单，一句话就能说清楚，就是指某个函数的最后一步是调用另一个函数。
```node
function f(x){
  return g(x);
}
```
### 数组的扩展
- 扩展运算符
```node
console.log(...[1, 2, 3])
// 1 2 3

console.log(1, ...[2, 3, 4], 5)
// 1 2 3 4 5
```
- 复制数组

es5
```node
const a1 = [1, 2];
const a2 = a1.concat();
```
es6
```node
const a1 = [1, 2];
// 写法一
const a2 = [...a1];
// 写法二
const [...a2] = a1;
```

- 合并数组
```node
const arr1 = ['a', 'b'];
const arr2 = ['c'];
const arr3 = ['d', 'e'];

// ES5 的合并数组
arr1.concat(arr2, arr3);
// [ 'a', 'b', 'c', 'd', 'e' ]

// ES6 的合并数组
[...arr1, ...arr2, ...arr3]
// [ 'a', 'b', 'c', 'd', 'e' ]
```

- 数组实例的 flat()，flatMap()
```node
[1, 2, [3, 4]].flat()
// [1, 2, 3, 4]
```
```node
// 相当于 [2, 3, 4].map((x) => [x, x * 2]).flat()
[2, 3, 4].flatMap((x) => [x, x * 2])
// [2, 4, 3, 6, 4, 8]
```

### 对象的扩展
- 属性的简洁表示法
```node
const foo = 'bar';
const baz = {foo};
baz // {foo: "bar"}

// 等同于
const baz = {foo: foo};
```

- 属性名表达式
```node
let propKey = 'foo';

let obj = {
  [propKey]: true,
  ['a' + 'bc']: 123
};
```

- 对象的扩展运算符
```node
let { x, y, ...z } = { x: 1, y: 2, a: 3, b: 4 };
x // 1
y // 2
z // { a: 3, b: 4 }
```
拷贝对象
```node
let z = { a: 3, b: 4 };
let n = { ...z, ...{ x: 1, y: 2 } };
n // { a: 3, b: 4, x: 1, y: 2 }
```

### Promise 对象
- Promise 的含义
Promise 是异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理和更强大。它由社区最早提出和实现，ES6 将其写进了语言标准，统一了用法，原生提供了Promise对象。

有三种状态：pending（进行中）、fulfilled（已成功）和rejected（已失败）

- 基本用法
```node
const promise = new Promise((resolve, reject) => {
  // ... some code
  setTimeout(()=> {
    console.log("1");
    resolve(1000);
  }, 1000)

//  if (true){
//    resolve(value);
//  } else {
//    reject(error);
//  }
});

promise.then((value) =>{
  console.log(value);
}, function(error) {
  // failure
});
```
- Promise.all()
```node
const promises = [2, 3, 5, 7, 11, 13].map(function (id) {
  return getJSON('/post/' + id + ".json");
});

Promise.all(promises).then(function (posts) {
  // ...
}).catch(function(reason){
  // ...
});
```

### async 函数
- 含义
ES2017 标准引入了 async 函数，使得异步操作变得更加方便。
async函数返回一个 Promise 对象，可以使用then方法添加回调函数。当函数执行的时候，一旦遇到await就会先返回，等到异步操作完成，再接着执行函数体内后面的语句。
```node
function timeout(ms) {
  return new Promise((resolve) => {
    setTimeout(() => resolve(ms*10), ms);
  });
}

const promises = [2, 3, 5, 7, 11, 13].map(function (id) {
  return getJSON('/post/' + id + ".json");
});



async function asyncPrint(value, ms) {
  const result = await timeout(ms);
  const datas = await Promise.all(promises);
  console.log("get await value", result);
  console.log(value);
}

asyncPrint('hello world', 500);
```

## ref
  * [ECMAScript 6 入门](http://es6.ruanyifeng.com/)
  * [nodejs 文档](http://nodejs.cn/api/)
  * [nodejs 教程](https://www.runoob.com/nodejs)
