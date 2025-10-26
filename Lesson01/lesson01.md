# 0.前导

在前一节课程的学习中，我们学习了HTML，并且能够使用HTML制作一些简单的页面，例如：

![img](https://raw.githubusercontent.com/Senyu2333/pic/master/asynccode)

但是，你看到的这些样式就是浏览器的**默认样式**——非常基础的样式，用于确保即使页面作者没有指定样式，网页也能保持可读性。这些样式由浏览器内置的默认 CSS 样式表定义，与 HTML 本身无关。如果所有网站都长得像这样，web 将变得非常无趣。

这就是我们要学习CSS的原因——通过 CSS，可以精确控制 HTML 元素在浏览器中的外观，以你喜欢的设计和布局呈现文档。

CSS（Cascading Style Sheets）即**层叠样式表**，是一种用来为结构化文档（如 HTML 文档或 XML 应用）添加样式的语言。

# 1.规则

CSS 是一种基于规则的语言——通过定义一组样式规则来指定网页上哪些元素应该应用哪些样式。

**语法：****selector** **{ property : value; }**

“;”，可删去但不建议删去！便于继续扩展！

其中，

**selector**，即选择器，是用于选择要应用样式的HTML元素，

**property**，即属性，是期望设置的样式属性，

**value**，即值，是期望设置的样式属性的值，

# 2.引入

插入CSS的方法有三种：**外部样式表、内部样式表、内联样式。**

## 2.1.外部样式表(External style sheet)

这是一种把 CSS 独立成 .css 文件、再在 HTML 里引用的方式。

**语法：**

在<head>标签里引入<link>标签：

```HTML
<head>
<link rel="stylesheet" href="CSS的目标地址">
</head>
```

**rel="stylesheet"**：固定写法，告诉浏览器这是一份样式表

**href****：**指向**CSS** **文件路径**（相对/绝对/URL 均可）

## 2.2.内部样式表(Internal style sheet)

这是把CSS写在**当前****HTML****文档**里的<style> 标签中的方式，即此方式引入的CSS代码只作用于本页。

**语法：**

在<head>标签里引入<style>标签,并在<style>标签里书写CSS：

```HTML
<head>
<style>
 /* CSS */
</style>
</head>
```

## 2.3.内联样式(Inline style)

内联样式是把CSS 直接写到元素的style属性里的方式，只影响该元素本身。

**语法：**

在标签内的style属性里直接书写CSS：

```HTML
<标签名 style="property:value;">
```

# 3.选择器

选择器用来指定网页上我们想要样式化的HTML元素。有 CSS 选择器提供了很多种方法，所以在选择要样式化的元素时，我们可以做到很精细的地步。选择器是一段模式（pattern），用来在元素树（DOM）中筛选目标元素集合，然后把规则块里的声明（{ ... }）应用到这些元素上。 

## 3.1.基础选择器

基础选择器是由单个选择器组成的，主要包括：**标签选择器**、**类选择器**、**id 选择器**和**通配符选择器**。

### 3.1.1.元素选择器

元素选择器用于将HTML的标签元素作为选择器，能快速为页面中同类型的元素统一设置样式，但不能设计差异化样式。

语法：标签名：p、div、h1、ul、li、button …

```CSS
p{
    color:red;
}
```

### 3.1.2.类选择器

类选择器可以用于给多个HTML元素设置相同的样式，也可以给一个元素指定多个类名，从而达到更多的选择目的。

语法：

1. 先给元素设置类名

```HTML
<p class="red-p">这里的段落是红色的</p>
<p class="blue-p big-p">这里的段落又蓝又大</p>
```

1. 声明CSS，注意类选择器以" . " 进行标识

```CSS
.red-p{
color:red;
}

.blue-p{
color:blue;
}

.big-p{
font-size:50px;
}
```

### 3.1.3.id选择器

id选择器可以为标有特定 id 的 HTML 元素指定特定的样式，与类选择器不同的是，**id属性唯一**。文档中必须唯一（按规范）；重复会造成选择器行为不可靠。而class可在多个元素上复用。

语法：

1. 先给元素设置id：

```HTML
<p id="green-p">这是绿色段落</p>
```

1. 声明CSS，注意id选择器用‘#’标识

```CSS
#green-p{
color:green;
}
```

### 3.1.4.通配符选择器

通配符选择器使用 " * " 定义，它表示选取页面中所有元素，很少进行使用。

语法：

声明CSS即可：

```CSS
*{
color:red
}
```

## 3.2.复合选择器

复合选择器是建立在基础选择器之上，由两个或多个基础选择器，通过不同的方式组合而成的。 常用的复合选择器包括：**后代选择器、子选择器、并集选择器、****伪类****选择器等**。

### 3.2.1.后代选择器

后代选择器又称为包含选择器，可以选择父元素里面子元素。

语法：

element1 element2 { property:value; }

```CSS
/* 选择 div 里面所有的 p 标签元素 */
div p{color:red;}
```

### 3.2.2.子选择器

子选择器与后代选择器类似，可以选择父元素里面子元素，但是只能选择**最近一级子元素**。

语法：

```CSS
/* 选择 div 里面第一级 p 标签元素 */
div>p{color:red;}
```

也就是子类的子类不是我的子类，不能跨级选择。

### 3.2.3.并集选择器

并集选择器是指用 逗号（,） 将多个选择器连接在一起，这样可以同时对这些选择器所选中的元素应用同一组样式规则。

语法：

```CSS
/*元素1,元素2,元素3 { 样式声明 } */
div,.myclass,#psd { property:value; }
```

### 3.2.4.伪类和伪元素选择器

伪类（Pseudo-class）用于选择元素的“状态”或“位置”，比如鼠标悬停、表单校验状态、在同辈中的序号等。语法是单冒号 :

伪元素（Pseudo-element）用于选择元素内容中的“部分”，比如首字、首行、选中文本、生成内容等。语法是双冒号 ::（兼容写法 :before / :after 仍被广泛支持）。

伪类用于选择已有元素的特殊状态，而伪元素用于选取元素内容的一部分（如首行、首字），或生成额外内容.因此，伪类与伪元素的区别在于：有没有创建一个文档树之外的元素。故伪类和伪元素选择器往往不是单独出现的，而是和其他选择器一起出现。

![image](https://raw.githubusercontent.com/Senyu2333/pic/master/image.png)

# 4.性质

前文我们提到CSS的全称是层叠样式表，其中层叠的表现，就是我们理解CSS的关键。

有时候，我们会发现一些应该产生效果的样式没有生效，其中最可能的原因就是你创建了两个应用于同一个元素的规则。

## 4.1.层叠

CSS规则的顺序很重要，浏览器会按源顺序(source order)解析CSS，并在CSSOM保留这个顺序。于是，当两个同一级别的样式要应用到同一元素上时，写在后面的规则会被实际应用。

那不同一级别的呢？

## 4.2.优先级

对于不同一级别的样式，浏览器会根据它们的**优先级**(specificity)，应用高优先级的样式。本质上，不同类型的选择器有不同的分数，把这些分数相加之后就能得到选择器优先级的权重，从而匹配样式。

### 4.2.1.优先级权重

我们用一个**四元数组(a,b,c,d)**表示，比较时从左到右逐位比大小，数字大的就更优先，如果相等的话就继续看下一位。

| 维度 | 来源                  |
| ---- | --------------------- |
| a    | 行内样式              |
| b    | id选择器数量          |
| c    | 类/伪类选择器数量     |
| d    | 元素/伪元素选择器数量 |

### 4.2.2.!important

!important可以覆盖优先级计算。但是，不到非常情况不要使用，因为他忽略普通规则的层叠，使得调试CSS异常困难，尤其是大型项目。

**用法：****selector****{property:value!important;}**

**覆盖 !important 唯一的办法就是另一个 !important 具有相同优先级而且顺序靠后，或者更高优先级。**

# 5.盒模型

在 CSS 中，所有的元素都被一个个的“盒子”包围着。一个盒子是由四部分组成的：内容（content）、内边框（padding）、边框（border）和外边框（margin）。

![image1](https://raw.githubusercontent.com/Senyu2333/pic/master/image1.png)

盒模型有两种：**标准盒模型（content-box）** 和**IE盒模型（border-box）**

## 5.1.标准盒模型

标准盒模型是现代浏览器的默认盒模型，**它的width/height 只指内容区 content**。

![image2](https://raw.githubusercontent.com/Senyu2333/pic/master/image2.png)

**内容盒宽**：contentWidth = width

**边框盒宽**：borderBoxWidth = width + padding+ border

**实际占用宽**：outerWidth = borderBoxWidth + margin

## 5.2.IE盒模型

当容器的box-sizing属性为border-box时，使用此模型。

![image3](https://raw.githubusercontent.com/Senyu2333/pic/master/image3.png)

**边框盒宽**：borderBoxWidth = width

**内容盒宽**：contentWidth = width - padding - border

**实际占用宽**：outerWidth = width + margin

## 5.3.元素分类

我们使用的元素一般有三种类型：**块级元素，行内元素，行内块元素**

### 5.3.1.块级元素

每个块元素通常都会独自占据**一整行或多整行**，可以对其设置宽度、高度、对齐等属性、常用于网页布局和网页结构的搭建

特点：

- 总是从新行开始。
- 高度、行高、外边距以及内边距都可以控制。
- 宽度默认是容器的100%。
- 可以容纳内联元素和其他块元素。

常见的块元素：

<**h1**>~<**h6**>、<**p**>、<**div**>、<**ul**>、<**ol**>、<**li**>

### 5.3.2.行内元素

行内元素(内联元素)不占有独立的区域,仅仅靠自身的字体大小和图像尺寸来支撑结构，一般不可以设置宽度，高度，对齐等属性，常用于控制页面中文本的样式。

特点：

- 和相邻行元素在一行上。
- 高、宽设置无效，但水平方向的padding和margin可以设置，垂直方向的无效。
- 默认宽度就是它本身内容的宽度。
- 行内元素只能容纳文本或者其他行内元素。(a特殊，容纳链接)

常见的行内元素:

<a>、<strong>、<b>、<em>、<i>、<del>、<s>、<span>、<u>、<ins>

### 5.3.3.行内块元素(特殊的行内元素)

在行内元素中有几个特殊的标签 <img>、<input>、 <td>,可以对他们设置宽高和对齐属性，有些资料可能会称它们为行内块元素。

特点：

- 和相邻行内元素(行内块)在一行上，但是之间会有空白缝。
- 默认宽度就是它本身内部的宽度。
- 高度、行高、外边距以及内边距都可以控制。

### 5.3.4.显示模式转换

display属性允许我们更改默认的显示方式。正常流中的所有内容都有一个display的值，用作元素的默认行为方式。

| 值           | 特点         |
| ------------ | ------------ |
| block        | 块级模式     |
| inline       | 行内标签模式 |
| inline-block | 行内块模式   |

# 6.属性

这部分我不作赘叙，大部分一般在页面中用不到，需要大家自行实践了解。

> 不好好学的人，之后一定会被Tailwind CSS拷打的!

## 6.1.背景

背景属性用于定义HTML元素的背景。

| 属性                      | 取值                                                         | 说明                                                         |
| ------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| **background-color**      | 任意颜色值：`red`、`#fff`、`rgb(255,0,0)`、`hsl(0,100%,50%)`、`transparent` 等 | **作用**：设置元素的背景颜色，会铺满元素背景绘制区域（包括内边距）。**默认值**：`transparent`（透明） |
| **background-image**      | `url('图片路径')`、`linear-gradient(...)`、`none`            | **作用**：设置一个或多个背景图层。可多层，用逗号分隔；后写的在下层，先写的在上层。**默认值**：`none` |
| **background-repeat**     | `repeat`（默认）`no-repeatrepeat-xrepeat-yspaceround`        | **作用**：控制背景图如何平铺。**默认值**：`repeat`（横纵方向都平铺） |
| **background-attachment** | `scroll`（默认）`fixedlocal`                                 | **作用**：决定背景图相对于哪个滚动容器固定。- `scroll`：随页面滚动- `fixed`：相对视口固定- `local`：随元素内容滚动**默认值**：`scroll` |
| **background-position**   | 关键字：`left`、`center`、`right`、`top`、`bottom`或长度/百分比：`<x> <y>`（如 `50% 50%`） | **作用**：设置背景图的起始定位（锚点），决定图像放置的位置。**默认值**：`0% 0%`（等同于 `left top`） |

## 6.2.文本

| 属性                       | 取值                                                  | 说明                                                         |
| -------------------------- | ----------------------------------------------------- | ------------------------------------------------------------ |
| color                      | 颜色值：#333、rgb()、hsl()、currentColor              | 作用：设置文本颜色（可继承）。 默认值：浏览器默认颜色（通常接近黑色）。 |
| text-align                 | left、right、center、justify、start、end              | 作用：设置文本水平对齐方式。 默认值：start（多数环境表现为 left）。 |
| line-height                | normal、数值（如 1.5）、长度、百分比                  | 作用：设置行高，控制行距（可继承）。 默认值：normal。        |
| letter-spacing             | normal、长度（如 2px、0.1em）                         | 作用：设置字符间距。 默认值：normal。                        |
| word-spacing               | normal、长度                                          | 作用：设置单词之间的间距。 默认值：normal。                  |
| text-indent                | 长度或百分比                                          | 作用：设置段落首行缩进。 默认值：0。                         |
| text-transform             | none、capitalize、uppercase、lowercase                | 作用：控制文本大小写格式。 默认值：none。                    |
| white-space                | normal、nowrap、pre、pre-wrap、pre-line、break-spaces | 作用：控制空白字符与换行的处理方式。 默认值：normal。        |
| word-break                 | normal、break-all、keep-all、break-word               | 作用：控制单词换行规则。 默认值：normal。                    |
| overflow-wrap（word-wrap） | normal、break-word、anywhere                          | 作用：指定当单词太长时是否允许断行换行。 默认值：normal。    |
| text-overflow              | clip、ellipsis                                        | 作用：定义文本溢出时的显示方式（如省略号），需配合 overflow:hidden; white-space:nowrap 使用。 默认值：clip。 |
| vertical-align             | baseline、top、middle、bottom、长度、百分比           | 作用：设置行内元素或单元格内容的垂直对齐方式。 默认值：baseline。 |
| text-shadow                | 水平偏移 垂直偏移 模糊半径 颜色                       | 作用：给文本添加阴影效果，可叠加多个阴影，用逗号分隔。 默认值：none。 |
| direction                  | ltr、rtl                                              | 作用：设置文本的书写方向。 默认值：ltr。                     |
| writing-mode               | horizontal-tb、vertical-rl、vertical-lr               | 作用：定义文字的书写方向和排列方式（横排/竖排）。 默认值：horizontal-tb。 |
| hyphens                    | none、manual、auto                                    | 作用：控制单词是否自动断字加连字符（需语言支持）。 默认值：manual。 |
| text-decoration            | none、underline、overline、line-through、blink        | 作用：设置文本装饰线，可组合使用。 默认值：none。            |
| tab-size                   | 整数或长度值                                          | 作用：定义制表符（Tab）宽度，等效于空格数。  默认值：8。     |
| caret-color                | 颜色值或 auto                                         | 作用：设置文本输入光标颜色。 默认值：auto。                  |

## 6.3.边框

| 属性                               | 取值                                                         | 说明                                                         |
| ---------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| border（简写）                     | 如 1px solid #ccc（等价于 border-width style color）         | 作用：一次性设置边框宽度、样式、颜色。 默认值：medium none currentColor。 |
| border-width                       | thin / medium / thick / 长度（如 1px）                       | 作用：设置边框宽度（可分别对四边）。 默认值：medium。        |
| border-style                       | none / solid / dashed / dotted / double / groove / ridge / inset / outset | 作用：设置边框线型（可分别对四边）。 默认值：none。          |
| border-color                       | 颜色值 / transparent / currentColor                          | 作用：设置边框颜色（可分别对四边）。 默认值：currentColor。  |
| border-top / right / bottom / left | 如 2px dashed #f90                                           | 作用：分别设置单侧边框（宽度/样式/颜色）。 默认值：medium none currentColor。 |
| border-block / inline（逻辑方向）  | 如 1px solid #ddd                                            | 作用：按书写模式设置块向/行向边框（对应物理上下/左右）。 默认值：medium none currentColor。 |
| border-radius                      | 单值：8px；四值：8px 8px 8px 8px；椭圆：8px / 12px           | 作用：设置圆角（可分别设四角：border-top-left-radius 等）。 默认值：0。 |
| border-image（简写）               | source slice / width / outset repeat（如：url(frame.png) 30 fill / 10px / 0 round） | 作用：用图片绘制边框，支持切片、缩放、重复方式。 默认值：none 100% 1 0 stretch（等价各子属性默认）。 |
| border-image-source                | url(...) / none                                              | 作用：指定边框图像来源。 默认值：none。                      |
| border-image-slice                 | 数值 / 百分比 / fill                                         | 作用：定义从图像四边切多宽进入（可选 fill 填充中间）。默认值：100%。 |
| border-image-width                 | 数值 / 百分比 / 长度 / auto                                  | 作用：边框图片占据的边框宽度。 默认值：1。                   |
| border-image-outset                | 数值 / 长度                                                  | 作用：边框图片向外扩出的距离。 默认值：0。                   |
| border-image-repeat                | stretch / repeat / round / space                             | 作用：边框图片在各边的平铺/拉伸方式。 默认值：stretch。      |
| outline（轮廓，非边框）            | 如 2px solid #4c9                                            | 作用：绘制在边框外、不占布局的轮廓线（不参与圆角裁剪）。 默认值：medium none currentColor。 |
| outline-offset                     | 长度（可正可负）                                             | 作用：轮廓与边框之间的距离。 默认值：0。                     |

