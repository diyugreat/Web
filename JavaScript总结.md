[TOC]

------



# 为何学习JavaScript？

JavaScript 是 web 开发者必学的三种语言之一：

- *HTML* 定义了·网页的内容
- *CSS* 规定了网页的布局
- *JavaScript* 控制了网页的行为（动作）

**现在的JavaScript不仅仅是一门简单的脚本语言了，无论前端还是后端，JavaScript都有良好的表现。**

# JS用法

HTML 中的 Javascript 脚本代码必须位于 **\<script>** 与 **\</script>** 标签之间。

> **注释：** 旧的 JavaScript 例子也许会使用 `type` 属性：\<script type="text/javascript">。
>
> **注释：** type 属性不是必需的。JavaScript 是 HTML 中的默认脚本语言。

## 内部JavaScript

Javascript 脚本代码**全部**放置在 HTML 页面的 **\<body>** 或者 **\<head>** 部分中。

==示例==

head内的js，会页面加载时弹出窗口显示相应内容

body内的js，会在指定地方添加内容，若已有内容，则覆盖掉。

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <script>
      alert("我的第一个 JavaScript");
    </script>
  </head>
  <body>
    <p id="demo">body内部的js</p>
    <button type="button" onclick="myFunction()">试一试</button>
    <script >
      function myFunction() {
         document.getElementById("demo").innerHTML = "P段落被更改。";   // 点击button按钮，p段落内容改变
      }
    </script>
  </body>
</html>
```

先弹出窗口

![image-20220702222044724](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220702222044724.png)

点击确定后，点击按钮，对应内容改变

![image-20220702223744075](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220702223744075.png)

![image-20220702223756761](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220702223756761.png)

## 外部JavaScript（脚本文件）

外部 js，也就是我们所熟悉的脚本文件用法。

只需要在外面单独建一个js文件，然后在 **\<body>** 或者 **\<head>** 中引用即可。

建立 `myjs.js`文件，内容如下

```js
function myFunction() {
    document.getElementById("demo").innerHTML = "Hello world！P段落被更改。";
 }
```

在**\<script>**标签中引用js文件

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
  </head>
  <body>
    <p id="demo">body内部的js</p>
    <button type="button" onclick="myFunction()">试一试</button>
    <script src="./myjs.js" ></script>   <!-- 引用js文件 -->
  </body>
</html>
```

**外部 JavaScript 的优势**

在外部文件中放置脚本有如下优势：

- 分离了 HTML 和代码
- 使 HTML 和 JavaScript 更易于阅读和维护
- 已缓存的 JavaScript 文件可加速页面加载

如需向一张页面添加多个脚本文件 - 请使用多个 script 标签：

# JS输出

JavaScript 能够以不同方式“显示”数据：

- 使用 `window.alert()` 写入警告框
- 使用 `document.write()` 写入 HTML 输出
- 使用 `innerHTML` 写入 HTML 元素
- 使用 `console.log()` 写入浏览器控制台

**innerHTML**

如需访问 HTML 元素，JavaScript 可使用 `document.getElementById(id)` 方法。

`id` 属性定义 HTML 元素。innerHTML 属性定义 HTML 内容：

**提示：**更改 HTML 元素的 innerHTML 属性是在 HTML 中显示数据的常用方法。

```html
<script>
 document.getElementById("demo").innerHTML = 5 + 6;  // id=demo处的元素内容为11
</script>
```

**window.alert()**

能够使用警告框来显示数据：

```html
<script>
window.alert(5 + 6);  // 弹出警告（提示）框，显示计算结果
</script>
```

**document.write()**

在网页中相应位置直接进行输出

**提示：**`document.write()` 方法仅用于测试。

**注意：**在 HTML 文档完全加载后使用 `document.write()` 将*删除所有已有的 HTML* ：

```html
<!DOCTYPE html>
<html>
<body>
<h2>我的第一张网页</h2>
<p>我的第一个段落。</p>
<script>
	document.write(5 + 6);
</script>
</body>
</html>
```

![image-20220702224844534](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220702224844534.png)

**console.log()**

在浏览器中，您可使用 `console.log()` 方法来显示数据。

请通过 F12 来激活浏览器控制台，并在菜单中选择“控制台”。

```html
<!DOCTYPE html>
<html>
<body>

<h1>我的第一张网页</h1>
<p>我的第一个段落</p>

<script>
console.log(5 + 6);
</script>

</body>
</html>
```

![image-20220702225432214](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220702225432214.png)

# JS语法

JavaScript 语法是一套规则，它定义了 JavaScript 的语言结构。

```js
var x, y;	// 如何声明变量
x = 7; y = 8;	// 如何赋值
z = x + y;	// 如何计算值
```

**JavaScript 值**

JavaScript 语句定义两种类型的值：混合值（固定值）和变量值。

混合值被称为 *字面量（literal）*。变量值被称为 *变量*。

## JavaScript 字面量

**数字（Number）字面量** 可以是整数或者是小数，或者是科学计数(e)。

> 3.14 小数   1001 整数   123e5 科学计数

**字符串（String）字面量** 可以使用单引号或双引号:

> "di yu"  ，或者 'di yu'  

**数组（Array）字面量** 定义一个数组：

> [40, 100, 1, 5, 25, 10]

**对象（Object）字面量** 定义一个对象：

> {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"}

**函数（Function）字面量** 定义一个函数：

> function myFunction(a, b) { return a * b;}

## JavaScript 变量

在编程语言中，*变量*用于*存储*数据值。

JavaScript 使用 `var` 关键词来*声明*变量。

`=` 号用于为变量*赋值*。

在本例中，x 被定义为变量。然后，x 被赋的值是 7：

```js
// 先声明，再赋值
var x;   
x = 7;
// 声明时赋值
var x = 7;
// 一条语句中声明许多变量
var person = "Bill Gates", carName = "porsche", price = 15000;
// 不带有值的变量，它的值将是 undefined。
var carName;  // 变量 carName 在这条语句执行后的值是 undefined
// 重复声明 JavaScript 变量，将不会丢失它的值。
var carName = "porsche";
var carName;   // 变量 carName 的值仍然是 "porsche"

```

变量是一个**名称**。字面量是一个**值**。



## JavaScript 运算符

JavaScript 使用*算数运算符*（`+` `-` `*` `/`）来*计算值*：

```js
(7 + 8) * 10
```

JavaScript 使用*赋值运算符*（`=`）向变量*赋值*：

```js
var x, y;
var x = 7;
var y = 8;
```

JavaScript语言有多种类型的运算符：

| 类型                   | 实例      | 描述                   |
| :--------------------- | :-------- | :--------------------- |
| 赋值，算术和位运算符   | = + - * / | 在 JS 运算符中描述     |
| 条件，比较及逻辑运算符 | == != < > | 在 JS 比较运算符中描述 |

## JavaScript 语句

在 HTML 中，JavaScript 语句向浏览器发出的命令。

语句是用分号分隔：

```js
x = 5 + 6;
y = x * 10;
```

## JavaScript 关键字

JavaScript 关键字用于标识要执行的操作。

和其他任何编程语言一样，JavaScript 保留了一些关键字为自己所用。

**var** 关键字告诉浏览器创建一个新的变量：

```js
var x = 5 + 6;
var y = x * 10;
```

## JavaScript 注释

并非所有 JavaScript 语句都被“执行”。

双斜杠 `//` 或 `/*` 与 **/* 之间的代码被视为*注释*。

注释会被忽略，不会被执行：

```js
var x = 7;   // 会执行

// var x = 8;   不会执行
```

**单行注释**

单行注释以 `//` 开头。

任何位于 `//` 与行末之间的文本都会被 JavaScript 忽略（不会执行）。

**多行注释**

多行注释以 `/*` 开头，以 `*/` 结尾。

任何位于 `/*` 和 `*/` 之间的文本都会被 JavaScript 忽略。

## JavaScript 数据类型

JavaScript 有多种数据类型：数字，字符串，数组，对象等等：

```js
var length = 16;                  				// Number 通过数字字面量赋值
var points = x * 10;             		 		 // Number 通过表达式字面量赋值
var lastName = "Johnson";             			// String 通过字符串字面量赋值
var cars = ["Saab", "Volvo", "BMW"];       		// Array 通过数组字面量赋值
var person = {firstName:"John", lastName:"Doe"}; // Object 通过对象字面量赋值
```

## JavaScript 标识符

标识符是名称。

在 JavaScript 中，标识符用于命名变量（以及关键词、函数和标签）。

在大多数编程语言中，合法名称的规则大多相同。

所有 JavaScript *变量*必须以*唯一的名称*的*标识*。

这些唯一的名称称为*标识符*。

标识符可以是短名称（比如 x 和 y），或者更具描述性的名称（age、sum、totalVolume）。

构造变量名称（唯一标识符）的通用规则是：

- 名称可包含字母、数字、下划线和美元符号
- 名称必须以字母开头,，也可以 `$` 和 `_` 开头
- 名称对大小写敏感（y 和 Y 是不同的变量）
- 保留字（比如 JavaScript 的关键词）无法用作变量名称

**提示：**JavaScript 标识符对大小写敏感。

**提示：**数值不可以作为首字符。这样，JavaScript 就能轻松区分标识符和数值。

## JavaScript 字母大小写

JavaScript 对大小写是敏感的。

当编写 JavaScript 语句时，请留意是否关闭大小写切换键。

函数 **getElementById** 与 **getElementbyID** 是不同的。

同样，JavaScript 不会把 VAR 或 Var 译作关键词 **var**。

## JavaScript 字符集

JavaScript 使用 *Unicode* 字符集。

Unicode 覆盖世界上几乎所有的字符、标点和符号。

# JS作用域

ES2015 引入了两个重要的 JavaScript 新关键词：`let` 和 `const`。

这两个关键字在 JavaScript 中提供了块作用域（*Block Scope*）变量（和常量）。

在 ES2015 之前，JavaScript 只有两种类型的作用域：*全局作用域*和*函数作用域*。

## 全局作用域

*全局*（在函数之外）声明的变量拥有*全局作用域*。

==提示==：*全局*变量可以在 JavaScript 程序中的任何位置访问。

```js
var carName = "porsche";

// 此处的代码可以使用 carName

function myFunction() {
  // 此处的代码也可以使用 carName
}
```

## 函数作用域

*局部*（函数内）声明的变量拥有*函数作用域*。

==提示==：*局部*变量只能在它们被声明的函数内访问。

```js
// 此处的代码不可以使用 carName

function myFunction() {
  var carName = "porsche";
  // code here CAN use carName
}

// 此处的代码不可以使用 carName
```

## 块作用域

通过 `var` 关键词声明的变量 **没有** 块*作用域*。

在块 *{}* 内声明的变量可以从块之外进行访问。

在 ES2015 之前，JavaScript 是没有块作用域的。

ES2015 引入了两个重要的 JavaScript 新关键词：`let` 和 `const`。

==可以使用 `let` 关键词声明拥有块作用域的变量。==

 `const` 定义的变量与 `let` 变量类似，但不能重新赋值：

在块 *{}* 内声明的变量无法从块外访问：

实例1

```js
{ 
  var x = 10; 
}
// 此处可以使用 x

{ 
  let x = 10;
}
// 此处不可以使用 x

var x = 10;
// 此处 x 为 10
{ 
  let x = 6;
  // 此处 x 为 6
}
// 此处 x 为 10
```

示例2

```js
// 常量不允许修改
const PI = 3.141592653589793;
PI = 3.14;      // 会出错
PI = PI + 10;   // 也会出错

// 常量对象可以更改。
const car = {type:"porsche", model:"911", color:"Black"};  // 可以创建 常量对象：
car.color = "White";   // 可以更改属性：
car.owner = "Bill";     // 可以添加属性：
// 常量数组可以更改
const cars = ["Audi", "BMW", "porsche"];    // 可以创建常量数组：
cars[0] = "Honda";    // 可以更改元素：
cars.push("Volvo");    // 可以添加元素：
```

# JS运算符

## 算数运算符

算数运算符用于对数字执行算数运算：

| 运算符 | 描述         |
| :----- | :----------- |
| +      | 加法         |
| -      | 减法         |
| *      | 乘法         |
| /      | 除法         |
| %      | 取模（余数） |
| ++     | 递加         |
| --     | 递减         |

## 赋值运算符

赋值运算符向 JavaScript 变量赋值。

| 运算符 | 例子   | 等同于    |
| :----- | :----- | :-------- |
| =      | x = y  | x = y     |
| +=     | x += y | x = x + y |
| -=     | x -= y | x = x - y |
| *=     | x *= y | x = x * y |
| /=     | x /= y | x = x / y |
| %=     | x %= y | x = x % y |

加法赋值运算符（`+=`）向变量添加一个值。

## 比较运算符

| 运算符 | 描述           |
| :----- | :------------- |
| ==     | 等于           |
| ===    | 等值等型       |
| !=     | 不相等         |
| !==    | 不等值或不等型 |
| >      | 大于           |
| <      | 小于           |
| >=     | 大于或等于     |
| <=     | 小于或等于     |
| ?      | 三元运算符     |

## 逻辑运算符

| 运算符 | 描述   |
| :----- | :----- |
| &&     | 逻辑与 |
| \|\|   | 逻辑或 |
| !      | 逻辑非 |

## 类型运算符

| 运算符     | 描述                                  |
| :--------- | :------------------------------------ |
| typeof     | 返回变量的类型。                      |
| instanceof | 返回 true，如果对象是对象类型的实例。 |

## 位运算符

位运算符处理 32 位数。

该运算中的任何数值运算数都会被转换为 32 位的数。结果会被转换回 JavaScript 数。

| 运算符 | 描述         | 例子    | 等同于       | 结果 | 十进制 |
| :----- | :----------- | :------ | :----------- | :--- | :----- |
| &      | 与           | 5 & 1   | 0101 & 0001  | 0001 | 1      |
| \|     | 或           | 5 \| 1  | 0101 \| 0001 | 0101 | 5      |
| ~      | 非           | ~ 5     | ~0101        | 1010 | 10     |
| ^      | 异或         | 5 ^ 1   | 0101 ^ 0001  | 0100 | 4      |
| <<     | 零填充左位移 | 5 << 1  | 0101 << 1    | 1010 | 10     |
| >>     | 有符号右位移 | 5 >> 1  | 0101 >> 1    | 0010 | 2      |
| >>>    | 零填充右位移 | 5 >>> 1 | 0101 >>> 1   | 0010 | 2      |

# JS语句

## if 条件语句

```js
if (condition1)
{
    当条件 1 为 true 时执行的代码
}
else if (condition2)
{
    当条件 2 为 true 时执行的代码
}
else
{
  当条件 1 和 条件 2 都不为 true 时执行的代码
}
```

## switch 语句

```js
switch(n)
{
    case 1:
        执行代码块 1
        break;
    case 2:
        执行代码块 2
        break;
    default:
        与 case 1 和 case 2 不同时执行的代码
}
```

## for 循环

-  `for for-in for-of  forEach`

```js
var colors = ['red', 'green', 'blue', 'brown'];	//colors是一个数组
//传统遍历（基本不用了）
for(var i=0;i<colors.length;i++){
  console.log(colors[i]);
}
//for-in，专注下标
for(var c in colors){
  console.log(colors[c]);
}
//for-of，专注元素
for(var c of colors){
  console.log(c);
}
//高级遍历
colors.forEach(c => console.log(c));
var other = colors.map(c => c + 'X');  //map不仅遍历，还返回另一个数组
console.log(other);
```

## while 循环

```js
while (条件)
{
    需要执行的代码
}

do
{
    需要执行的代码
}
while (条件);
```

## break 和 continue 语句

break 语句用于跳出循环。

continue 用于跳过循环中的一个迭代。

# JS对象

在 JavaScript 中，几乎“所有事物”都是对象。

- 布尔是对象（如果用 *new* 关键词定义）
- 数字是对象（如果用 *new* 关键词定义）
- 字符串是对象（如果用 *new* 关键词定义）
- 日期永远都是对象
- 算术永远都是对象
- 正则表达式永远都是对象
- 数组永远都是对象
- 函数永远都是对象
- 对象永远都是对象

**所有 JavaScript 值，除了原始值，都是对象。**

## JavaScript 原始值

*原始值* 指的是没有属性或方法的值。

*原始数据类型*指的是拥有原始值的数据。

JavaScript 定义了 5 种原始数据类型：

- string
- number
- boolean
- null
- undefined

原始值是一成不变的（它们是硬编码的，因此不能改变）。

假设 x = 3.14，您能够改变 x 的值。但是您无法改变 3.14 的值。

| 值        | 类型      | 注释                       |
| :-------- | :-------- | :------------------------- |
| "Hello"   | string    | "Hello" 始终是 "Hello"     |
| 3.14      | number    | 3.14 始终是 3.14           |
| true      | boolean   | true 始终是 true           |
| false     | boolean   | false 始终是 false         |
| null      | null      | (object) null 始终是 null  |
| undefined | undefined | undefined 始终是 undefined |

## 对象是包含变量的变量

JavaScript 变量能够包含单个的值：

```js
var person = "Bill Gates";
```

对象也是变量。但是对象能够包含很多值。

值按照 **名称（属性） : 值** 的形式编写（名称和值以冒号分隔）。

```js
var person = {firstName:"Bill", lastName:"Gates", age:62, eyeColor:"blue"};
```

# JavaScript 函数

**JavaScript 函数是通过 `function` 关键词\*定义\*的。**

可以使用函数声明或函数表达式。

## 函数声明

通过如下语法*声明*函数：

```js
function functionName(parameters) {
   要执行的代码
}
```

被声明的函数不会直接执行。它们被“保存供稍后使用”，将在稍后执行，当它们被调用时。

==实例==

```js
function myFunction(a, b) {
     return a * b;
}
```

分号用于分隔可执行的 JavaScript 语句。

由于函数*声明*不是可执行的语句，以分号结尾并不常见。

## 函数表达式

JavaScript 函数也可以使用*表达式*来定义。

函数表达式可以在变量中存储：

==实例==

```js
var x = function (a, b) {return a * b};
```

## 函数提升

Hoisting 是 JavaScript 将 *声明* 移动到当前作用域顶端的默认行为。

Hoisting 应用于变量声明和函数声明。

正因如此，JavaScript 函数能够在声明之前被调用：

```js
myFunction(5);

 function myFunction(y) {
     return y * y;
}
```

使用表达式定义的函数不会被提升。

## 箭头函数

箭头函数允许使用简短的语法来编写函数表达式。

您不需要 function 关键字、return 关键字和花括号。

==实例==

```js
// ES5
var x = function(x, y) {
  return x * y;
}

// ES6
const x = (x, y) => x * y;
```

箭头函数没有自己的 this。它们不适合定义对象方法。

箭头函数未被提升。它们必须在使用前进行定义。

使用 const 比使用 var 更安全，因为函数表达式始终是常量值。

如果函数是单个语句，则只能省略 return 关键字和大括号。因此，保留它们可能是一个好习惯：

==实例==

```js
const x = (x, y) => { return x * y };
```

# 参考资料

* MDN
* 菜鸟教程
* w3school
