# es6 模块

* 模块入门

    模块（ module ），基本意思就是把一个大程序，切分成多个文件。这样，说白了，一个文件就是一个模块。但是，在 ES6 编程领域，模块有自己的一些固定的使用语法。

*********

##ES6 模块

* react 写代码的时候要用 ES6 模块。

* es6 module 基本语法如下：

```
export // (命名导出,默认导出)
import // 导入v

```

### ES6 模块到底帮我们解决什么问题

ES6 模块的引入，基于的现实是当前 Web 项目变得复杂了，所以 JS 文件会切分成 不同的多个文件，这样，没有模块之前，我们是使用 <script> 标签来导入多个 js 文件，但是，如果一个 html 文件中有几十个 script 标签来加载 js 文件，那么造成 的问题就是：

* 会发出多个 http 请求，影响页面加载速度
* 各个 JS 文件之间的依赖关系混乱，给项目管理带来了困难
于是 ES6 模块就是我们的救星。

********

### 模块默认隔离所有内容

隔离：意思就是如果我在当前模块中，声明一个变量或者函数，那么默认其他文件（模块）中是访问不到的。

比如我们有这样的程序

```
class Person {
  sayHello(){
    console.log('hello');
  }
}
let i = 1;

let peter = new Person;
peter.sayHello();
console.log(i);

```
****
是这样，一个文件中我们定义一个变量（或者一个类，函数），那么它的作用范围一般 就是在整个文件内可以用了，这样的好处是使用方便，但是，当程序写大之后，变量名 冲突就会带来调试困难。针对这个问题，ES6 模块的默认行为是隔离，一个变量一旦 移动到模块中，那么即使我们导入模块文件，那么默认情况下，这个变量也不能在模块之外 的位置被访问到。

既然模块中的变量，默认是隔离的，那么就需要我们明文的去进行变量的导出和导入。

****

#### 导出方式

有两种形式：

* 第一种叫做默认导出 。用 export default Person; 。对应的导入方式是 import Person from './Person' 。默认导出方式，在一个模块中，只能用一次，同时一次只能导出一个变量。

* 另一种形式叫做命名导出 。如果我们想要一次导出多个变量，那就 export { Person，i};，对应的导入方式是 import { Person, i} from ./Person ，

* 理解了导入导出方式，也就掌握了 ES6 模块。

* 运行环境

import/export 是 ES6 新关键字。普通浏览器包括 nodejs 都还不支持。所以代码未来我们需要到 create-react-app 环境中去使用。
