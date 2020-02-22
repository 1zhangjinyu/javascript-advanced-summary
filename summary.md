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
1. ES5 数据类型（6种）及其划分（2类）：基本（原始）类型（Number、String、Boolean、Null、Undefined）；引用（对象）类型（Object（Array、Function、Date、String等））  
2. typeof：返回一个字符串，表示未经计算的操作数的类型。如a为number，b为string a+b后，a的类型仍为number。typeof operand  或者  typeof (operand)，其中括号可选。操作数如果是函数，返回object；如果是undefined，返回‘undefined’；  
instanceof用于对象。如果value是一个通过Constr构造器创建的对象，则返回true
3. 函数如果没有return，则返回值类型为undefined  
4. JavaScript 有七种内置类型：  
• 空值（null） • 未定义（undefined） • 布尔值（ boolean） • 数字（number） • 字符串（string） • 对象（object） • 符号（symbol，ES6 中新增） 除对象之外，其他统称为“基本类型”。   
5. typeof null === "object"; // true  
6. 数组也是对象。  
7. JavaScript 中的变量是没有类型的，只有值才有。变量可以随时持有任何类型的值。  
8. 变量在未持有值的时候为 undefined。此时 typeof 返回 "undefined"；还没有在作用域中声明 过的变量，是 undeclared 的。undefined 是值的一种。undeclared 则表示变量还没有被声明过  

#### 类型转换  
1. 隐式类型转换：通常是某些操作的副作用，不易看出  
2. 显示类型转换：可以在代码中明显看出  
3. 规则：  
①转为Number：undefined-->NaN;null-->0; 强制转为number：parseInt()、parseFloat()、Number()  
NaN(Not a Number)NaN!=NaN；console.log( typeof  NaN);//number  
isNaN( ) 函数用来检测参数是否为 NaN 值，参数是 "NaN" 时返回 true，否则返回 false  
布尔型a转换为数值用a*/1;若a为undefined，转换为布尔，为！！a  
②转为string：直接加单引号；强制转换：String（）  
“+”运算符左右两侧有字符串时为拼接运算符  
运算符等级相同时，从左往右计算（var a=1; var b="2"; var c=3;则a+c+b=42）  
③转换为Boolean：undefined，null，NaN,"" 均是false；强制转换：Boolean（）  
逻辑运算符会将数据类型转换为布尔类型之后再做运算  
#### 变量与内存  
1. 一般来说，系统会划分出两种不同的内存空间：  
①栈内存（stack）：存储的值大小固定；由系统自动分配内存空间；空间小，运行效率高  
②堆内存（heap）：存储的值大小不定，可动态调整；由程序员通过代码进行分配；空间大，运行效率相对较低  
2. 基本类型的变量是存放在栈区的，基本类型的值不可变（如：var a="abc"; a.toUpperCase(); console.log(a);//仍为"abc")；基本类型的值直接访问（运行速率快）；基本类型复制---相互独立互不影响  
引用类型的值是同时保存在栈内存和堆内存中的对象，值可变。如 【var person = {name:'Lily'}; 其中堆区存放的是（具体值）该对象{name:'Lily'}，栈区存放的是变量person在堆区的地址 】；引用类型的值通过引用访问，不能直接访问（运行速率慢）  
3. 基本数据类型与引用类型的比较：值类型是判断变量的值是否相等（值比较）；引用类型是判断所指向的内存空间（地址）是否相同（引用比较）  
4. ECMAScript 中所有函数的参数都是按值来传递的  
5. 基本类型值：把变量里的数据值传递给参数，之后参数和变量互不影响。  
引用类型值：把对象的引用（地址）值传递给参数，参数和对象都指向同一个对象，相互影响。  

### 数组  
1. 在 JavaScript 中，数组可以容纳任何类型的值，可以是字符串、 数字、对象（object），甚至是其他数组，对数组声明后即可向其中加入值，不需要预先设定大小  
2. var a = [ ]; a.length; // 0   
3. 使用 delete 运算符可以将单元从数组中删除，但是请注意，单元删除后，数 组的 length 属性并不会发生变化。  
4. 如果字符串键值能够被强制类型转换为十进制数字的话，它 就会被当作数字索引来处理。var a = [ ]; a["13"] = 42; a.length; // 14  
### 字符串  
1. JavaScript 中的字符串和字符数组并不是一回事  
2. var a = "foo"; var b = ["f","o","o"]; 字符串和数组的确很相似，它们都是类数组：a.length=b.length=3  
3. JavaScript 中字符串是不可变的，而数组是可变的.字符串不可变是指字符串的成员函数不会改变其原始值，而是创建并返回一个新的字符 串。而数组的成员函数都是在其原始值上进行操作。  
4. push--在末尾加元素；reverse()--字符串反转；split--转换为数组；join--将数组中的字符拼接回字符串  
5. 字符串可用+=拼接  
6. slice用于字符串截取
### 数字  
1. 数字前面的 0 可以省略：var a = 0.42; var b = .42;  
2. 特别大和特别小的数字默认用指数格式显示，与 toExponential() 函数的输出结果相同。 
var a = 5E10; a;// 50000000000    a.toExponential();  // "5e+10"   
3. tofixed(..) 方法可指定小数部分的显示位数；toPrecision(..) 方法用来指定有效数位的显示位数：  
4. 二进制浮点数中的 0.1 和 0.2 并不是十分精确，它们相加的结果并非刚好等于 0.3，而是一个比较接近的数字 0.30000000000000004，所以条件判断结果为 false。0.1 + 0.2 === 0.3; // false  
Infinity比任何一个数都大（NaN除外），-Infinity比任何一个数都小（NaN除外）
### 特殊数值  
1. undefined 类型只有一个值，即 undefined。null 类型也只有一个值，即 null。它们的名 称既是类型也是值。null 指空值，或曾赋过值，但是目前没有值；undefined 指没有值，从未赋值。undefined和null都没有属性  
null 是一个特殊关键字，不是标识符，我们不能将其当作变量来使用和赋值。然而 undefined 却是一个标识符，可以被当作变量来使用和赋值。永远不要重新定义 undefined.void 运算符返回 undefined 丢失的参数也是undefined  
2.NaN 意指“不是一个数字”（not a number），理解为“无效数值”“失败数值”或者“坏数值”可能更准确些。NaN 是一个特殊值，它和自身不相等，是唯一一个非自反的值。而 NaN != NaN 为 true.可以使用内建的全局工具函数 isNaN(..) 来判断一个值是否是 NaN  
### 函数  
1. 实参>形参----额外的参数会被忽略（arguments除外），实参<形参，丢失的参数是undefined  
2. 闭包：函数以及它所连接的周围作用域中的变量即为闭包。  


1. 等于号的两种不同用法：①一个单独的等于号，用于为变量赋值；②三个连续的等号，用于比较两个值  
2. JS中的两种注释：单行注释：由//开始；多行注释：/* */  
3. 每个对象都有唯一的标识且只等于自己（所有的非基本数据类型外，都是对象）  
4. 原始布尔类型包含true和false。二元逻辑运算符（&&与、||或）、前置逻辑运算符（！非）、比较运算符【相等运算符===、！==、==、！= ；排序运算符（针对字符串及数字）>,<,>=,<=】这些运算符会产生布尔值

