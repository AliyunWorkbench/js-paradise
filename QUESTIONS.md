## html

1. HTML5 和 CSS3 有哪些

https://www.cnblogs.com/star91/p/5659134.html

2.

## css

1. BFC

- [史上最全面、最透彻的 BFC 原理剖析](https://github.com/zuopf769/notebook/blob/master/fe/BFC%E5%8E%9F%E7%90%86%E5%89%96%E6%9E%90/README.md)
- [学习 BFC (Block Formatting Context)](https://juejin.im/post/59b73d5bf265da064618731d)

2. CSS 清浮动处理

- [CSS 清浮动处理（Clear 与 BFC）](https://www.cnblogs.com/dolphinX/p/3508869.html)

3. 移动端 1px

- [移动端 1px 解决方案](https://juejin.im/post/5d19b729f265da1bb2774865)
- [移动端 1px 像素问题及解决办法](https://www.jianshu.com/p/31f8907637a6)
- [吃透移动端 1px ｜从基本原理到开源解决方案](https://juejin.im/post/5df3053ce51d45583d425ada)
- [CSS3 border-image 彻底明白](https://segmentfault.com/a/1190000010969367)

首先要了解虚拟像素（css 像素）、物理像素（设备像素）、逻辑像素 和设备像素比(dpr)的概念，然后要了解我们设计师的设计稿一般都是 750\*1334，这个设计稿上的 1px 是 css 像素, 而设计师要的效果是 1px 的物理像素，所以需要除于设备像素比(dpr)，比如 iPhone6 的 dpr 是 2，就 1/2

dpr 的意思可以这样理解，1css 像素要用 dpr 个物理像素来表示

4. 圣杯布局和双飞翼布局

- [圣杯布局和双飞翼布局的理解与思考](https://www.jianshu.com/p/81ef7e7094e8)

5. CSS 画扇形

- [css 画扇形的几种实现方式](https://blog.csdn.net/young_Emily/article/details/80091667)
- [你真的理解 CSS 的 linear-gradient？](https://www.w3cplus.com/css3/do-you-really-understand-css-linear-gradients.html)

## js

### 表达式和语句

表达式是由运算符构成，并运算产生结果的语法结构。每个表达式都会产生一个值，它可以放在任何需要一个值的地方

语句则是由“；（分号）”分隔的句子或命令。如果在表达式后面加上一个“；”分隔符，这就被称为“表达式语句”。

1. getcomputedstyle 和 style 的区别

```
1.只读与可写
  getComputedStyle方法是只读的，只能获取样式，不能设置；而element.style能读能写，能屈能伸。
2.获取的对象范围
  getComputedStyle方法获取的是最终应用在元素上的所有CSS属性对象（即使没有CSS代码，也会把默认的祖宗八代都显示出来）；
  而element.style只能获取元素style属性中的CSS样式。
  因此对于一个光秃秃的元素<p>，getComputedStyle方法返回对象中length属性值（如果有）就是190+(据我测试FF:192, IE9:195, Chrome:253, 不同环境结果可能有差异),
  而element.style就是0。
3.作用
  getComputedStyle方法有一个很重要的，类似css()方法没有的功能——获取伪类元素样式
4.兼容性
  getComputedStyle方法IE6~8是不支持的

```

2. 判断数据类型的方法

- typeof

```
console.log(typeof 2);               // number
console.log(typeof true);            // boolean
console.log(typeof 'str');           // string
console.log(typeof undefined);       // undefined
console.log(typeof []);              // object
console.log(typeof {});              // object
console.log(typeof function(){});    // function
console.log(typeof null);            // object

```

- instanceof

```
console.log(2 instanceof Number);                    // false
console.log(true instanceof Boolean);                // false
console.log('str' instanceof String);                // false
console.log([] instanceof Array);                    // true
console.log(function(){} instanceof Function);       // true
console.log({} instanceof Object);                   // true
```

- Object.prototype.toString.call()

```
var toString = Object.prototype.toString;

console.log(toString.call(2));                      //[object Number]
console.log(toString.call(true));                   //[object Boolean]
console.log(toString.call('str'));                  //[object String]
console.log(toString.call([]));                     //[object Array]
console.log(toString.call(function(){}));           //[object Function]
console.log(toString.call({}));                     //[object Object]
console.log(toString.call(undefined));              //[object Undefined]
console.log(toString.call(null));                   //[object Null]
```

3. 变量提升&作用域

- [图解作用域及闭包](https://juejin.im/post/5af109426fb9a07aa047f1c7)
- [深入理解 JavaScript, 从作用域与作用域链开始](https://juejin.im/post/5d13a5fce51d455a694f9560)
- [深入理解 JavaScript 作用域和作用域链](https://juejin.im/post/5c8290455188257e5d0ec64f)

4. 闭包

- [图解 JS 闭包形成的原因](https://segmentfault.com/a/1190000011504517)

5. this

- [嗨，你真的懂 this 吗？](https://juejin.im/post/5c96d0c751882511c832ff7b)
- [Js 中 this 的用法](http://xieyufei.com/2016/09/18/Explain-Js-This.html)
- [通过运行机制看 this 绑定 、作用域、作用域链和闭包](https://juejin.im/post/5dde27615188256ebd1618fb)
- [JavaScript this 的六道坎](https://blog.crimx.com/2016/05/12/understanding-this/)

```
1. 普通函数的调用：this指向window(浏览器环境)。
2. 对象方法的调用：this指向调用对象。（隐式绑定）
3. 构造函数：this指向构造函数实例。
4. apply、call、bind：this指向绑定值。（显示绑定）
5. 箭头函数this：this指向外层第一个普通函数调用的this。（默认绑定）(对于箭头函数，只要看它在哪里创建)


优先级
1. 函数是否存在new绑定调用：如果是的话this绑定到新创建的对象上。
2. 函数是否通过apply、call、bind显示绑定：如果是，this绑定到指定对象上。
3. 函数是否在对象方法隐式调用：如果是的话，this绑定到调用对象。
4. 如果上面三条都不满足的话：在严格模型下，this绑定到undefined，在非严格模式下，this绑定到全局对象上。

```

5.0 new 执行的操作

```
1. 创建一个全新的对象。
2. 这个新对象会被执行 [[Prototype]] 连接。
3. 这个新对象会绑定到函数调用的 this。
4. 如果函数没有返回其他对象，那么 new 表达式中的函数调用会自动返回这个新对象。
```

手动实现 new

```
function New(Constructor, ...args){
    let obj = {};   // 创建一个新对象
    Object.setPrototypeOf(obj, Constructor.prototype);  // 连接新对象与函数的原型
    return Constructor.apply(obj, args) || obj;   // 执行函数，改变 this 指向新的对象
}

function Foo(a){
    this.a = a;
}

New(Foo, 1);  // Foo { a: 1 }

```

```
function _new() {
    let target = {}; //创建的新对象
    //第一个参数是构造函数
    let [constructor, ...args] = [...arguments];
    //执行[[原型]]连接;target 是 constructor 的实例
    target.__proto__ = constructor.prototype;
    //执行构造函数，将属性或方法添加到创建的空对象上
    let result = constructor.apply(target, args);
    if (result && (typeof (result) == "object" || typeof (result) == "function")) {
        //如果构造函数执行的结构返回的是一个对象，那么返回这个对象
        return result;
    }
    //如果构造函数返回的不是一个对象，返回创建的新对象
    return target;
}

```

### Object.create

- [详解 Object.create(null)](https://juejin.im/post/5acd8ced6fb9a028d444ee4e)

6. 理解 constructor、prototype、**proto**和原型链

- [用自己的方式（图）理解 constructor、prototype、**proto**和原型链](https://juejin.im/post/5cc99fdfe51d453b440236c3)

```
任何一个对象都有constructor
对象和函数的constructor都是Function

```

7. let const var

- [一道面试题引发的“血案”](https://juejin.im/post/5bab1d4ae51d450e4d2feb7a)

8. setTimeout 和 setInterval 和 requestAnimationFrame

- [关于 setInterval 与 setTimeout 作用域问题](https://my.oschina.net/huskydog/blog/1553720)
- [注意点——setTimeout、setInterval 使用](https://juejin.im/post/59cf06745188253fbe466f78)
- [你真的了解 setTimeout 和 setInterval 吗？](http://qingbob.com/difference-between-settimeout-setinterval/)
- [关于 setTimeout](https://juejin.im/post/5aa4c47af265da239866e236)
- [深度解密 setTimeout 和 setInterval——为 setInterval 正名！](https://juejin.im/post/5c4044e1f265da614f708f7d)
- [从 setTimeout/setInterval 看 JS 线程](https://palmer.arkstack.cn/2017/12/%E4%BB%8EsetTimeout-setInterval%E7%9C%8BJS%E7%BA%BF%E7%A8%8B/?hmsr=toutiao.io&utm_medium=toutiao.io&utm_source=toutiao.io)
- [你知道的 requestAnimationFrame【从 0 到 0.1】](https://juejin.im/post/5c3ca3d76fb9a049a979f429)

9. Event Loop

- [这一次，彻底弄懂 JavaScript 执行机制](https://juejin.im/post/59e85eebf265da430d571f89)
- [JavaScript 运行机制详解：再谈 Event Loop](http://www.ruanyifeng.com/blog/2014/10/event-loop.html)
- [JavaScript 的 Event Loop 详解](https://juejin.im/post/5d21c6d56fb9a07ea4209ffc)
- [Visualizing the javascript runtime at runtime](https://github.com/latentflip/loupe)

### JSON.parse(JSON.stringify())的缺点

在 JSON.stringify()阶段

```
1.如果obj里面有时间对象，则JSON.stringify后再JSON.parse的结果，时间将只是字符串的形式，而不是对象的形式

2.如果obj里有RegExp(正则表达式的缩写)、Error对象，则序列化的结果将只得到空对象

3、如果obj里有函数，undefined，则序列化的结果会把函数或 undefined丢失

4、如果obj里有NaN、Infinity和-Infinity，则序列化的结果会变成null

5、JSON.stringify()只能序列化对象的可枚举的自有属性，例如 如果obj中的对象是有构造函数生成的， 则使用JSON.parse(JSON.stringify(obj))深拷贝后，会丢弃对象的constructor

6、如果对象中存在循环引用的情况也无法正确实现深拷贝
```

### 进程与线程

- [深入理解 Node.js 中的进程与线程](https://juejin.im/post/5d43017be51d4561f40adcf9)
- [进程与线程的一个简单解释](http://www.ruanyifeng.com/blog/2013/04/processes_and_threads.html)
- [一篇让你明白进程与线程之间的区别与联系](https://juejin.im/post/5c932660f265da612524ad6d)
- [浅析操作系统的进程、线程区别](https://blog.csdn.net/zhuoxiuwu/article/details/77850724)

### 函数式编程

- [JavaScript 函数式编程](https://juejin.im/post/5b4ac0d0f265da0fa959a785)
- [函数式编程入门教程](http://www.ruanyifeng.com/blog/2017/02/fp-tutorial.html)
- [ramda](https://github.com/ramda/ramda)
- [Ramda 函数库参考教程](http://www.ruanyifeng.com/blog/2017/03/ramda.html)

### 深拷贝与浅拷贝

- [浅拷贝与深拷贝](https://juejin.im/post/5b5dcf8351882519790c9a2e)
- [如何写出一个惊艳面试官的深拷贝?](https://juejin.im/post/5d6aa4f96fb9a06b112ad5b1)
- [一步一步实现深拷贝](https://github.com/950905/record-summary/blob/master/common/%E4%B8%80%E6%AD%A5%E4%B8%80%E6%AD%A5%E5%AE%9E%E7%8E%B0%E6%B7%B1%E6%8B%B7%E8%B4%9D.md)

### 防抖与节流

- [js 史上最精简！防抖节流（你的比我精简，算我输）](https://juejin.im/post/5da7c77a51882554c0757f46)
- [2019 面试准备 - JS 防抖与节流](https://juejin.im/post/5c87b54ce51d455f7943dddb)

### 对象与数组的遍历

- [javaScript 遍历对象、数组总结](https://www.cnblogs.com/chenyablog/p/6477866.html)
  对象的属性分为三种： 是否是自身属性 是否可以枚举 是否是 Symbol 属性
  注意：对象没有 for...of...

举个栗子

```js
var a = { a: 1 };
var b = { b: 2 };
b.__proto__ = a;
Object.defineProperty(b, "c", {
  value: 3
});
b[Symbol()] = 4;

Object.keys(b); // ["b"]  返回一个数组,包括对象自身的(不含继承的)所有可枚举属性(不含Symbol属性).

for (var i in b) {
  console.log(i, ":", b[i]);
} // b : 2 a : 1   循环遍历对象自身的和继承的可枚举属性(不含Symbol属性)

Object.getOwnPropertyNames(obj); // ["b", "c"] 返回一个数组,包含对象自身的所有属性(不含Symbol属性,但是包括不可枚举属性).
Reflect.ownKeys(b); // ["b", "c", Symbol()] 返回一个数组,包含对象自身的所有属性,不管属性名是Symbol或字符串,也不管是否可枚举.
```

### 数组去重

- [JavaScript 专题之数组去重](https://juejin.im/post/5949d85f61ff4b006c0de98b)
- [如何答一道惊艳面试官的数组去重问题？](https://mp.weixin.qq.com/s/IA41OWhKS062WzTOQ6hDAA)

### 严格模式

严格模式主要有以下限制。

```
变量必须声明后再使用
函数的参数不能有同名属性，否则报错
不能使用with语句
不能对只读属性赋值，否则报错
不能使用前缀 0 表示八进制数，否则报错
不能删除不可删除的属性，否则报错
不能删除变量delete prop，会报错，只能删除属性delete global[prop]
eval不会在它的外层作用域引入变量
eval和arguments不能被重新赋值
arguments不会自动反映函数参数的变化
不能使用arguments.callee
不能使用arguments.caller
禁止this指向全局对象
不能使用fn.caller和fn.arguments获取函数调用的堆栈
增加了保留字（比如protected、static和interface）
```

### 异常处理

- [[html] script 的 crossorigin 属性](https://www.jianshu.com/p/a45c9d089c93)

### 代码质量

- [代码整洁的 JavaScript](https://github.com/beginor/clean-code-javascript)
- [如何提升 Web 应用的代码质量](https://juejin.im/post/5b21ae895188257d5e3b9f89)

### 正则表达式

- [JS 正则表达式完整教程（略长）](https://juejin.im/post/5965943ff265da6c30653879)

## typescript

- [typescript 中文官网](https://www.tslang.cn/docs/home.html)
- [Typescript 中的 interface 和 type 到底有什么区别](https://juejin.im/post/5c2723635188252d1d34dc7d)

## vue

- [30 道 Vue 面试题，内含详细讲解（涵盖入门到精通，自测 Vue 掌握程度）](https://juejin.im/post/5d59f2a451882549be53b170)
- [Vue 3 中令人兴奋的新功能](https://juejin.im/post/5dc3cfce6fb9a04a665f100e)
- [面试官: 实现双向绑定 Proxy 比 defineproperty 优劣如何?](https://juejin.im/post/5acd0c8a6fb9a028da7cdfaf)

![vue响应式原理](https://user-gold-cdn.xitu.io/2018/4/11/162b38ab2d635662?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

### vue-cli

- [改造 vue-cli，让它更好用](https://juejin.im/post/5b7392b16fb9a009b82c05de)
- [这可能是 vue-cli 最全的解析了……](https://juejin.im/post/5b2872516fb9a00e8626e34f)
- [Vue-cli 原理分析](https://juejin.im/post/5b592db551882536e5178ce6)

### vue3

- [面试官: 实现双向绑定 Proxy 比 defineproperty 优劣如何?](https://juejin.im/post/5acd0c8a6fb9a028da7cdfaf)

### 组件间通信示例

- [EventBus （$emit / $on）](https://codesandbox.io/s/vue-bus-tms87)
- [$attrs/$listeners](https://codesandbox.io/s/vue-attrs-listeners-z5rwe)
- [provide / inject ](https://codesandbox.io/s/affectionate-matsumoto-w5l8h)

### react 组件间通信示例

- Context
- render prop
- 组合组件，提升组件层次，把组件作为 prop
- redux

## es6

- [ES6 入门教程](http://es6.ruanyifeng.com)
- [1.5 万字概括 ES6 全部特性](https://juejin.im/post/5d9bf530518825427b27639d)

### 什么叫暂时性死区

在代码块内，使用 let 命令声明变量之前，该变量都是不可用的。这在语法上，称为“暂时性死区”（temporal dead zone，简称 TDZ）。

## weex

### 源码

- [Weex 中别具匠心的 JS Framework](https://halfrost.com/weex_js_framework/)

## react

- [官网](https://zh-hans.reactjs.org/docs/getting-started.html)
- [关于 Vue 和 React 的一些对比及个人思考（上）](https://juejin.im/post/5e153e096fb9a048297390c1)
- [【React 深入】从 Mixin 到 HOC 再到 Hook](https://juejin.im/post/5cad39b3f265da03502b1c0a)

## 小程序

### taro

## webpack

- [2020 年了,再不会 webpack 敲得代码就不香了(近万字实战)](https://juejin.im/post/5de87444518825124c50cd36)
- [一步步从零开始用 webpack 搭建一个大型项目](https://juejin.im/post/5de06aa851882572d672c1ad)

## 浏览器

- [从输入 URL 到页面加载的过程？如何由一道题完善自己的前端知识体系！](https://zhuanlan.zhihu.com/p/34453198?group_id=957277540147056640)
- [从浏览器多进程到 JS 单线程，JS 运行机制最全面的一次梳理](https://juejin.im/post/5a6547d0f265da3e283a1df7)

### 页面渲染

- [你不知道的浏览器页面渲染机制](https://juejin.im/post/5ca0c0abe51d4553a942c17d)
- [浏览器页面渲染机制，你真的弄懂了吗？](https://mp.weixin.qq.com/s?__biz=MzUxMzcxMzE5Ng==&mid=2247489674)

### 缓存

- [彻底理解浏览器的缓存机制](https://juejin.im/entry/5ad86c16f265da505a77dca4)
- [浏览器缓存](https://segmentfault.com/a/1190000008377508)
- [前端静态资源缓存最优解以及 max-age 的陷阱](https://blog.csdn.net/weixin_42817899/article/details/84553595)
- [面试精选之 http 缓存](https://juejin.im/post/5b3c87386fb9a04f9a5cb037)

### 跨域与安全

- [我知道的跨域与安全](https://juejin.im/post/5a6320d56fb9a01cb64ee191)

- 跨站攻击

```
1. XSS（cross-site-scripting, 跨站脚本）攻击

解决方法： 字符串转义

2. 跨站请求伪造（CSRF）

解决方法： 1.明文传递cookie
         2. 请求一个随机字符串（只能用一次）

```

- [ajax 跨域，这应该是最全的解决方案了](https://segmentfault.com/a/1190000012469713)
- [浏览器同源政策及其规避方法](http://www.ruanyifeng.com/blog/2016/04/same-origin-policy.html)
- [跨域资源共享 CORS 详解](http://www.ruanyifeng.com/blog/2016/04/cors.html)
- 可以通过 Symbol 进行 iframe 的跨域 http://es6.ruanyifeng.com/#docs/symbol

```
iframe = document.createElement('iframe');
iframe.src = String(window.location);
document.body.appendChild(iframe);

iframe.contentWindow.Symbol.for('foo') === Symbol.for('foo')
// true
```

- 限制网站被 iframe 包裹

添加这个 http 头可以限制别人把你的网站套成它的 iframe

```
X-Frame-Options: SAMEORIGIN
```
- [JS判断页面是否被iframe及禁止页面被iframe](https://www.cnblogs.com/bella-lin/p/9266994.html)


### http

- [七层网络结构](https://blog.csdn.net/u010359398/article/details/82142449)

### 垃圾回收

- [图解 JavaScript 垃圾回收 — 现代 JavaScript 教程](https://juejin.im/post/5e0ddc24f265da5d1805ee6f)

### 架构

- [一文带你看透 Chrome 浏览器架构](https://juejin.im/post/5e11cd225188253a73288212)

## 性能优化

- [用 100 行代码提升 10 倍的性能](https://juejin.im/post/5bec223f5188250c102116b5)

## 移动端

- [吃透移动端 H5 与 Hybrid ｜实践踩坑 12 种问题汇总](https://juejin.im/post/5dfadb91e51d45584006e486)
- [前端基础知识概述 -- 移动端开发的屏幕、图像、字体与布局的兼容适配](https://juejin.im/post/5d70747cf265da03e16897c8)
- [移动前端知识总结](http://caibaojian.com/mobile-knowledge.html)

## nodejs

### npm

- [npx 使用教程](http://www.ruanyifeng.com/blog/2019/02/npx.html)

## 服务端相关

- [傻傻分不清之 Cookie、Session、Token、JWT](https://juejin.im/post/5e055d9ef265da33997a42cc)
- [图文并茂，为你揭开“单点登录“的神秘面纱](https://juejin.im/post/5e11a6e96fb9a048411a4eca)

## 算法与数据结构

- [前端该如何准备数据结构和算法？](https://juejin.im/post/5d5b307b5188253da24d3cd1)
- [js 实现排序算法（冒泡、选择、插入、二分插入、快速、希尔）](http://blog.csdn.net/charlene0824/article/details/51387165)
- [前端面试中的常见的算法问题](https://www.jackpu.com/qian-duan-mian-shi-zhong-de-chang-jian-de-suan-fa-wen-ti/)
- [图形算法（邻接矩阵）](https://juejin.im/post/5de7c053518825125d1497e2)
- [5 分钟带你领略:某跳动公司面试出镜率最高的算法之一——虚拟十叉树建模问题](https://juejin.im/post/5d7fb1e16fb9a06ac76de435)
- [【从蛋壳到满天飞】JS 数据结构解析和算法实现-集合和映射](https://juejin.im/post/5c9242926fb9a070b33c4f57)
- [聊聊面试必考-递归思想与实战](https://juejin.im/post/5d85cda3f265da03b638e918)

### 复杂度

- [算法的时间和空间复杂度，就是这么简单](https://www.toutiao.com/a6750625828465279495)

### 二叉树

- [JavaScript 二叉树深入理解](https://www.jianshu.com/p/61f75e0f549f)
- [3 分钟理解完全二叉树、平衡二叉树、二叉查找树](https://mp.weixin.qq.com/s/K_oGI2rl3epTirxkST5LVQ)

```

```

## 选择题

- [2020 年从基础到进阶，测试你有多了解 JavaScript，刷新你的知识！](https://juejin.im/post/5e1830c05188254c461313dc)

## 手写题

- [23 行代码实现一个带并发数限制的 fetch 请求函数](https://juejin.im/post/5c89d447f265da2dd37c604c)
- [字节跳动面试官：请你实现一个大文件上传和断点续传](https://juejin.im/post/5dff8a26e51d4558105420ed)

## 服务端渲染
