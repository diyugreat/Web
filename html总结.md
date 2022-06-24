[TOC]

------

网页内容可以是：一组段落、一个重点信息列表、也可以含有图片和数据表。正如标题所示，本文将对 HTML 及其功能做一个基本介绍。

# HTML 到底是什么？

超文本标记语言 (英语：**H**yper**t**ext **M**arkup **L**anguage，简称：HTML ) 是一种用来结构化 Web 网页及其内容的标记语言。

==说人话就是: html = 网页内容== 

HTML 不是一门编程语言，而是一种用于定义内容结构的*标记语言*。HTML 由一系列的**元素**组成，这些元素可以用来包围不同部分的内容，使其以某种方式呈现或者工作。 一对标签（ tags）可以为一段文字或者一张图片添加超链接，将文字设置为斜体，改变字号，等等。 

例如，键入下面一行内容：

```html
我的猫非常脾气暴躁
```

可以将这行文字封装成一个段落（**p**aragraph）元素来使其在单独一行呈现：

```html
<p>我的猫非常脾气暴躁</p>
```

p：段落标签

## HTML 元素详解

让我们深入探索一下这个段落元素。



<img src="https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220527091746941.png" alt="image-20220527091746941" style="zoom: 67%;" />

这个元素的主要部分有：

1. **开始标签**（Opening tag）：包含元素的名称（本例为 p），被大于号、小于号所包围。表示元素从这里开始或者开始起作用 —— 在本例中即段落由此开始。
2. **结束标签**（Closing tag）：与开始标签相似，只是其在元素名之前包含了一个斜杠。这表示着元素的结尾 —— 在本例中即段落在此结束。初学者常常会犯忘记包含结束标签的错误，这可能会产生一些奇怪的结果。
3. **内容**（Content）：元素的内容，本例中就是所输入的文本本身。
4. **元素**（Element）：开始标签、结束标签与内容相结合，便是一个完整的元素。

元素也可以有属性（Attribute）：

![image-20220527092657465](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220527092657465.png)



属性包含了关于元素的一些额外信息，这些信息本身不应显现在内容中。本例中，`class` 是属性名称，`editor-note` 是属性的值 。`class` 属性可为元素提供一个标识名称，以便进一步为元素指定样式或进行其他操作时使用。

属性应该包含：

1. 在属性与元素名称 或 元素与元素之间添加空格符。`元素p 与 属性名称class 间有空格`
2. 属性的名称，并接上一个等号。`比如 class=`
3. 由引号所包围的属性值。`属性值用引号括起来，比如 “edtior-note”`

> **注：**不包含 ASCII 空格（以及 `"` `'` ``` `=` `<` `>` ）的简单属性值可以不使用引号，但是建议将所有属性值用引号括起来，这样的代码一致性更佳，更易于阅读。



## HTML 文档详解

以上介绍了 HTML 元素，但孤木不成林。现在来看看单个元素如何彼此协同构成一个完整的 HTML 页面。

html文件内容如下：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <p>我的猫咪脾气<strong>暴躁</strong>:)</p>
    <!-- p标签：段落标签-->
    <!-- strong标签：文字加粗 -->
</body>
</html>
```

这里有：

- `<!DOCTYPE html>` — 文档类型，这里即 html 5。<!DOCTYPE> 不是 HTML 标签。它为浏览器提供一项信息（声明），即 HTML 是用什么版本编写的。
- `<html></html>` — `html`元素。该元素包含整个页面的内容，也称作根元素。
- `<head></head>` — `head` 元素。该元素的内容对用户不可见，其中包含例如面向搜索引擎的搜索关键字（[keywords](https://developer.mozilla.org/zh-CN/docs/Glossary/Keyword)）、页面描述、CSS 样式表和字符编码声明等。
- `<meta charset="utf-8">` — 该元素指定文档使用 UTF-8 字符编码 ，UTF-8 包括绝大多数人类已知语言的字符。基本上 UTF-8 可以处理任何文本内容，还可以避免以后出现某些问题，没有理由再选用其他编码。
- `<title></title>` — `title`元素。该元素设置页面的标题，显示在浏览器标签页上，也作为收藏网页的描述文字。
- `<body></body>` — `body`元素。该元素包含期望让用户在访问页面时看到的内容，包括文本、图像、视频、游戏、可播放的音轨或其他内容。

# HTML5 标签

## 1 标题、水平线、段落、注释

标题（Heading）是通过 \<h1> - \<h6> 等标签进行定义的。

\<h1> 定义最大的标题。\<h6> 定义最小的标题。

\<hr /> 标签在 HTML 页面中创建水平线。

\<p> 定义了段落标签

\<!-- 注释内容 -->：**注释：**开始括号之后（左边的括号）需要紧跟一个叹号，结束括号之前（右边的括号）不需要

```html
<!DOCTYPE html>
<html>
<body>
    <h1>这是h1标题</h1>
    <h2>这是h2标题</h2>
    <h3>这是h3标题</h3>
    <hr />  <!-- 水平线-->
    <p>这是一个段落</p>
    <!-- This is a comment，这是一个注释 -->
</body>
</html>
```

![image-20220617223223858](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220617223223858.png)

## 2 style样式

style属性作用：可以改变所有HTML元素的样式的通用方式。

它可以定义背景颜色（background-color），字体样式（font-family），字体颜色（color ），尺寸（font-size），还有文本对齐方式（text-align）

```html
<!DOCTYPE html>
<html>
<body>
    <h1 style="background-color:yellow">这是h1标题</h1>
    <h2 style="background-color:red">这是h2标题</h2>
    <h3>这是h3标题</h3>
    <hr />  <!-- 水平线-->
    <p text-align: center>这是一个段落，且中心对齐</p>
    <p style="font-family:arial;color:red;font-size:20px;">这是一个段落：arial字体，红色字体，大小20px</p>
    <!-- This is a comment，这是一个注释 -->
</body>
</html>
```

![image-20220617224454890](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220617224454890.png)

## 3 格式化标签

文本格式化

|   标签    |      描述      |
| :-------: | :------------: |
|   \<b>    | 定义粗体文本。 |
|  \<big>   |  定义大号字。  |
|   \<em>   | 定义着重文字。 |
|   \<i>    |  定义斜体字。  |
| \<small>  |  定义小号字。  |
| \<strong> | 定义加重语气。 |
|  \<sub>   |  定义下标字。  |
|  \<sup>   |  定义上标字。  |
|  \<ins>   |  定义插入字。  |
|  \<del>   |  定义删除字。  |

 “计算机输出” 标签

|  标签   |         描述         |
| :-----: | :------------------: |
| \<code> |   定义计算机代码。   |
| \<kbd>  |     定义键盘码。     |
| \<samp> | 定义计算机代码样本。 |
|  \<tt>  |   定义打字机代码。   |
| \<var>  |      定义变量。      |
| \<pre>  |   定义预格式文本。   |

 引用、引用和术语定义

|     标签      |        描述        |
| :-----------: | :----------------: |
|    \<abbr>    |     定义缩写。     |
|  \<acronym>   |  定义首字母缩写。  |
|  \<address>   |     定义地址。     |
|    \<bdo>     |   定义文字方向。   |
| \<blockquote> |   定义长的引用。   |
|     \<q>      |  定义短的引用语。  |
|    \<cite>    |  定义引用、引证。  |
|    \<dfn>     | 定义一个定义项目。 |

## 4 颜色

颜色由红色、绿色、蓝色混合而成。

它可以由颜色值和颜色名表示。

颜色值支持HEX十六进制（\#000000，黑色），以及RGB值 rgb(0,0,0)，黑色。比如下图

![image-20220617233846055](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220617233846055.png)

颜色名即预先已经定义好的颜色，有十六种：aqua, black, blue, fuchsia, gray, green, lime, maroon, navy, olive, purple, red, silver, teal, white, yellow。

## 5 超链接

超链接可以是一个字，一个词，或者一组词，也可以是一幅图像，您可以点击这些内容来跳转到新的文档或者当前文档中的某个部分。

当您把鼠标指针移动到网页中的某个链接上时，箭头会变为一只小手。

我们通过使用 \<a> 标签在 HTML 中创建链接。

有两种使用 \<a> 标签的方式：

1. 通过使用 href 属性 - 创建指向另一个文档的链接
2. 通过使用 name 属性 - 创建文档内的书签

```html
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3School!</a>
```

href：指定链接，被链接资源/文档的 URL。

target属性：规定在何处打开链接文档，比如在当前页面打开，还是新建页面打开

| target属性值 |                 描述                 |
| :----------: | :----------------------------------: |
|    _blank    |      在新窗口中打开被链接文档。      |
|    _self     | 默认。在相同的框架中打开被链接文档。 |
|   _parent    |     在父框架集中打开被链接文档。     |
|     _top     |     在整个窗口中打开被链接文档。     |
|  framename   |    在指定的框架中打开被链接文档。    |

name属性：规定锚（anchor）的名称，可以用来创建 HTML 页面中的书签

首先，我们在 HTML 文档中对锚进行命名（创建一个书签）：

```html
<a name="tips">基本的注意事项 - 有用的提示</a>
```

然后，我们在同一个文档中创建指向该锚的链接：

```html
<a href="#tips">有用的提示</a>
```

这样点击 href=“#tips”这个链接，就会跳转到本页面指定的地方（即 name=“tips”)

## 6 图像、音频、视频

在 HTML 中，图像由 \<img> 标签定义。

\<img> 是空标签，意思是说，它只包含属性，并且没有闭合标签。

要在页面上显示图像，你需要使用源属性（src）。src 指 "source"。源属性的值是图像的 URL 地址。

alt属性为替换文本，当图像无法显示时，此文本会代替图像显示。

```html
<img src="boat.gif" alt="Big Boat">
```

| 图像标签 |             描述             |
| :------: | :--------------------------: |
|  \<img>  |          定义图像。          |
|  \<map>  |        定义图像地图。        |
| \<area>  | 定义图像地图中的可点击区域。 |



音频由 \<audio> 标签定义，下面就是最后浏览器展现的情况。\<audio>元素是一个 HTML5 元素，在 HTML 4 中是非法的，但在所有浏览器中都有效。

<audio> 元素是一个 HTML5 元素，在 HTML 4 中是非法的，但在所有浏览器中都有效。

```html
<audio controls="controls">
  <source src="song.mp3" type="audio/mp3" />
</audio>
```

视频由 \<video> 标签定义，下面就是最后浏览器展现的情况。\<video>元素是一个 HTML5 元素，在 HTML 4 中是非法的，但在所有浏览器中都有效。

<video> 是 HTML 5 中的新标签。

以下 HTML 片段会显示一段嵌入网页的 ogg、mp4 或 webm 格式的视频：

```html
<video width="320" height="240" controls="controls">
  <source src="movie.mp4" type="video/mp4" />
  <source src="movie.ogg" type="video/ogg" />
  <source src="movie.webm" type="video/webm" />
Your browser does not support the video tag.
</video>
```

## 7 表格

表格由 \<table> 标签来定义。每个表格均有若干行（由 \<tr> 标签定义），每行被分割为若干单元格（由 \<td> 标签定义）。字母 td 指表格数据（table data），即数据单元格的内容。数据单元格可以包含文本、图片、列表、段落、表单、水平线、表格等等。

表格的表头使用 \<th> 标签进行定义

![image-20220618001021091](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220618001021091.png)

```html
<!DOCTYPE html>
<html>
<body>
    <table border="1">
        <caption>跨两列的单元格</caption>
        <tr>
          <th>姓名</th>
          <th colspan="2">电话</th>
        </tr>
        <tr>
          <td>Bill Gates</td>
          <td>555 77 854</td>
          <td>555 77 855</td>
        </tr>
        </table>
        <br>  <!-- 空行 -->
        <table border="1">
         <caption>横跨两行的单元格</caption>
        <tr>
          <th>姓名</th>
          <td>Bill Gates</td>
        </tr>
        <tr>
          <th rowspan="2">电话</th>
          <td>555 77 854</td>
        </tr>
        <tr>
          <td>555 77 855</td>
        </tr>
        </table>
</body>
</html>
```

## 8 列表

**无序列表**

无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记。

无序列表始于 \<ul> 标签。每个列表项始于 \<li>。

```html
<ul>
<li>Coffee</li>
<li>Milk</li>
</ul>
```

浏览器显示如下：

- Coffee
- Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

**有序列表**

同样，有序列表也是一列项目，列表项目使用数字进行标记。

有序列表始于 <ol> 标签。每个列表项始于 <li> 标签。

```html
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
```

浏览器显示如下：

1. Coffee
2. Milk

列表项内部可以使用段落、换行符、图片、链接以及其他列表等等。

## 9 表单

\<form> 元素定义 HTML 表单：HTML 表单用于收集用户输入。

HTML 表单包含*表单元素*。表单元素指的是不同类型的 input 元素、复选框、单选按钮、提交按钮等等。

input标签详细查看：[HTML input 标签 | 菜鸟教程 (runoob.com)](https://www.runoob.com/tags/tag-input.html)

```html
<!DOCTYPE html>
<html>
<body>
<form action="/demo/demo_form.asp">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
<p>如果您点击提交，表单数据会被发送到名为 demo_form.asp 的页面。</p>
</body>
</html>
```

展示效果如下：

<form action="/demo/demo_form.asp">
First name:<br>
<input type="text" name="firstname" value="Mickey">
<br>
Last name:<br>
<input type="text" name="lastname" value="Mouse">
<br><br>
<input type="submit" value="Submit">
</form> 
<p>如果您点击提交，表单数据会被发送到名为 demo_form.asp 的页面。</p>

## 10 块元素（div、span），内联元素

 **HTML 块元素**

大多数 HTML 元素被定义为块级元素或内联元素。

编者注：“块级元素”译为 block level element，“内联元素”译为 inline element。

块级元素在浏览器显示时，通常会以新行来开始（和结束）。

例子：\<h1>, \<p>, \<ul>, \<table>

**HTML 内联元素**

内联元素在显示时通常不会以新行开始。

例子：\<b>, \<td>, \<a>, \<img>

**HTML \<div> 元素**

<p style="color:red"> 一句话概括，万物皆可div </p>

\<div> 可定义文档中的分区或节（division/section）。

\<div> 标签可以把文档分割为独立的、不同的部分。它可以用作严格的组织工具，并且不使用任何格式与其关联。

HTML \<div> 元素是块级元素，它是可用于组合其他 HTML 元素的容器。

\<div> 元素没有特定的含义。除此 之外，由于它属于块级元素，浏览器会在其前后显示折行。

如果与 CSS 一同使用，\<div> 元素可用于对大的内容块设置样式属性。

\<div> 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 \<table> 元素进行文档布局不是表格的正确用法。\<table> 元素的作用是显示表格化的数据。

**HTML \<span> 元素**

HTML \<span> 元素是内联元素，可用作文本的容器。

\<span> 元素也没有特定的含义。

当与 CSS 一同使用时，\<span> 元素可用于为部分文本设置样式属性。

## 11 CSS

**CSS 使得 HTML 页面变得更容易设置以及改变页面布局、外观**

**外部样式表**

当样式需要被应用到很多页面的时候，外部样式表将是理想的选择。使用外部样式表，你就可以通过更改一个文件来改变整个站点的外观。

```html
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
```

**内部样式表**

当单个文件需要特别样式时，就可以使用内部样式表。你可以在 head 部分通过 \<style> 标签定义内部样式表。

```html
<head>
<style type="text/css">
body {background-color: red}
p {margin-left: 20px}
</style>
</head>
```

**内联样式**

当特殊的样式需要应用到个别元素时，就可以使用内联样式。使用内联样式的方法是在相关的标签中使用样式属性。样式属性可以包含任何 CSS 属性。以下实例显示出如何改变段落的颜色和左外边距。

```html
<p style="color: red; margin-left: 20px">
This is a paragraph
</p>
```

## 12 class（类）、Id

class属性 用于对html元素分类，id属性用于指定html元素唯一id。

它们的作用都是方便使用CSS从而对指定元素设置特定样式。具体在CSS中介绍。

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- CSS样式 -->
    <style> 
      #myId {
        background-color: blue;
      }
      .myclass {
        background-color: pink;
      }
    </style>
  </head>
  <body>
    <h1 id="myId">id属性</h1>
    <h2 class="myclass">class属性</h2>
  </body>
</html>
```

![image-20220618220731854](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220618220731854.png)

## 13 iframe内联框架

iframe 元素会创建包含另外一个文档的内联框架（即行内框架）。即 **iframe 用于在网页内显示网页。**

src：指定框架内打开的URL链接。name：iframe框架名

详细属性了解：[HTML  标签 (w3school.com.cn)](https://www.w3school.com.cn/tags/tag_iframe.asp)

==用法==：iframe 可用作链接的目标（target）。链接的 target 属性必须引用 iframe 的 name 属性：

```html
<!DOCTYPE html>
<html>
  <body>
    <iframe src="URL" width="200" height="200" name="iframe_a"></iframe>
    <p> <a href="http://www.w3school.com.cn" target="iframe_a">W3School.com.cn</a>  </p>
    <p> <b>注释：</b>由于链接的目标匹配 iframe 的名称，所以链接会在 iframe
      中打开。 </p>
  </body>
</html>
```

<img src="https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220618222902080.png" alt="image-20220618222902080" style="zoom: 50%;" align="left" /><img src="https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220618223254475.png" alt="image-20220618223254475" style="zoom:50%;" />

## 14 JavaScricpt

**JavaScript 使 HTML 页面更具动态性和交互性**

HTML `<script>` 标签用于定义客户端脚本（JavaScript）。

\<script> 元素即可包含脚本语句，也可通过 src 属性指向外部脚本文件。

JavaScript 的常见用途是图像处理、表单验证和内容的动态更改。

如需选取 HTML 元素，JavaScript 最常用 `document.getElementById()` 方法。

这个 JavaScript 示例向 id="demo" 的 HTML 元素内写入 "Hello JavaScript!"：

```html
<script>
document.getElementById("demo").innerHTML = "Hello JavaScript!";
</script>
```

## 15 HTML 头部元素

**\<head> 元素**

\<head> 元素是所有头部元素的容器。\<head> 内的元素可包含脚本，指示浏览器在何处可以找到样式表，提供元信息，等等。

以下标签都可以添加到 head 部分：\<title>、\<base>、\<link>、\<meta>、\<script> 以及 \<style>。

**\<title> 元素**

\<title> 标签定义文档的标题。

title 元素在所有 HTML/XHTML 文档中都是必需的。

title 元素能够：

- 定义浏览器工具栏中的标题
- 提供页面被添加到收藏夹时显示的标题
- 显示在搜索引擎结果中的页面标题

**\<base> 元素**

\<base> 标签为页面上的所有链接规定默认地址或默认目标（target）：

**\<link> 元素**

\<link> 标签定义文档与外部资源之间的关系。

\<link> 标签最常用于连接外部CSS样式表。

**\<style> 元素**

\<style> 标签用于为 HTML 文档定义样式信息。

可以在 style 元素内规定 HTML 元素在浏览器中呈现的样式。

**\<meta> 元素**

元数据（metadata）是关于数据的信息。

\<meta> 标签提供关于 HTML 文档的元数据。元数据不会显示在页面上，但是对于机器是可读的。

典型的情况是，meta 元素被用于规定页面的描述、关键词、文档的作者、最后修改时间以及其他元数据。

\<meta> 标签始终位于 head 元素中。

元数据可用于浏览器（如何显示内容或重新加载页面），搜索引擎（关键词），或其他 web 服务。

**\<script> 元素**

\<script> 标签用于定义客户端脚本，比如 JavaScript。



## 16 更多标签

参考：[HTML 标签列表（功能排序） | 菜鸟教程 (runoob.com)](https://www.runoob.com/tags/ref-byfunc.html)



