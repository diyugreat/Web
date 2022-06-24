[TOC]

------

# CSS 基础

## 1 CSS介绍

- *CSS* 指的是层叠样式表 (*C*ascading *S*tyle *S*heets)，也称级联样式表
- CSS 描述了*如何在屏幕、纸张或其他媒体上显示 HTML 元素*
- CSS *节省了大量工作*。它可以同时控制多张网页的布局
- 外部样式表存储在 *CSS 文件*中

## 2 CSS语法

和 HTML 类似，CSS 也不是真正的编程语言，甚至不是标记语言。它是一门样式表语言，这也就是说人们可以用它来选择性地为 HTML 元素添加样式。

举例来说，要选择一个 HTML 页面里**所有**的段落元素，然后将其中的文本改成红色，可以这样写 CSS：

CSS 规则集（rule-set）由选择器和声明块组成：

![图解CSS声明](https://mdn.mozillademos.org/files/16483/css-declaration.png)

整个结构称为 **规则集**（通常简称“规则”），各部分释义如下：

- 选择器（**Selector**）

  HTML 元素的名称位于规则集开始。它选择了一个或多个需要添加样式的元素（在这个例子中就是 `p` 元素）。要给不同元素添加样式只需要更改选择器就行了。

- 声明（**Declaration**）

  一个单独的规则，如 `color: red;` 用来指定添加样式元素的**属性**。

- 属性（**Properties**）

  改变 HTML 元素样式的途径。（本例中 `color` 就是 [``](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p) 元素的属性。）CSS 中，由编写人员决定修改哪个属性以改变规则。

- 属性的值（Property value）

  在属性的右边，冒号后面即**属性的值**，它从指定属性的众多外观中选择一个值（我们除了 `red` 之外还有很多属性值可以用于 `color` ）。

注意其他重要的语法：

- 每个规则集（除了选择器的部分）都应该包含在成对的大括号里（`{}`）。
- 在每个声明里要用冒号（`:`）将属性与属性值分隔开。
- 在每个规则集里要用分号（`;`）将各个声明分隔开。

如果要同时修改多个属性，只需要将它们用分号隔开，就像这样：

```css
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}
```

**多元素选择**

也可以选择多种类型的元素并为它们添加一组相同的样式。将不同的选择器用逗号分开。例如：

```css
p, li, h1 {
  color: red;
}
```

## 3 CSS选择器

CSS 选择器用于“查找”（或选取）要设置样式的 HTML 元素。

我们可以将 CSS 选择器分为五类：

- 简单选择器（根据名称、id、类来选取元素）
- [组合器选择器](https://www.w3school.com.cn/css/css_combinators.asp)（根据它们之间的特定关系来选取元素）
- [伪类选择器](https://www.w3school.com.cn/css/css_pseudo_classes.asp)（根据特定状态选取元素）
- [伪元素选择器](https://www.w3school.com.cn/css/css_pseudo_elements.asp)（选取元素的一部分并设置其样式）
- [属性选择器](https://www.w3school.com.cn/css/css_attribute_selectors.asp)（根据属性或属性值来选取元素）

下面就介绍下最基本的 CSS 选择器。

 **简单选择器**

==CSS 元素选择器==

元素选择器根据元素名称来选择 HTML 元素。

**实例**（演示在后面）

在这里，页面上的所有 \<p> 元素都将居中对齐，并带有红色文本颜色：

```css
p {
  text-align: center;
  color: red;
}
```

==CSS id 选择器==

id 选择器使用 HTML 元素的 id 属性来选择特定元素。

元素的 id 在页面中是唯一的，因此 id 选择器用于选择一个唯一的元素！

要选择具有特定 id 的元素，请写一个井号（＃），后跟该元素的 id。

**注意：**id 名称不能以数字开头。

**实例**（演示在后面）

这条 CSS 规则将应用于 id="para1" 的 HTML 元素：

```css
#para1 {
  text-align: center;
  color: red;
}
```

==CSS 类选择器==

类选择器选择有特定 class 属性的 HTML 元素。

如需选择拥有特定 class 的元素，请写一个句点（.）字符，后面跟类名。

**注意：**类名不能以数字开头！

 **实例1**（演示在后面）

在此例中，所有带有 class="center" 的 HTML 元素将为红色且居中对齐：

```css
.center {
  text-align: center;
  color: red;
}
```

你还可以指定只有特定的 HTML 元素会受类的影响，实例2。

**实例2**（演示在后面）

在这个例子中，只有具有 class="center" 的 \<p> 元素会居中对齐：

```css
p.center {
  text-align: center;
  color: red;
}
```

==完整代码：==

```html
<!DOCTYPE html>
<html>
  <head>
    <style>
       /* 元素选择器 */
      p {
        text-align: center;
        color: red;
      }
      /* id选择器 */
      #para1 {
        text-align: center;
        color: blue;
      }
      /* class类选择器 */
      .center {
        text-align: center;
        color: orange;
      }
      /* 元素选择器与class选择器叠加 */
      p.center {
        text-align: center;
        color: green;
      }
    </style>
  </head>
  <body>
    <p>每个段落都会受到样式的影响。</p>
    <p id="para1">我也是！</p>
    <h1 class="center">这个标题不受影响</h1>
    <p class="center">这个段落将是红色并居中对齐的。</p>
  </body>
</html>
```

![image-20220619235349123](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220619235349123.png)

==CSS 通用选择器==

通用选择器（*）选择页面上的所有的 HTML 元素。

**实例**

下面的 CSS 规则会影响页面上的每个 HTML 元素：

```css
* {
  text-align: center;
  color: blue;
}
```

==CSS 分组选择器==

分组选择器选取所有具有相同样式定义的 HTML 元素。

若h1、h2 和 p 元素具有相同的样式定义，则可以对选择器进行分组，以最大程度地缩减代码。

**实例**

在这个例子中，我们对选择器进行分组：

```css
h1, h2, p {
  text-align: center;
  color: red;
}
```

**组合器选择器**

详细参考：[CSS 组合器 (w3school.com.cn)](https://www.w3school.com.cn/css/css_combinators.asp)

组合器是解释选择器之间关系的某种机制。

CSS 选择器可以包含多个简单选择器。在简单选择器之间，我们可以包含一个组合器。

CSS 中有四种不同的组合器：

- 后代选择器 (空格)
- 子选择器 (`>`)
- 相邻兄弟选择器 (`+`)
- 通用兄弟选择器 (`~`)

**伪类选择器**

详细参考：[CSS 伪类 (w3school.com.cn)](https://www.w3school.com.cn/css/css_pseudo_classes.asp)

伪类用于定义元素的特殊状态。

例如，它可以用于：

- 设置鼠标悬停在元素上时的样式
- 为已访问和未访问链接设置不同的样式
- 设置元素获得焦点时的样式

**伪元素选择器**

详细参考：[CSS 伪元素 (w3school.com.cn)](https://www.w3school.com.cn/css/css_pseudo_elements.asp)

CSS 伪元素用于设置元素指定部分的样式。

例如，它可用于：

- 设置元素的首字母、首行的样式
- 在元素的内容之前或之后插入内容

**属性选择器**

详细参考：[CSS 属性选择器 (w3school.com.cn)](https://www.w3school.com.cn/css/css_attribute_selectors.asp)

我们可以设置带有特定属性或属性值的 HTML 元素的样式。

**总结**

| 选择器名称                           | 选择的内容                                                   | 示例                                                         |
| :----------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 元素选择器（也称作标签或类型选择器） | 所有指定 (该) 类型的 HTML 元素                               | `p` 选择 `<p>`                                               |
| ID 选择器                            | 具有特定 ID 的元素（单一 HTML 页面中，每个 ID 只对应一个元素，一个元素只对应一个 ID） | `#my-id` 选择 `<p id="my-id">` 或 `<a id="my-id">`           |
| 类选择器                             | 具有特定类的元素（单一页面中，一个类可以有多个实例）         | `.my-class` 选择 `<p class="my-class">` 和 `<a class="my-class">` |
| 属性选择器                           | 拥有特定属性的元素                                           | `img[src]` 选择 `<img src="myimage.png">` 而不是 `<img>`     |
| 伪（Pseudo）类选择器                 | 特定状态下的特定元素（比如鼠标指针悬停）                     | `a:hover` 仅在鼠标指针悬停在链接上时选择 `<a>`。             |

## 4 CSS使用

CSS的三种用法：

- 外部 CSS
- 内部 CSS
- 行内 CSS

**外部 CSS**

通过使用外部样式表，您只需修改一个文件即可改变整个网站的外观！

每张 HTML 页面必须在 head 部分的 `<link>` 元素内包含对外部样式表文件的引用。

```html
<!DOCTYPE html>
<html>
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css">
</head>
<body>
	<h1>This is a heading</h1>
	<p>This is a paragraph.</p>
</body>
</html>
```

外部样式表可以在任何文本编辑器中编写，并且必须以 `.css` 扩展名保存。

外部 `.css` 文件不应包含任何 HTML 标签。

**"mystyle.css"** 是这样的：

```CSS
body {
  background-color: lightblue;
}

h1 {
  color: navy;
  margin-left: 20px;
}
```

**内部 CSS**

如果一张 HTML 页面拥有唯一的样式，那么可以使用内部样式表。

内部样式是在 head 部分的 `<style>` 元素中进行定义。

```html
<!DOCTYPE html>
<html>
<head>
<style>
body {
  background-color: linen;
}
h1 {
  color: maroon;
  margin-left: 40px;
} 
</style>
</head>
<body>
<h1>This is a heading</h1>
<p>This is a paragraph.</p>
</body>
</html>
```

**行内 CSS**

行内样式（也称内联样式）可用于为单个元素应用唯一的样式。

如需使用行内样式，请将 style 属性添加到相关元素。style 属性可包含任何 CSS 属性。

行内样式在相关元素的 "style" 属性中定义：

```html
<!DOCTYPE html>
<html>
<body>

<h1 style="color:blue;text-align:center;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>

</body>
</html>
```

**提示：**行内样式失去了样式表的许多优点（通过将内容与呈现混合在一起）。请谨慎使用此方法。

**层叠顺序**

当为某个 HTML 元素指定了多个样式时，会使用哪种样式呢？

页面中的所有样式将按照以下规则“层叠”为新的“虚拟”样式表，其中第一优先级最高：

1. 行内样式（在 HTML 元素中）
2. 外部和内部样式表（在 head 部分）。先后顺序，后者覆盖前者。
3. 浏览器默认样式

因此，行内样式具有最高优先级，并且将覆盖外部和内部样式以及浏览器默认样式。

## 5 CSS 注释

注释用于解释代码，以后在您编辑源代码时可能会有所帮助。

浏览器会忽略注释。

位于 `<style>` 元素内的 CSS 注释，以 `/*` 开始，以 `*/` 结束：可以跨越多行。

## 6 CSS颜色

指定颜色是通过使用预定义的颜色名称，或 RGB、HEX、HSL、RGBA、HSLA 值。

**颜色名称**

在 CSS 中，可以使用颜色名称来指定颜色：

147颜色名称定义在HTML和CSS的颜色规格(17个标准色加上130多个其他)

具体颜色名称：[CSS 颜色 (w3school.com.cn)](https://www.w3school.com.cn/cssref/css_colors.asp)

**HEX 值**

在 CSS 中，可以使用以下格式的十六进制值指定颜色：

`#rrggbb`

其中 rr（红色）、gg（绿色）和 bb（蓝色）是介于 00 和 ff 之间的十六进制值（与十进制 0-255 相同）。

例如，`#ff0000` 显示为红色，因为红色设置为最大值（ff），其他设置为最小值（00）。

**RGB 值**

在 CSS 中，可以使用下面的公式将颜色指定为 RGB 值：

**rgb(*red*, *green*, *blue*)**

每个参数 (*red*、*green* 以及 *blue*) 定义了 0 到 255 之间的颜色强度。

例如，rgb(255, 0, 0) 显示为红色，因为红色设置为最大值（255），其他设置为 0。

要显示黑色，请将所有颜色参数设置为 0，如下所示：rgb(0, 0, 0)。

要显示白色，请将所有颜色参数设置为 255，如下所示：rgb(255, 255, 255)。

**RGBA 值**

RGBA 颜色值是具有 alpha 通道的 RGB 颜色值的扩展 - 它指定了颜色的不透明度。

RGBA 颜色值指定为：

 **rgba(*red*, *green*, *blue*, *alpha*)**

*alpha* 参数是介于 0.0（完全透明）和 1.0（完全不透明）之间的数字：

 **HSL 值**

在 CSS 中，可以使用色相、饱和度和明度（HSL）来指定颜色，格式如下：

**hsla(*hue*, *saturation*, *lightness*)**

* 色相（*hue*）是色轮上从 0 到 360 的度数。0 是红色，120 是绿色，240 是蓝色。

* 饱和度（*saturation*）是一个百分比值（颜色强度），0％ 表示完全灰色，而 100％ 是纯色。

* 亮度（*lightness*）也是百分比，0％ 是不亮（黑色），50％ 是既不明也不暗，100％是全明（白色）。

 **HSLA 值**

HSLA 颜色值是带有 Alpha 通道的 HSL 颜色值的扩展 - 它指定了颜色的不透明度。

HSLA 颜色值指定为：

 **hsla(*hue*, *saturation*, *lightness*, *alpha*)**

*alpha* 参数是介于 0.0（完全透明）和 1.0（完全不透明）之间的数字：

## 7 CSS背景

**CSS 背景属性用于定义元素的背景效果。**

CSS背景属性：

* background-color：指定元素的背景色。`background-color: lightblue;`

- background-image：指定用作元素背景的图像。 `background-image: url("paper.gif");`
- background-repeat：指定背景图像是否重复以及重复方向。默认情况下，background-image 属性在水平和垂直方向上都重复图像。`background-repeat: repeat-x;`：水平方向重复，`background-repeat: no-repeat;`：不重复。
- background-attachment：指定背景图像是应该滚动还是固定的（不会随页面的其余部分一起滚动）。`background-attachment: fixed 或者 scroll;`
- background-position：指定背景图像的位置。`background-position: right top;`

**背景简写**

在使用简写属性时，属性值的顺序为：

- background-color
- background-image
- background-repeat
- background-attachment
- background-position

例如：`background: #ffffff url("tree.png") no-repeat right top;`

属性值之一缺失并不要紧，只要按照此顺序设置其他值即可。请注意，在上面的例子中，我们没有使用 background-attachment 属性，因为它没有值。

## 8 CSS边框

**CSS 边框属性**

CSS `border` 属性允许您指定元素边框的样式、宽度和颜色。

**CSS 边框样式**

`border-style` 属性指定要显示的边框类型。

允许以下值：

- `dotted` - 定义点线边框
- `dashed` - 定义虚线边框
- `solid` - 定义实线边框
- `double` - 定义双边框
- `groove` - 定义 3D 坡口边框。效果取决于 border-color 值
- `ridge` - 定义 3D 脊线边框。效果取决于 border-color 值
- `inset` - 定义 3D inset 边框。效果取决于 border-color 值
- `outset` - 定义 3D outset 边框。效果取决于 border-color 值
- `none` - 定义无边框
- `hidden` - 定义隐藏边框

`border-style` 属性可以设置一到四个值（用于上边框、右边框、下边框和左边框）。

**CSS 边框宽度**

`border-width` 属性指定四个边框的宽度。可以设置一到四个值（用于上边框、右边框、下边框和左边框）：

可以将宽度设置为特定大小（以 px、pt、cm、em 计），也可以使用以下三个预定义值之一：thin、medium 或 thick：

**CSS 边框颜色**

`border-color` 属性用于设置四个边框的颜色。可以设置一到四个值（用于上边框、右边框、下边框和左边框）。

可以通过以下方式设置颜色：

- name - 指定颜色名，比如 "red"
- HEX - 指定十六进制值，比如 "#ff0000"
- RGB - 指定 RGB 值，比如 "rgb(255,0,0)"
- HSL - 指定 HSL 值，比如 "hsl(0, 100%, 50%)"
- transparent：默认值，边框透明。

**注释：**如果未设置 `border-color`，则它将继承元素的颜色。

**CSS Border - 简写属性**

就像在前面中所见，为了缩减代码，也可以在一个属性中指定所有单独的边框属性。

`border` 属性是以下各个边框属性的简写属性：

- `border-width`
- `border-style`（必需）
- `border-color`

```css
p {
  border: 5px solid red;
}
```

## 9 CSS 圆角边框

`border-radius` 属性用于向元素添加圆角边框：

 **实例**

```css
p {
  border: 2px solid red;
  border-radius: 5px;
}
```

![image-20220620233242409](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220620233242409.png)

## 10 CSS 外边距

CSS `margin` 属性用于在任何定义的边框之外，为元素周围创建空间。

通过 CSS，您可以完全控制外边距。有一些属性可用于设置元素每侧（上、右、下和左）的外边距。

**Margin - 单独的边**

CSS 拥有用于为元素的每一侧指定外边距的属性：

- `margin-top`
- `margin-right`
- `margin-bottom`
- `margin-left`

所有外边距属性都可以设置以下值：

- auto - 浏览器来计算外边距
- *length* - 以 px、pt、cm 等单位指定外边距
- % - 指定以包含元素宽度的百分比计的外边距
- inherit - 指定应从父元素继承外边距

**提示：**允许负值。

**Margin - 简写属性**

为了缩减代码，可以在一个属性中指定所有外边距属性。

- margin: 25px 50px 75px 100px;   上、右、下、左

## 11 CSS内边距

CSS `padding` 属性用于在任何定义的边界内的元素内容周围生成空间。

通过 CSS，您可以完全控制内边距（填充）。有一些属性可以为元素的每一侧（上、右、下和左侧）设置内边距。

**Padding - 单独的边**

CSS 拥有用于为元素的每一侧指定内边距的属性：

- `padding-top`
- `padding-right`
- `padding-bottom`
- `padding-left`

所有内边距属性都可以设置以下值：

- *length* - 以 px、pt、cm 等单位指定内边距
- % - 指定以包含元素宽度的百分比计的内边距
- inherit - 指定应从父元素继承内边距

**提示：**不允许负值。

Padding - 简写属性

为了缩减代码，可以在一个属性中指定所有内边距属性。

- padding: 25px 50px 75px 100px;  上右下左

## 12 CSS 高度/宽度

`height` 和 `width` 属性用于设置元素的高度和宽度。

**注意：** 

* 只有块元素才可以设置高度宽度。

* height 和 width 属性不包括内边距、边框或外边距。它设置的是元素内边距、边框以及外边距内的区域的高度或宽度。

**设置CSS 高度和宽度值**

`height` 和 `width` 属性可设置如下值：

- `auto` - 默认。浏览器计算高度和宽度。
- `*length*` - 以 px、cm 等定义高度/宽度。
- `%` - 以包含块的百分比定义高度/宽度。
- `initial` - 将高度/宽度设置为默认值。
- `inherit` - 从其父值继承高度/宽度。

**设置 max-width**

`max-width` 属性用于设置元素的最大宽度。

可以用长度值（例如 px、cm 等）或包含块的百分比（％）来指定 max-width（最大宽度），也可以将其设置为 none（默认值。意味着没有最大宽度）。

当浏览器窗口小于元素的宽度（500px）时，会发生之前那个 `<div>` 的问题。然后，浏览器会将水平滚动条添加到页面。

在这种情况下，使用 `max-width` 能够改善浏览器对小窗口的处理。

## 13 CSS框模型

所有 HTML 元素都可以视为方框。在 CSS 中，在谈论设计和布局时，会使用术语“盒模型”或“框模型”。

CSS 框模型实质上是一个包围每个 HTML 元素的框。它包括：外边距、边框、内边距以及实际的内容。下图展示了框模型：

![CSS 框模型](https://www.w3school.com.cn/i/css/boxmodel.gif)

对不同部分的说明：

- **内容** - 框的内容，其中显示文本和图像。
- **内边距** - 清除内容周围的区域。内边距是透明的。
- **边框** - 围绕内边距和内容的边框。
- **外边距** - 清除边界外的区域。外边距是透明的。

框模型允许我们在元素周围添加边框，并定义元素之间的空间。

元素框的最内部分是实际的内容，直接包围内容的是内边距。内边距呈现了元素的背景。内边距的边缘是边框。边框以外是外边距，外边距默认是透明的，因此不会遮挡其后的任何元素。

**提示：**背景应用于由内容和内边距、边框组成的区域。

内边距、边框和外边距都是可选的，默认值是零。

==**元素的总宽度和总高度**==

为了在所有浏览器中正确设置元素的宽度和高度，您需要了解框模型如何工作。

**重要提示：**使用 CSS 设置元素的 width 和 height 属性时，只需设置内容区域的宽度和高度。要计算元素的完整大小，还必须把内边距、边框和外边距加起来。

元素的总宽度应该这样计算：

* 元素总宽度 = 宽度 + 左内边距 + 右内边距 + 左边框 + 右边框 + 左外边距 + 右外边距

元素的总高度应该这样计算：

* 元素总高度 = 高度 + 上内边距 + 下内边距 + 上边框 + 下边框 + 上外边距 + 下外边距

## 14 CSS 轮廓

轮廓是在元素周围绘制的一条线，在边框之外，以凸显元素。

CSS 拥有如下轮廓属性：

- `outline-style`
- `outline-color`
- `outline-width`
- `outline-offset`
- `outline`

**注意：**轮廓与[边框](https://www.w3school.com.cn/css/css_border.asp)不同！不同之处在于：轮廓是在元素边框之外绘制的，并且可能与其他内容重叠。同样，轮廓也不是元素尺寸的一部分；元素的总宽度和高度不受轮廓线宽度的影响。

**CSS 轮廓样式**

outline-style 属性指定轮廓的样式，并可设置如下值：

- `dotted` - 定义点状的轮廓。
- `dashed` - 定义虚线的轮廓。
- `solid` - 定义实线的轮廓。
- `double` - 定义双线的轮廓。
- `groove` - 定义 3D 凹槽轮廓。
- `ridge` - 定义 3D 凸槽轮廓。
- `inset` - 定义 3D 凹边轮廓。
- `outset` - 定义 3D 凸边轮廓。
- `none` - 定义无轮廓。
- `hidden` - 定义隐藏的轮廓。

**CSS 轮廓宽度**

`outline-width` 属性指定轮廓的宽度，并可设置如下值之一：

- thin（通常为 1px）
- medium（通常为 3px）
- thick （通常为 5px）
- 特定尺寸（以 px、pt、cm、em 计）

**CSS 轮廓颜色**

`outline-color` 属性用于设置轮廓的颜色。

可以通过以下方式设置颜色：

- *name* - 指定颜色名，比如 "red"
- HEX - 指定十六进制值，比如 "#ff0000"
- RGB - 指定 RGB 值，比如 "rgb(255,0,0)"
- HSL - 指定 HSL 值，比如 "hsl(0, 100%, 50%)"
- invert - 执行颜色反转（确保轮廓可见，无论是什么颜色背景）

==CSS Outline - 简写属性==

`outline` 属性是用于设置以下各个轮廓属性的简写属性：

- `outline-width`
- `outline-style`（必需）
- `outline-color`

从上面的列表中，`outline` 属性可指定一个、两个或三个值。值的顺序无关紧要。

**CSS 轮廓偏移**

`outline-offset` 属性在元素的轮廓与边框之间添加空间。元素及其轮廓之间的空间是透明的。

## 15 CSS文本

**文本颜色**

`color` 属性用于设置文本的颜色。颜色由以下值指定：

- 颜色名 - 比如 "red"
- 十六进制值 - 比如 "#ff0000"
- RGB 值 - 比如 "rgb(255,0,0)"

**文本对齐**

`text-align` 属性用于设置文本的水平对齐方式。

文本可以左对齐（left）或右对齐（right），或居中对齐（center）。

文本方向

`direction` 和 `unicode-bidi` 属性可用于更改元素的文本方向：

**垂直对齐**

`vertical-align` 属性设置元素的垂直对齐方式。

**文字装饰**

`text-decoration` 属性用于设置或删除文本装饰。

`text-decoration: none;` 通常用于从链接上删除下划线：

**文本转换**

`text-transform` 属性用于指定文本中的大写和小写字母。

它可用于将所有内容转换为大写或小写字母，或将每个单词的首字母大写：

实例

```css
p.uppercase {
  text-transform: uppercase;
}

p.lowercase {
  text-transform: lowercase;
}

p.capitalize {
  text-transform: capitalize;
}
```

**文字缩进**

`text-indent` 属性用于指定文本第一行的缩进：

**字母间距**

`letter-spacing` 属性用于指定文本中字符之间的间距。

**行高**

`line-height` 属性用于指定行之间的间距：

**字间距**

`word-spacing` 属性用于指定文本中单词之间的间距。

**空白**

`white-space` 属性指定元素内部空白的处理方式。

**文本阴影**

`text-shadow` 属性为文本添加阴影。

text-shadow: *h-shadow v-shadow blur color*;

| 值         | 描述                                                         |
| :--------- | :----------------------------------------------------------- |
| *h-shadow* | 必需。水平阴影的位置。允许负值。                             |
| *v-shadow* | 必需。垂直阴影的位置。允许负值。                             |
| *blur*     | 可选。模糊的距离。                                           |
| *color*    | 可选。阴影的颜色。参阅 [CSS 颜色值](https://www.runoob.com/cssref/css-colors-legal.html)。 |

## 16 CSS字体

***字体选择很重要***

选择正确的字体会对网站的用户体验产生巨大影响。

正确的字体可以为您的品牌创造强有力的形象。

使用易于阅读的字体很重要。字体为您的文本增加了价值。为字体选择正确的颜色和文本大小也很重要。

**字体**

`font-family` 属性规定文本的字体。

font-family 属性应包含多个字体名称作为“后备”系统，以确保浏览器/操作系统之间的最大兼容性。请以您需要的字体开始，并以通用系列结束（如果没有其他可用字体，则让浏览器选择通用系列中的相似字体）。字体名称应以逗号分隔。

**注释：**如果字体名称不止一个单词，则必须用引号引起来，例如："Times New Roman"。

**字体样式**

`font-style` 属性主要用于指定斜体文本。

此属性可设置三个值：

- normal - 文字正常显示
- italic - 文本以斜体显示
- oblique - 文本为“倾斜”（倾斜与斜体非常相似，但支持较少）

**字体粗细**

`font-weight` 属性指定字体的粗细：

**字体变体**

`font-variant` 属性指定是否以 small-caps 字体（小型大写字母）显示文本。

在 small-caps 字体中，所有小写字母都将转换为大写字母。但是，转换后的大写字母的字体大小小于文本中原始大写字母的字体大小。

**字体大小**

`font-size` 属性设置文本的大小。

在网页设计中，能够管理文本大小很重要。但是，不应使用调整字体大小来使段落看起来像标题，或是使标题看起来像段落。

请始终使用正确的 HTML 标签，例如 <h1> - <h6> 用于标题，而 <p> 仅用于段落。

font-size 值可以是绝对或相对大小。

绝对尺寸：

- 将文本设置为指定大小
- 不允许用户在所有浏览器中更改文本大小（可访问性不佳）
- 当输出的物理尺寸已知时，绝对尺寸很有用

相对尺寸：

- 设置相对于周围元素的大小
- 允许用户在浏览器中更改文本大小

**注释：**如果您没有指定字体大小，则普通文本（如段落）的默认大小为 16px（16px = 1em）。

**简写字体属性**

为了缩短代码，也可以在一个属性中指定所有单个字体属性。

`font` 属性是以下属性的简写属性：

- `font-style`
- `font-variant`
- `font-weight`
- `font-size/line-height`
- `font-family`

**注意：**`font-size` 和 `font-family` 的值是必需的。如果缺少其他值之一，则会使用其默认值。

## 17 CSS图标

向 HTML 页面添加图标的最简单方法是使用图标库，比如 Font Awesome。

将指定的图标类的名称添加到任何行内 HTML 元素（如 \<i> 或 \<span>）。

下面的图标库中的所有图标都是可缩放矢量，可以使用 CSS进行自定义（大小、颜色、阴影等）。

![image-20220621000306675](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220621000306675.png)

 **Font Awesome 图标**

如需使用 Font Awesome 图标，请访问 fontawesome.com，登录并获取代码添加到 HTML 页面的 <head> 部分：

```html
<script src="https://kit.fontawesome.com/yourcode.js"></script>
```

**Bootstrap 图标**

如需使用 Bootstrap glyphicons，请在 HTML 页面的 <head> 部分内添加这行：

```html
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css">
```

**提示：**无需下载或安装！

**Google 图标**

如需使用 Google 图标，请在HTML页面的 <head> 部分中添加以下行：

```html
<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons">
```

**提示：**无需下载或安装！

## 18 CSS 链接

通过 CSS，可以用不同的方式设置链接的样式。

**设置链接样式**

链接可以使用任何 CSS 属性（例如 `color`、`font-family`、`background` 等）来设置样式。

实例

```css
a {
  color: hotpink;
}
```

此外，可以根据链接处于什么状态来设置链接的不同样式。

四种链接状态分别是：

- `a:link` - 正常的，未访问的链接
- `a:visited` - 用户访问过的链接
- `a:hover` - 用户将鼠标悬停在链接上时
- `a:active` - 链接被点击时

如果为多个链接状态设置样式，请遵循如下顺序规则：

- a:hover 必须 a:link 和 a:visited 之后
- a:active 必须在 a:hover 之后

**文本装饰**

`text-decoration` 属性主要用于从链接中删除下划线：

 **背景色**

`background-color` 属性可用于指定链接的背景色：

# CSS 中级

## 1 CSS display属性

`display` 属性是用于控制布局的最重要的 CSS 属性。

`display` 属性规定是否/如何显示元素。

每个 HTML 元素都有一个默认的 display 值，具体取决于它的元素类型。大多数元素的默认 display 值为 `block` 或 `inline`。

**块级元素（block element）**

块级元素总是从新行开始，并占据可用的全部宽度（尽可能向左和向右伸展）。

块级元素的一些例子：

- \<div>
- \<h1> - \<h6>
- \<p>
- \<form>
- \<header>
- \<footer>
- \<section>

**行内元素（inline element）**

内联元素不从新行开始，仅占用所需的宽度。

这是段落中的行内 \<span> 元素。

行内元素的一些例子：

- \<span>
- \<a>
- \<img>

**Display: none;**

`display: none;` 通常与 JavaScript 一起使用，以隐藏和显示元素，而无需删除和重新创建它们。如果您想知道如何实现此目标，请查看本页面上的最后一个实例。

默认情况下，`<script>` 元素使用 `display: none;`。

**覆盖默认的 Display 值**

每个元素都有一个默认 display 值。但是，您可以覆盖它。

将行内元素更改为块元素，反之亦然

**注意：**设置元素的 display 属性仅会更改元素的显示方式，而不会更改元素的种类。因此，带有 `display: block;` 的行内元素不允许在其中包含其他块元素。

**隐藏元素 - display:none还是 visibility:hidden**

通过将 `display` 属性设置为 `none` 可以隐藏元素。该元素将被隐藏，并且页面将显示为好像该元素不在其中：

`visibility: hidden;` 也可以隐藏元素。但是，该元素仍将占用与之前相同的空间。元素将被隐藏，但仍会影响布局：

## 2 CSS 布局 - width 和 max-width

## 使用 width、max-width 和 margin: auto;

如上一章所述，块级元素始终占用可用的全部宽度（尽可能向左和向右伸展）。

设置块级元素的 `width` 将防止其延伸到其容器的边缘。然后，您可以将外边距设置为 auto，以将元素在其容器中水平居中。元素将占用指定的宽度，剩余空间将在两个外边距之间平均分配：

![image-20220624210203052](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624210203052.png)

**注意：**当浏览器窗口小于元素的宽度时，上面这个 `<div>` 会发生问题。浏览器会将水平滚动条添加到页面。

在这种情况下，使用 `max-width` 可以改善浏览器对小窗口的处理。为了使网站在小型设备上可用，这一点很重要：

![image-20220624210209886](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624210209886.png)

**提示：**请将浏览器窗口的大小调整为小于 500 像素，以查看两个 div 之间的区别！

## 3 CSS position定位

**position 属性**

`position` 属性规定应用于元素的定位方法的类型。

有五个不同的位置值：

- static
- relative
- fixed
- absolute
- sticky

元素其实是使用 top、bottom、left 和 right 属性定位的。但是，除非首先设置了 position 属性，否则这些属性将不起作用。

根据不同的 position 值，它们的工作方式也不同。

**position: static;**

HTML 元素默认情况下的定位方式为 static（静态）。

静态定位的元素不受 top、bottom、left 和 right 属性的影响。

position: static; 的元素不会以任何特殊方式定位；它始终根据页面的正常流进行定位：

**position: relative;**

`position: relative;` 的元素相对于其正常位置进行定位。

设置相对定位的元素的 top、right、bottom 和 left 属性将导致其偏离其正常位置进行调整。不会对其余内容进行调整来适应元素留下的任何空间。

**position: fixed;**

`position: fixed;` 的元素是相对于视口定位的，这意味着即使滚动页面，它也始终位于同一位置。 top、right、bottom 和 left 属性用于定位此元素。

固定定位的元素不会在页面中通常应放置的位置上留出空隙。

**position: absolute;**

`position: absolute;` 的元素相对于最近的定位祖先元素进行定位（而不是相对于视口定位，如 fixed）。

然而，如果绝对定位的元素没有祖先，它将使用文档主体（body），并随页面滚动一起移动。

**注意：**“被定位的”元素是其位置除 `static` 以外的任何元素。

**position: sticky;**

`position: sticky;` 的元素根据用户的滚动位置进行定位。

粘性元素根据滚动位置在相对（`relative`）和固定（`fixed`）之间切换。起先它会被相对定位，直到在视口中遇到给定的偏移位置为止 - 然后将其“粘贴”在适当的位置（比如 position:fixed）。

**重叠元素**

在对元素进行定位时，它们可以与其他元素重叠。

`z-index` 属性指定元素的堆栈顺序（哪个元素应放置在其他元素的前面或后面）。

元素可以设置正或负的堆叠顺序。

基本默认 z-index为 0，具体看每个浏览器情况。

## 4 CSS overflow溢出

**CSS Overflow**

`overflow` 属性指定在元素的内容太大而无法放入指定区域时是剪裁内容还是添加滚动条。

`overflow` 属性可设置以下值：

- `visible` - 默认。溢出没有被剪裁。内容在元素框外渲染
- `hidden` - 溢出被剪裁，其余内容将不可见
- `scroll` - 溢出被剪裁，同时添加滚动条以查看其余内容
- `auto` - 与 `scroll` 类似，但仅在必要时添加滚动条

**注释：**`overflow` 属性仅适用于具有指定高度的块元素。

**注释：**在 OS X Lion（在 Mac 上）中，滚动条默认情况下是隐藏的，并且仅在使用时显示（即使设置了 "overflow:scroll"）。

**overflow: visible**

默认情况下，溢出是可见的(`visible`)，这意味着它不会被裁剪，而是在元素框外渲染：

![image-20220624210943055](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624210943055.png)

**overflow: hidden**

如果使用 `hidden` 值，溢出会被裁剪，其余内容被隐藏：

![image-20220624211110082](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624211110082.png)

**overflow: scroll**

如果将值设置为 `scroll`，溢出将被裁剪，并添加滚动条以便在框内滚动。请注意，这将在水平和垂直方向上添加一个滚动条（即使您不需要它）：

![image-20220624211126590](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624211126590.png)

**overflow: auto**

`auto` 值类似于 `scroll`，但是它仅在必要时添加滚动条：

![image-20220624211143652](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624211143652.png)

**overflow-x 和 overflow-y**

`overflow-x` 和 `overflow-y` 属性规定是仅水平还是垂直地（或同时）更改内容的溢出：

- `overflow-x` 指定如何处理内容的左/右边缘。
- `overflow-y` 指定如何处理内容的上/下边缘。

![image-20220624211205420](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624211205420.png)

## 5 CSS float浮动 和 clear、clearfix清除浮动

CSS `float` 属性规定元素如何浮动。

**float 属性**

`float` 属性用于定位和格式化内容，例如让图像向左浮动到容器中的文本那里。

`float` 属性可以设置以下值之一：

- left - 元素浮动到其容器的左侧
- right - 元素浮动在其容器的右侧
- none - 元素不会浮动（将显示在文本中刚出现的位置）。默认值。
- inherit - 元素继承其父级的 float 值

最简单的用法是，`float` 属性可实现（报纸上）文字包围图片的效果。

**clear 属性**

`clear` 属性指定哪些元素可以浮动于被清除元素的旁边以及哪一侧。

`clear` 属性可设置以下值之一：

- none - 允许两侧都有浮动元素。默认值
- left - 左侧不允许浮动元素
- right- 右侧不允许浮动元素
- both - 左侧或右侧均不允许浮动元素
- inherit - 元素继承其父级的 clear 值

使用 `clear` 属性的最常见用法是在元素上使用了 `float` 属性之后。

在清除浮动时，应该对清除与浮动进行匹配：如果某个元素浮动到左侧，则应清除左侧。您的浮动元素会继续浮动，但是被清除的元素将显示在其下方。

**clearfix Hack**

如果一个元素比包含它的元素高，并且它是浮动的，它将“溢出”到其容器之外：

然后我们可以向包含元素添加 overflow: auto;，来解决此问题：

```css
.clearfix {
  overflow: auto;
}
```

![image-20220624211729225](https://images-diyu.obs.cn-east-3.myhuaweicloud.com/typora/image-20220624211729225.png)

只要您能够控制外边距和内边距（否则您可能会看到滚动条），overflow: auto clearfix 就会很好地工作。但是，新的现代 clearfix hack 技术使用起来更安全，以下代码被应用于多数网站：

```css
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
```

## 6 CSS inline-block

**display: inline-block**

与 `display: inline` 相比，主要区别在于 `display: inline-block` 允许在元素上设置宽度和高度。

同样，如果设置了 display: inline-block，将保留上下外边距/内边距，而 display: inline 则不会。

与 display: block 相比，主要区别在于 display：inline-block 在元素之后不添加换行符，因此该元素可以位于其他元素旁边。

## 7 CSS 对齐

**居中对齐元素**

要使块元素（例如 \<div> ）水平居中，请使用 `margin: auto;`。

设置元素的宽度将防止其延伸到容器的边缘。

然后，元素将占用指定的宽度，剩余空间将在两个外边距之间平均分配。

```css
.center {
  margin: auto;
  width: 50%;
  border: 3px solid green;
  padding: 20px;
}
```

**注意：**如果未设置 `width` 属性（或将其设置为 100％），则居中对齐无效。

**居中对齐文本**

如果仅需在元素内居中文本，请使用 `text-align: center;`：

```css
.center {
  text-align: center;
  border: 3px solid green;
}
```

**居中对齐图像**

如需居中图像，请将左右外边距设置为 `auto`，并将其设置为块元素：

```css
img {
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 40%;
}
```

**左和右对齐 - 使用 position**

对齐元素的一种方法是使用 `position: absolute;` :

```css
.right {
  position: absolute;
  right: 0px;
  width: 300px;
  border: 3px solid #73AD21;
  padding: 20px;
}
```

**注意：**绝对定位的元素将从正常流中删除，并可能出现元素重叠。

**左和右对齐 - 使用 float**

对齐元素的另一种方法是使用 `float` 属性：

```css
.right {
  float: right;
  width: 300px;
  border: 3px solid #73AD21;
  padding: 10px;
}
```

**注意：**如果一个元素比包含它的元素高，并且它是浮动的，它将溢出其容器。您可以使用 *clearfix hack* 来解决此问题

**clearfix Hack**

然后我们可以向包含元素添加 `overflow: auto;`，来解决此问题：

```css
.clearfix {
  overflow: auto;
}
```

**垂直对齐**

- 使用 padding。同时垂直和水平对齐，请使用 `padding` 和 `text-align: center;`：

* 使用 line-height。另一个技巧是使用其值等于 `height` 属性值的 `line-height` 属性：

* 使用 position 和 transform。如果您的选择不是 `padding` 和 `line-height`，则另一种解决方案是使用 `position` 和 `transform` 属性：

## 8 CSS组合器

**CSS 组合器**

组合器是解释选择器之间关系的某种机制。

CSS 选择器可以包含多个简单选择器。在简单选择器之间，我们可以包含一个组合器。

CSS 中有四种不同的组合器：

- 后代选择器 (空格)
- 子选择器 (`>`)
- 相邻兄弟选择器 (`+`)
- 通用兄弟选择器 (`~`)

**后代选择器**

后代选择器匹配属于指定元素后代的所有元素。

下面的例子选择 \<div> 元素内的所有 \<p> 元素：

```css
div p {
  background-color: yellow;
}
```

**子选择器**

子选择器匹配属于指定元素子元素的所有元素。

下面的例子选择属于 \<div> 元素子元素的所有 \<p> 元素：

```css
div > p {
  background-color: yellow;
}
```

**相邻兄弟选择器**

相邻兄弟选择器匹配所有作为指定元素的相邻同级的元素。

兄弟（同级）元素必须具有相同的父元素，“相邻”的意思是“紧随其后”。

下面的例子选择紧随 \<div> 元素之后的所有 \<p> 元素：

```css
div + p {
  background-color: yellow;
}
```

**通用兄弟选择器**

通用兄弟选择器匹配属于指定元素的同级元素的所有元素。

下面的例子选择属于 \<div> 元素的同级元素的所有 \<p> 元素：

```css
div ~ p {
  background-color: yellow;
}
```

## 9 CSS伪类

伪类用于定义元素的特殊状态。

例如，它可以用于：

- 设置鼠标悬停在元素上时的样式
- 为已访问和未访问链接设置不同的样式
- 设置元素获得焦点时的样式

**锚伪类**

链接能够以不同的方式显示：

```css
/* 未访问的链接 */
a:link {
  color: #FF0000;
}

/* 已访问的链接 */
a:visited {
  color: #00FF00;
}

/* 鼠标悬停链接 */
a:hover {
  color: #FF00FF;
}

/* 已选择的链接 */
a:active {
  color: #0000FF;
}
```

**注意：**`a:hover` 必须在 CSS 定义中的 `a:link` 和 `a:visited` 之后，才能生效！`a:active` 必须在 CSS 定义中的 `a:hover` 之后才能生效！伪类名称对大小写不敏感。

**CSS - :first-child 伪类**

`:first-child` 伪类与指定的元素匹配：该元素是另一个元素的第一个子元素。

在下面的例子中，选择器匹配作为任何元素的第一个子元素的任何 \<p> 元素：

```css
p:first-child {
  color: blue;
}
```

**匹配所有 \<p> 元素中的首个 \<i> 元素**

在下面的例子中，选择器匹配所有 \<p> 元素中的第一个 \<i> 元素：

```css
p i:first-child {
  color: blue;
}
```

**匹配所有首个 \<p> 元素中的所有 \<i> 元素**

在下面的例子中，选择器匹配作为另一个元素的第一个子元素的 \<p> 元素中的所有 \<i> 元素：

```css
p:first-child i {
  color: blue;
}
```

更多伪类：[CSS 伪类 (w3school.com.cn)](https://www.w3school.com.cn/css/css_pseudo_classes.asp)

## 10 伪元素

CSS 伪元素用于设置元素指定部分的样式。

例如，它可用于：

- 设置元素的首字母、首行的样式
- 在元素的内容之前或之后插入内容

**::first-line 伪元素**

`::first-line` 伪元素用于向文本的首行添加特殊样式。

**::first-letter 伪元素**

`::first-letter` 伪元素用于向文本的首字母添加特殊样式。

**::before 伪元素**

`::before` 伪元素可用于在元素内容之前插入一些内容。

**::after 伪元素**

`::after` 伪元素可用于在元素内容之后插入一些内容。

**::selection 伪元素**

`::selection` 伪元素匹配用户选择的元素部分。

