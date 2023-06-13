# html学习

## vscode快捷键

- shift+alt+f 代码格式化

- ctrl+f   快速查找

- ctrl+h 快速替换

- !+回车自动生成html的基本结构

- 

  



## html基本骨架

- 单标签<img>
- 双标签<html></html>
- 文档类型的缩写，必须声明<!DOCTYPE html>
- head双标签 是给开发者看的，描述了文档的各种属性和信息（其中必须包含title标签）
- title双标签  定义文档的标题，可显示在浏览器的标题栏，且有助于seo的优化
- meta单标签  描述文档的属性  比如<meta charset="UTF-8"> 编码的表达  写在head里
- body双标签  定义文档的主题及所有内容（文本，超链接，列表等）

```html
<!DOCTYPE html>
<html>

<head>
    <meta charset="UTF-8">
    <title>这是一个网页</title>
</head>

<body>
    hi
</body>

</html>
```



## 标题标签<h1></h1>

```
<h1>一级标签</h1>
<h2>二级标签</h2>
...
```

- 生成h1-h6的快捷键  h$*6
- 逐层大小下降
- 正确使用标题标签有助于seo识别
- 标签中的属性：align="left|center|right"

```
<h1 align="left"></h1>
```







## 标签- 段落、换行、水平线

### 段落<p></p>

```
<p></p>
```

### 换行<br>

在不产生新段落的时候换行

```
<p>我的下一个我<br>要换行</p>
```

### 水平线<hr/>

生成一条线

可根据属性换颜色color,设置长度width，设置高度大小size，对齐方式align

```
<hr color="green">
```





## 标签-图片<img>

```
<body>
	<img src="图片名称.属性"   此照片必须在当前源码文件下
</body>
```

属性

- src 图片路径
- alt  图像无法显示时的代替文本
- width 图像宽度  300px
- height 图高  一般不规定宽度
- title 鼠标悬浮在图片上给的提示



### 图片路径详解

- 绝对路径：电脑盘符与访问的具体位置E:/

- 相对路径：两者存在关系，在同一路径下可以直接访问

  子级关系  通过/寻找

  父级关系 通过../寻找

  同级关系 通过./寻找（可以省略）

- 网络路径：某网页链接

  

## 标签-超文本链接

使用<a></a>设置超文本链接

超链接可以是字、词、图像、文档

```
<a href="url">链接在网站上展现的文本</a>

<a href="url">
	<img>
</a>
```

超链接属性：在<a>中使用href来描述链接中的地址

- 未访问的为蓝色字体并带有下划线

- 访问过的为紫色字体并带下划线

- 点击后会显示为红色并带有下划线

  

##  标签-文本

| 标签              | 作用       |
| ----------------- | ---------- |
| <em></em>         | 着重       |
| <b></b>           | 粗体       |
| <i></i>           | 斜体       |
| <strong></strong> | 加重       |
| <del></del>       | 删除字     |
| <span></span>     | 无特定含义 |

## 列表标签-有序和无序标签

有序标签

```
<ol type="">
	<li>第一个</li>
	<li>第二个</li>
</ol>
```

<ol type=""></ol>的type属性可改变列表项目（1，2，3、、）（a,b,c...)



无序标签

```
<ul type="">
	<li></li>
</ul>
```

其type选项为

- disc默认实心圆
- circle空心圆
- square小方块
- none不显示



快速生成ul+li的布局

ul>li*所需数字

## 标签-表格

```
<table>
	<tr>
		<td></td>
		<td></td>
	</tr>
	<tr>
		<td></td>
		<td></td>
	</tr>
</table>
```

以上为2*2表格

tr行  td列



快速生成键(2*2)：table>tr*2>td*2{单元格文本信息}

table表格属性：

- border边框
- width宽度
- height高度

### 合并单元格

横向合并colspan  保留左边，删除右边

垂直合并rowspan  保留上边，删除下边

```
<table>
        <tr>
            <td colspan="2">1-2</td>
            ”<td>2</td>“直接删除即可
        </tr>
        <tr>
            <td colspan="" rowspan="">1</td>
            <td>2</td>
        </tr>
    </table>
```

## form 表单

让网站具有交互性：填写信息，登录注册，搜索框等

**表单由容器和控件组成，一般应该包括用户填写信息的输入框、按钮**

**这些输入框和按钮叫做控件，**

**表单为容器，他能容纳各种控件**

```
<form action="url" method="get|post" name="表单名"></form>
```

**属性介绍**

- action服务器地址
- name表单名称,用于内部的调动，不展示给用户
- method数据提交方式 get|post

get 提交数据 url可见  一般用于提交少量数据

post 提交数据url不可见  一般用于提交大量数据



### **表单元素**

三个基本组成部分：表单标签、表单域input、表单按钮input

```
<form>
	<input type="text">
	<input type="submit">
</form>
```

#### 文本框

文本域<input type="text">来设定

``` 
<form>
	first name:<input type="text" name="firstname">
	<br>
	last name:<input type="text" name="lastname">
</form>
```

#### 密码框

密码框使输入的文字显示为星号或原点

```
<form>
	possword:<input type="password" name"pwd>
</form>
```

```
<body>
<form>
        用户名<input type="text">
        密码<input type="password">
        <input type="submit" value="登录"> 登陆按钮部分
    </form>
</body>
```

## 块元素和内联元素

块元素是上下摆放的，内联元素左右摆放的

行内块级元素：不换行能识别宽高



**常见块级元素**

div     form      h1-h6  hr   p   table   ul

**常见内联元素（行内元素）**

a  b   em   i   span   strong

**行内块级元素**

button   img    input



| 块级元素                               | 内联元素                               |
| -------------------------------------- | -------------------------------------- |
| 在页面中自上而下垂直排列               | 只占自身的大小                         |
| 可设置width，height等属性              | 不可设置width，height等属性            |
| 一般块级元素可包含内元素和其他块级元素 | 一般内联元素包含内联元素不包含块级元素 |

## html5新增标签

div容器

div可嵌套，为了更有结构化，无效果

div的属性id可命名div



**传统布局与html5的新标签布局比较**

```html
<div id="header"></div>
<div id="nav"></div>
<div id="article">
	<div id="section"></div>	
</div>
<div id="silder"></div>
<div id="footer"></div>
```

```html
<header></header
<nav></nav>
<article>
	<section></section>
</article>
<aside></aside>
<footer></footer>
```

![HTML5新增语义化标签是什么呢？（1）_㼛思雨的博客-CSDN博客](https://img-blog.csdnimg.cn/20200623155927156.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NTE0Nzg5NA==,size_16,color_FFFFFF,t_70)

