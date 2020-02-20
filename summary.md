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
#### 数据类型
1.ES5 数据类型（6种）及其划分（2类）：基本（原始）类型（Number、String、Boolean、Null、Undefined）；引用（对象）类型（Object（Array、Function、Date、String等））  
2.typeof：返回一个字符串，表示未经计算的操作数的类型。如a为number，b为string a+b后，a的类型仍为number。typeof operand  或者  typeof (operand)，其中括号可选  
3.函数如果没有return，则返回值类型为undefined  
#### 变量与内存  
1.一般来说，系统会划分出两种不同的内存空间：  
①栈内存（stack）：存储的值大小固定；由系统自动分配内存空间；空间小，运行效率高  
②堆内存（heap）：存储的值大小不定，可动态调整；由程序员通过代码进行分配；空间大，运行效率相对较低  
2.基本类型的变量是存放在栈区的，基本类型的值不可变（如：var a="abc"; a.toUpperCase(); console.log(a);//仍为"abc")；基本类型的值直接访问（运行速率快）；基本类型复制---相互独立互不影响  
引用类型的值是同时保存在栈内存和堆内存中的对象，值可变。如 【var person = {name:'Lily'}; 其中堆区存放的是（具体值）该对象{name:'Lily'}，栈区存放的是变量person在堆区的地址 】；引用类型的值通过引用访问，不能直接访问（运行速率慢）  
3.基本数据类型与引用类型的比较：值类型是判断变量的值是否相等（值比较）；引用类型是判断所指向的内存空间（地址）是否相同（引用比较）  
4.ECMAScript 中所有函数的参数都是按值来传递的  
5.基本类型值：把变量里的数据值传递给参数，之后参数和变量互不影响。  
引用类型值：把对象的引用（地址）值传递给参数，参数和对象都指向同一个对象，相互影响。  
### 类型转换  
1.隐式类型转换：通常是某些操作的副作用，不易看出  
2.显示类型转换：可以在代码中明显看出  
3.规则：  
①转为Number：undefined-->NaN;null-->0; 强制转为number：parseInt()、parseFloat()、Number()  
NaN(Not a Number)NaN!=NaN；console.log( typeof  NaN);//number  
isNaN( ) 函数用来检测参数是否为 NaN 值，参数是 "NaN" 时返回 true，否则返回 false  
布尔型a转换为数值用a*/1;若a为undefined，转换为布尔，为！！a  
②转为string：直接加单引号；强制转换：String（）  
“+”运算符左右两侧有字符串时为拼接运算符  
运算符等级相同时，从左往右计算（var a=1; var b="2"; var c=3;则a+c+b=42）  
③转换为Boolean：undefined，null，NaN,"" 均是false；强制转换：Boolean（）  
逻辑运算符会将数据类型转换为布尔类型之后再做运算  



.等于号的两种不同用法：①一个单独的等于号，用于为变量赋值；②三个连续的等号，用于比较两个值  
.

