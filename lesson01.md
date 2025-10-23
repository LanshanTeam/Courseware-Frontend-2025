# 为什么要学HTML
> 把软件比作一个人，分为三部分，身体，衣装打扮，能够交流互动的行为，我们平常使用的像网页App都是如此，身体实际上就是结构，衣装打扮就是样式，交流互动也就是交互，也就分别对应我们的html,css,js。


网页的结构搭建其实像俄罗斯方块一样
![俄罗斯方块](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/1.png)
如果你会搭俄罗斯方块，那么搭网页也是同样的一个道理，html就是用来前端搭建网页骨架（结构）的一种工具
![网页骨架](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/017a86da-23b3-4abb-8e47-9f116cf2b58c.png)

# 了解HTML
### 什么是HTML
HTML全称Hyper Text Markup Language, 翻译成中文就是 超文本标记语言，是一种最基础的网页开发语言, 需要注意的是HTML并不是编程语言, 而是一种标记语言

 1. **超文本** 可以理解为超越了文本的意思，也就是超越文本，超文本不止是普通的文本内容，还可以加入图片，视频，声音等内容，甚至可以从一个文件跳转到另一个文件（超链接文本）
 2. **标记语言** 可以理解为一套标记标签，也就是由许多标记组成的语言
 3. **作用** 告诉浏览器如何构造网页
### 这节课的目标
html实际上不属于一种编程语言，所有它的门槛相较于其他编程语言来说更低一些，这也是我们前端学习的优点，易于上手。但同时，html有很多标签在日常开发中用不到。笔者希望通过这节课，能帮助学习前端的小伙伴，能够学习html一些比较常用的标签，从而缩短一些学习压力，而一些不常用的标签，这个文档则不作过多赘述，可以在遇见后查询“mdn中文文档”以及一些文档来快速学习用法。
# 前置准备
### VSCode的使用
首先打开我们的前端开发软件vscode
点击左上角文件，新建一个文件夹，用于我们的课程相关，然后再在这个文件下创建一个html文件（注意后缀一定是要为html）
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/3.png)  
进入这个页面后，我们按下" ! "，再按下tap键就会自动生成我们html的骨架
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/4.png)
>**VSCode的使用**
>①双击打开软件
>②新建一个html文件（Ctrl + N）
>③Ctrl + 加号键，Ctrl + 减号键 可以放大缩小视图
>④生成页面骨架结构，输入"!"按下tap键
### 插件安装
VSCode作为我们前端常用的一个软件，得益于其中丰富的插件功能
按下Ctrl + Shift + X 进入插件安装页面，确保你已经安装以下几个插件
1. **Chinese（Simplified）**
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/5.png)
2. **Live Server 实时预览**
 ![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/6.png)
这个插件可以帮助预览页面，我们在编译器中编写完代码后，网页就会自动刷新更新浏览器，将我们的修改展现出来，在当前html点击鼠标右键，会看见 open with Live Server，即可打开网页
>小技巧：
在刚开始学习前端时，页面很少的情况下可以一边放编辑器，一边浏览器，这样编写完毕后保存，浏览器就会自动更新
![](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/7.png)

# HTML的学习
接下来我们正式进入html的一个学习
### 骨架了解
我们在建好一个html文件的同时，第一件事就是先把骨架搭出来

```html
<!DOCTYPE html>

<html lang="en">

<head>

	<meta charset="UTF-8">

	<meta name="viewport" content="width=device-width, initial-scale=1.0">

	<title>Document</title>

</head>

<body>

	hello world

</body>

</html>
```

 -  **文档类型声明标签** `<!DOCTYPE html>`
		
	 - 文档类型声明，不是一个HTML标签，作用就是告诉浏览器使用那种HTML版本来显示网页
	- 这句代码的意思是：当前页面采取HTML5版本来显示网页
 -   **语言种类**`lang`
		- 用来定义当前文档显示的语言。
		- en定义语言为英语，zh-CN定义语言为中文
 - **字符集**`charset`
	- 在< head>标签内,可以通过< meta>标签的charset属性来规定HTML文档应该使用哪种字符编码。
	- “UTF-8”是 Unicode 系列中的其中一个编码，这个编码是互联网上使用最广泛的一种 Unicode 的实现方式。它是为传输而设计的编码，并使编码无国界，这样就可以显示世界上所有文化的字符了——不管字母、数字还是中文、阿拉伯文等等
- `<html>`
	-	必须以 `<html>` 标记开始我们的页面，以`</html>`标记结束，注意看，结束标记多了一个“`/`”。这整个包含“开始标记 + 内容 + 结束标记”的一个整体就称作一个“元素”。 
	-	对于`<html>`元素，页面中的所有内容都**嵌套**在这个元素中。只有 `<head>` 和 `<body>` 元素能直接放在 `<html>` 元素里。
- `<head>`
	-	`<head>` 里主要放一些与当前页面内容无关、但承载一些对页面描述的标记——可以设置它的 meta、title，可以放 CSS，这些部分不会被用户看到；
	-	`<head>` 里主要放一些与当前页面内容无关、但承载一些对页面描述的标记——可以设置它的 meta、title，可以放 CSS，这些部分不会被用户看到；
- `<body>`
	-   `<body>` 里边放的是和页面内容相关的元素——即你想让用户看到的内容,也就是我们代码主要集中写的地方。

### 标签
浏览器会从头到尾分析你的html代码，寻找代码里的标签
#### 标签格式
- 标签的格式基本上为
	-	小于号-字母-大于号
	-	而如果这个标签有内容，那么后面还要加一个结束标签
小于号-左斜杠-和前面相同的字母-大于号
`<p> 中间有内容需要添加结束标签 </p>`

- 名称
	-	标签格式里的字母就是这个标签的名称
	-	比如 `<p> 英语: paragraph 段落 </p>`

>当我们用标签符合格式把内容包裹起来后，浏览器就会知道这是一个标签，我们也可以把它叫做盒子（也就是我们要用来搭建网页的俄罗斯方块），盒子里面可以装文字，也可装更多盒子。所谓的写网页就是用标签分隔盒子（html），用样式控制外观和位置（css）。
### 标签的学习
实际上html中有很多不同种功能的标签，记不全，也没必要记全，更推荐的是想用什么功能，到时候再去文档里面搜索，以mdn中文文档举例![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/8.png)
在我们想实现对应功能前，去搜索对应功能有什么标签，在这个网站查找具体语法（当作新华字典使用）。

## 基础标签
 标签名   | 定义     | 使用           |
| :------: | :------: | :------------: |
| h1 - h6  | 标题标签 | 1-6逐级递减    |
| p        | 段落标签 |                |
| br       | 换行标签 |                |
| div      | 盒子标签 | 独占一行       |
| span     | 盒子标签 |                |
| img      | 图像标签 |                |
| a        | 超链接标签|               |
	


### h1 -h6 标题标签
- 标签介绍
h就是单词 head 的缩写, 意为头部, 标题, 常用于标题, 并依据重要性递减( h1最大, h6最小)
-  实际演示

```html
<h1>一级标签</h1>

<h2>二级标签</h2>

<h3>三级标签</h3>

<h4>四级标签</h4>

<h5>五级标签</h5>

<h6>六级标签</h6>
```
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/18.jpg)

### p段落标签
-  标签介绍
p就是单词 paragraph 的缩写, 意为段落, 常用于定义段落, 将整个网页分为若干个段落
-  实际演示

```html
	<P>第一个段落</P>
	<p>第二个段落</p>
```
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/10.png)
### br 换行标签
-  标签介绍
br是单词 break 的缩写, 意为打断,换行, 页面中的文字需要到最右端才会自动换行, 如果希望文本强制换行, 可以使用br标签进行换行
- 实际演示
```html
	第一行<br />
	第二行
```
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/11.png)
### div标签
- 标签介绍
div是单词 division 的缩写, 表示分割,分区, 没有什么特殊意义,常用来装内容, 需要注意的是,div标签独占一行, 也就是说一行只能放一个div盒子
- 实际演示
```html 
		<div>div标签独占一行</div>
		<div>div标签独占一行</div>
```
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/12.png)

### span标签
- 标签介绍
span表示跨度,跨距, 没有什么特殊含义,常用来装内容,与div不同的是,一行可以放多个span标签，所以它一般承担的是装盒子的盒子功能，目的在于将几个盒子归纳到一起，与其他盒子隔离开。
>div标签与span标签的区别
>1、div标签是块级元素，每个div标签都会从新行开始显示，占据一行；
>2、div标签内可以添加其他的标签元素；
>3、span标签是行内元素，会在一行显示；
>4、span标签内只能添加行内元素的标签或文本。


### img 图片标签
- 标签介绍
img是单词 image 的缩写,意为图像,常用来定义页面中图片
- 标签属性
	- src – 指定图片的路径
	- alt – 设置图片的替代文本( 图片加载失败时显示)
	- title – 设置图片的提示文本( 鼠标悬浮在图片上时显示)
>在这里出现了一个我们原先没有提到的概念：**标签的属性**。
>所谓属性，就是每个东西的某一方面信息 <br/>
>` <人 姓名='sjy' 年龄='20' 性别='male'></人>`<br/>
>这里的姓名，年龄，性别就是属于人这个标签的属性，而'sjy', '20', 'male'，就是对应这些属性的各种值。
>那么浏览器会在处理某个标签的代码时，会根据设计的属性和具体的属性值的描述，来生成相应的标签元素。
>有些属性是某种标签特有的，而有些属性又是每种标签都有的，也不用全记，跟标签的学习是一样的，只记常用的。
- 实际演示

```html
	<img src="./hot.jpg" title="提示文本">
	<img src="./hot1.jpg" alt="替换文本">
``` 
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/13.png)
### a超链接标签
- 标签介绍
a是单词 anchor 的缩写,意为锚, 可以从一个页面链接到另一个页面，用这个标签可以用来包裹其它标签，让我们在点击这个被包裹标签时，可以进行跳转页面的功能
- 标签属性
	-	href – 指定目标url（我们要跳转的网页地址）
	-	target – 指定链接页面的打开方式
			这个属性有几个值（前两种较常用）
			 _blank 新页面打开
			_self 当前页面打开
			_top 在最顶层页面打开
			_parent 在当前页面的上一级打开

## 文本格式化标签
| 标签 | 定义   |
| :--: | :----: |
|  b   |  加粗  |
|  i   |  斜体  |
|  s   | 删除线 |
|  u   | 下划线 |

### 实际演示

```html
<b>加粗</b><br />
<i>斜体</i><br />
<s>删除线</s><br />
<u>下划线</u>
```
![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/14.png)

## 表格标签
| 标签   | 定义                                   |
| :----: | :------------------------------------ |
| table  | 定义表格                               |
|  tr    | 定义行, 必须嵌套在 table 标签中        |
|  td    | 定义单元格, 必须嵌套在 tr 标签中       |
|  th    | 定义表头, 必须嵌套在 tr 标签中         |

### 标签介绍
表格主要用于显示和展示数据, 可以让数据显示的非常整齐, 提高可读性, 一个简洁的表格能够把繁杂的数据表现的很有条理, 需要注意的是 表格擅长的是展示数据而不是布局页面, 页面的布局推荐使用 div 或 span 等标签
### 实际演示

```html
	<table border='1'>
    <tr>
        <th>姓名</th>
        <th>年龄</th>
    </tr>
    <tr>
        <td>张三</td>
        <td>18</td>
    </tr>
    <tr>
        <td>李四</td>
        <td>19</td>
    </tr>
</table>
```

![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/15.png)

## 列表标签
常用前三个
| 标签 | 定义                                       |
| :--: | :---------------------------------------- |
|  ul  | 定义无序列表, ul 标签中只能嵌套 li 标签    |
|  ol  | 定义有序列表, ol 标签中只能嵌套 li 标签    |
|  li  | 定义列表项, 一个容纳数据元素的容器         |
|  dl  | 自定义列表, dl 标签中只能嵌套 dt 和 dd 标签 |
|  dt  | 定义列表头                                 |
|  dd  | 定义列表项                                 |
### 标签介绍
顾名思义, 列表标签可以使数据呈列表的形式展现, 提高数据的可读性, 使数据的展现更加规律和美观  
列表分为有序列表和无序列表, 无序列表没有顺序可言, 通常以项目符号呈现列表项, 而有序列表可以显示各个列表项的顺序

### 标签演示

```html
<ul>
  <li></li>
</ul>
```

1.u标签里只能嵌套li标签
2.li标签可以嵌套任意标签

```html
<ol>
  <li></li>
</ol>
```

所有特性基本与ul 一致，比ul多了一个顺序数字

## 表单标签

| 标签      | 定义       |
| :-------: | :--------: |
| form      | 定义表单   |
| input     | 文本输入框 |
| select    | 下拉       |
| option    | 下拉列表项 |
| textarea  | 文本域     |


### form表单
- 标签介绍
form 标签用来创建一个 **表单域**, 在提交数据时, 表单域中的所有数据元素将被作为一个整体提交至服务器（你们暂时用不上这个标签，因为会涉及后端的一些接口）
- 标签属性
	- action – 指定表单数据提交的url地址
	- method – 指定提交方式( get/post)
### input 输入框
- 表单属性
	-   type – 指定输入框的属性
	-   name – 定义元素名, 用于后端接收数据
	-   value – 设置输入框的值
	-   checked – 首次加载时选中
	-   maxlength – 最大长度, 用于规定输入的字符数量( 没啥用,前端源码中随便修改)
- 常用属性

| 属性值   | 定义                                   |
| :------: | :------------------------------------ |
| text     | 文本, 默认20个字符                     |
| password | 密码, 输入框中的字符将被掩饰           |
| submit   | 提交按钮, 提交表单的数据到服务器       |
| button   | 普通按钮, 常用于触发JS函数             |
| file     | 上传文件按钮                           |
| radio    | 单选按钮                               |
| checkbox | 复选框                                 |
| hidden   | 隐藏输入框                             |
| image    | 提交按钮, 图片形式                     |
| reset    | 重置按钮, 清空表单内容                 |

- 实际演示

```html
    <form action="xxx.php" method="get">
        用户名:<input type="text" name="username" value="用户名" /><br />
        密码:<input type="password" name="passwd" /><br />
        性别:男<input type="radio" name="sex" value="1" checked />
        女<input type="radio" name="sex" value="2"/><br />
        爱好:苹果<input type="checkbox" name="happy" value="1" />
        香蕉<input type="checkbox" name="happy" value="2"/><br />
        籍贯:<select name="city">
        		<option value="1">山东</option>
        		<option value="2">北京</option>
        	</select><br />
        上传头像:<input type="file" name="file" /><br />
        留言:<textarea name="text"></textarea><br />
        <input type="submit" value="提交" />
        <input type="reset" value="重置" />
    </form>
```

![输入图片说明](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/16.png)

>以上就是我们常用的标签的一些汇总，像一些视频标签，就适合一些有需求的同学通过各种字典文档去查询它们的语法，也能够快速上手，进行一些网页实现

## 预习作业(不强制要求)
- 第一项
	- 跟学习其他编程语言一样，我们也有仪式感一点
	- 将' Hello， world！' 用html在网页上展示出来
- 第二项
	- 运用p标签，h标签，img，等等基础标签，随便找一个新闻网的一个，把它的主体给复现出来
	- 具体网页可以参考[新华网文化观察丨2025年电影国庆档：多元类型传递主流价值 “电影+”延伸产业边界-新华网](http://www.news.cn/ci/20251010/14699d22371247fcb5510ba7533f6934/c.html)，随便找的一个新闻，像初学html的你们就可以找找这种纯文本比较多的来练练手
- 第三项
	- 模仿制作一个网站的注册页面，用于熟悉表单标签
	- 效果类似如下
	![](https://cdn.jsdelivr.net/gh/CQUPT-Christopher/picture/19.jpg)
	>ps：总之，我们加油吧！😀
