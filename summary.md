## 第一章  
### 概述  
1.ECMAScript（ES）是 JavaScript 的语法标准  
2.前端JS的组成：ECMAScript（核心语言，不可替代）；BOM--浏览器（宿主对象，可替代）；DOM--文档对象模型（宿主对象，可替代）  
3.客户端JS在浏览器运行，服务端JS在node.js中运行.二者的核心语言都是ECMAScript  
4.JS在浏览器中的实现方式是通过JS引擎（chrome通过v8）  
5.JavaScript 只能够在浏览器中执行？不是，JavaScript 除了在浏览器中运行，还可以在其他的运行环境中运行，如 node.js 环境。目前 JavaScript 的运行环境有浏览器和 node.js 环境两种  
6.JavaScript 在浏览器中是如何运行的？浏览器下载 JavaScript 脚本文件后，由浏览器JavaScript 引擎解释执行。  
7.ECMAScript的版本：ES5（2009年12月发布）、ES6（2015年06月发布）、ES7（2016年06月发布）、ES8（2017年06月发布）、ES9（2018年06月发布）、ES10（2019年06月发布）  
8.JS语言特点：直译式脚本语言；弱类型、动态类型语言；  
### 数据类型以及存储转换  
1.ES5 数据类型（6种）及其划分（2类）：基本（原始）类型（Number、String、Boolean、Null、Undefined）；引用（对象）类型（Object（Array、Function、Date、String等））  
2.typeof：返回一个字符串，表示未经计算的操作数的类型。如a为number，b为string a+b后，a的类型仍为number。typeof operand  或者  typeof (operand)，其中括号可选  
3.函数如果没有return，则返回值类型为undefined  


.等于号的两种不同用法：①一个单独的等于号，用于为变量赋值；②三个连续的等号，用于比较两个值  
.

