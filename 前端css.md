# css的概念

## css概念

- css 简称样式表

- css文件后缀为css

- css用于html文档中的元素样式的定义

- css的唯一目的是为了让网页变得美观

  

## css语法

**选择器+{属性:值;属性:值;}**

用style属性插在head里，然后选择body里需要改变样式的html元素（方案一）

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        h1{
            color: aqua;
            font-size: 40px;
        }
    </style>
</head>
<body>
    <h1>这是网页</h1>
</body>
</html>
```

# css的引入方式

### **内联样式的引入**

（不利于维护）

方法一

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    <h1 style="color:red;">这是网页</h1>
</body>
</html>
```

方法二

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        h1{
            color: aqua;
            font-size: 40px;
        }
    </style>
</head>
<body>
    <h1>这是网页</h1>
</body>
</html>
```

### **外部样式的引入**

独立建立一个css文件

在多页面的时候在需要使用css的页面的head里用

```
<link rel="stylesheet" href="css所在的目录">
```

即可

css文件里只能写css比如

```css
p{
    color:aqua;
}
```

# 选择器

## 全局选择器

可以与任何元素匹配

```
*{
	color:blue;
}
```

## 元素选择器

选择同一类型的所有标签，如p b  div  img 等

```
p{
	color:blue;
}
```

## 类选择器

给需要选择的标签添加class属性并命名，然后用.选择

可以选择多种同一命名class的标签**（可重复）**

类名不能开头为数字

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .content{
            color: aqua;
        }
    </style>
</head>
<body>
    <h1 class="content">这是网页</h1>
    <h2>hihi</h2>
    <p class="content">wo</p>
</body>
</html>
```

同一标签可使用多个类选择器，用空格隔开

```
<p class="content size">wo</p>
```

## id选择器

标签的id是**唯一的**，用#选择，不能以数字开头



## 合并选择器

提取相同的样式，减少代码重复

```html
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        h1,h2{
            color: aqua;
        }
    </style>
</head>
<body>
    <h1>这是网页</h1>
    <h2>hihi</h2>
</body>
</html>
```

## 选择器的优先级

从高到低

行内样式>id选择器>类选择器>元素选择器

# 字体属性

可定义字体颜色大小加粗样式

color字体颜色

font-size字体大小，chrome能接受的最小字体是12px

font--weight字体的粗细

font-style字体样式（默认或斜体）

font-family 指定一个元素的字体

# 背景属性

background-color设置背景颜色

background-image设置背景图

background-position设置背景图位置

background-repeat设置背景图如何填充  默认垂直水平平铺  垂直平铺  水平平铺  不平铺

background-size设置背景图片大小

```html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .box1{
            width: 600px;
            height: 600px;
            background-image: url("1.jpg");
            background-repeat: no-repeat;
        }
    </style>
</head>
<body>
    <p>home</p>
    <a href="./product.html">product</a>
    <div class="box1"></div>
</body>
```

# 文本属性

text-align指定文本的水平对齐方式

text-decoretion指定文本的修饰，下划线、上划线、删除线等等

text-transform控制文本的大小写

text-indent规定首航文本的缩写

# 表格属性

## 表格添加边框

border:像素 样式 颜色  ，其中间用空格隔开(双边框)

```
table,td{
	border:1px solid black;
}
```

折叠边框（单一边框）

border-collapse

```
table,td{
	border-collapse:1px solid black;
}
```

## 表格文字对齐

text-align属性设置文本对齐方式

```
td{text-align:right;}
```

vertical-align垂直对齐属性设置垂直对齐

```
td{height:50px;
vertical-align:bottom;}
```

## 表格的填充

padding

如果在表的内容中控制空格之间的边框，应用td和th元素的填充属性

## 表格的颜色

边框的颜色

```
table{border:1px solid green;}
```

th元素的文本和背景颜色

```
td{background-color:green;color:white;}
```

# 关系选择器

## 后代选择器

选择被E包含的F元素，对更深一步的元素仍起作用

E F{}

## 子代选择器

选择作为E元素的直接子元素F，对更深的一层元素不起作用

E>F{}

## 相邻兄弟选择器

选择紧跟E后的F元素，选择相邻的第一个兄弟元素，只能向下选择

E+F{}

## 通用兄弟选择器

选择E元素**之后的所有**兄弟元素F，作用于多个元素，只能向下选择

E~F{}

# css盒子模型

css盒子模型本质上就是一个盒子，封装周围的html元素

包括外边距margin，边框border，内边距填充padding，实际内容content

margin清除边框外的区域，外边框是透明的

border围绕内边距和内容外的边框

padding清楚内容周围的区域  可设置padding-left 等

# 弹性盒子模型flex box

为了更好的布局，比如小程序适配等

**弹性容器是通过display属性的值为flex将其定义为弹性容器**

display: flex

弹性容器内包含了一个或多个弹性子元素

弹性容器外及弹性子元素内是正常渲染的

弹性盒子只定义了弹性子元素如何在弹性容器内的布局

默认情况下弹性盒子里的内容横向摆放

```html
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .container{
            width: 500px;
            height: 500px;
            background-color: aqua;
            display: flex;
        }
        .box1{
            width: 100px;
            height: 100px;
            background-color: black
        }
        .box2{
            width: 100px;
            height: 100px;
            background-color: blue;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box1"></div>
        <div class="box2"></div>
    </div>
</body>
</html>
```

## 父元素上的属性

display: flex开启弹性盒



flex-direction属性指定了弹性子元素在父容器中的位置

语法

```
flex-direction:row|row-reverse|column|column-reverse
```



justify-content属性应用在弹性容器上，就是把弹性项沿着弹性容器的主轴线对齐

align-items属性设置或检索弹性盒子元素在策州或纵轴方向上对齐的方式





## 子元素上的属性

flex-grow或者flex根据弹性盒子元素所设置的扩展银子作为比率来分配剩余空间

默认为零，如果存在剩余空间也不放大

按比（权重）分大小，一旦设置此属性，原来宽高属性失效

？



# 文档流

文档流是指文档中可显示对象在排列时所占的位置/空间



以下为文档流的问题现象

空格折叠现象

默认无论文本里有多少空格，在网站上都显示为一个空格



间隙现象

默认两个图片会有间隙



根据脱离文档流的方式解决文档流的问题

# 脱离文档流的三种方式

- 浮动
- 绝对定位
- 固定定位

## 浮动

增加一个**浮层**来放置内容（加一个图层，覆盖）

float属性定义在哪个方向浮动，任何元素都可以浮动

浮动只有左右浮动left|right

### 清除浮动

浮动所引发的问题

- 浮动元素会造成父元素高度坍塌

- 后续元素会受到影响

  

清除浮动的方法

- 父元素设置高度
- 受影响的元素增加clear属性
- overflow清除浮动  需要overflow;hidden一起写
- 伪对象方式   如果有父级塌陷，并且同级元素受到了影响，可以用伪对象的方式处理。为父标签添加伪类after，并使用clear:both

## 定位

position属性指定了元素的定位类型

position的值  relative相对定位  absolute绝对定位   fixed固定定位

例如 

**position:relative**

**left：200px**



设置定位后，可以直接使用left top right bottom调整位置



### 相对定位 relative

还是标准文件流



### 绝对定位absolute

脱离标准文件流，会有覆盖的特点

每设置一个绝对定位，就会出现一层覆盖

（float浮动只有一层）



### 固定定位fixed

也脱离了标准文件流

整个页面一般只有一个固定定位

无论页面怎么滚动，被固定的元素不变，始终在页面上



设置定位之后，相对定位和绝对定位相对于具有定位的父级元素进行位置调整

如果父级元素不存在，则继续向上级寻找，知道顶层文档。



也就是说子级是绝对定位时，父级是相对定位时

如果现在在父级中添加margin的移动属性，

那么子元素box1会跟着父元素container一起移动



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        .container{
            width: 400px;
            height: 400px;
            background-color: aqua;
            position: relative;
            margin-left: 100px;
        }
        .box1{
            width: 100px;
            height: 100px;
            background-color: black;
            position:absolute;
            left: 50px;
            top:50px;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="box1"></div>
    </div>
</body>
</html>
```



# z-index调整覆盖顺序

z-index：数值；

数值高就不会被覆盖



# css3的新特性

## 圆角

可以使任何元素变成圆角（默认情况下的元素为方角）

border-radius:数值 数值 数值 数值;   数值一般为px像素单位

数值为一个，四个圆角相同

数值为两个，两个角发生变化

border-radius:100%;   为纯原形



## 阴影

box-shadow向框添加一个或多个阴影

box-shadow：h-shadow v-shadow blur color;

​                          水平阴影位置  垂直阴影位置 模糊度  阴影颜色



# 动画

动画是使元素一种样式逐渐变化为另一个样式的效果

用百分比来规定变化的时间，或者用from 和to  其等同于0%和100%（后者用于变化次数多的）

0%为动画的开始，100%为动画的完成

@keyframes创建动画

```

```

animation执行动画

animation：name duration timing-function delay iteration-count direction;

```html
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        div{
            width: 100px;
            height: 100px;
            background-color:hsl(212, 100%, 75%);
            animation: myanime 3s linear 0s infinite;
        }
        div:hover{
            animation-play-state: paused;
        }
        /* 此处实现鼠标触碰，动画即可暂停的操作 */
        @keyframes myanime{
            0%{
                background-color: palegoldenrod;
            }
            50%{
                background-color:aquamarine;
            }
            100%{
                background-color: aqua;
            }
        }

    </style>
</head>
<body>
    <div></div>
</body>
```



div:hover{}实现鼠标接触后可变化

```
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        div{
            width: 100px;
            height: 100px;
            background-color:aquamarine;

        }
        div:hover{
            background-color: aqua;
        }

    </style>
</head>
<body>
    <div></div>
</body>
</html>
```

## 实现运动渐变背景

```html
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        body{
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 30px;
            height: 100vh;
            color: aliceblue;
            background-image: linear-gradient(
                125deg, hsl(150, 37%, 55%),hsl(191, 35%, 56%),hsl(219, 37%, 65%),hsl(276, 59%, 63%)
            );
            background-size: 400%;
            animation: myanime 20s infinite;
        }
        @keyframes myanime{
            0%{
                background-position: 0% 50%;
            }
            50%{
                background-position: 100% 50%;
            }
            100%{
                background-position: 0% 50%;
            }
        }

    </style>
</head>
<body>
    <h1>You are welcome</h1>
</body>
```

## 视差滚动

直接在相关图片元素的css里添加background-attachment：fixed

# 媒体查询

使页面在不同的终端设备下达到不同的效果

会根据设备的大小自动识别加载不同的样式



## 设置meta标签

设置设备的宽度作为视图宽度并禁止初始的缩放

在<head>标签里加入meta标签

<meta .....>

## 媒体查询语法

```css
@media  screen and (max-width:992px) and (min-width:768){
	body{
		background-color: blanchedalmond;
		}
}
```

根据and()后的限制对屏幕大小的感知

之后@media screen and ()后的{}实现元素的颜色变化或者其他属性的变化

比如元素的不显示display：none



# 雪碧图

是一种网页图片应用处理方式，允许将一个页面涉及到的所有零星图片包含到一张大图去

优点：减少图片字节和性能提升

原理：通过background-image引入背景图片

通过background-position把背景图片移动到自己需要的位置

```css
<style>
	span{
		dispaly:block;
        width:45px;
        height;70px;
        background-image:url(i.png);
        background-position:-21px;-12px;
        /* 此处根据坐标对一张大图片进行移动px，根据图层覆盖只显示一个小图 */
	}
</style>
```

# 字体图标

以字体图标代替图片图标

字体图标不会失真

![如何使用字体图标（新手指南） - osc_joe3czc9的个人空间- OSCHINA - 中文开源技术交流社区](https://oscimg.oschina.net/oscnet/1e562a00bb40fc6ffd2330ba833f5c897e0.png)

方法一

```
<span class="iconfont name"></span>
```

iconfont必加

方法二

<link rel="stylesheet" href="./name.css">