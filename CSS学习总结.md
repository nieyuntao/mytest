#             CSS学习总结

## 1.何为CSS

 CSS是Cascading Style Sheet的缩写，层叠样式表，是一种用来表现文件样式的计算机语言。CSS不仅可以静态的修饰网页，还可以配合各种脚本语言动态地对网页各元素进行格式化。

------

## 2.CSS如何生效

一般有三种办法让CSS生效

#### <font color="red">外部样式表</font>

在同一个目录下创建一个文件夹，例如名字为CSS，然后在CSS下创建文件，名字为mycss.css,后缀要为.css。然后需要在HTML文件中<head>标签中加入语句

`<link rel="stylesheet" type="text/css" href="mycss.css">`

这样就引入完成了。

#### <font  color="red">内部样式表</font>

这种方法只需要在HTML文件中的<head>标签中加入你需要规定的格式，例如：

```
<style>
    body {
      background-color: linen;
      text-align: center;
    }
    h1 {
      color: red;
    }
    .haha {
      margin-top: 100px;
      color: chocolate;
      font-size: 50px;
    }
  </style>
```

#### <font color="red">内联样式</font>

这种方法就是直接把样式规则直接写到要应用的元素中，例如：

```
<h1 style="color:green;">I am a heading</h1>
```

## 3.CSS语法

一条CSS样式规则由选择器和以{}包裹的声明组成

> <font color="blue">h1    {color:blue;font-size:12px;}</font>

其中h1为选择器，选择器是你需要改变样式的对象。每条声明由;隔开。

###### id选择器

```
/*id选择器前有#号。*/
#sky{
color: red;
}
```

id选择器适用范围只有一个元素。

###### class选择器

```
/*class选择器前有.号/*
.blue{
color:blue;
}
```

元素的class值可以多个，所以其应用比较普遍。

## 4.颜色，尺寸，对齐

###### 颜色

 颜色在网页中的重要性不言而喻。
我们可以采用颜色名称也可以使用颜色RGB16进制值，来设定前景或背景的颜色 。

###### 尺寸

 我们可以用 `height` 和 `width` 设定元素内容占据的尺寸。常见的尺寸单位有：像数 `px`，百分比 `%`等。 

###### 对齐

 对于**元素中的文本**，我们可以简单的设置`text-align`属性为`left, center, right`即可。

## 5.盒子模型

 盒子模型指的是一个 HTML 元素可以看作一个盒子。从内到外，这个盒子是由**内容 content, 内边距 padding, 边框 border, 外边距 margin**构成的。

Content 盒子的内容，如文本、图片等Padding 填充，也叫内边距，即内容和边框之间的区域Border 边框，默认不显示Margin 外边距，边框以外与其它元素的区域

一个元素真正占据的宽度应该是：
左外边距 + 左边框宽度 + 左内边距 + 内容宽度 + 右内边距 + 右边框宽度 + 右外边距

## 6.定位

position属性用于对元素进行定位，该属性有static,relative,fixed,absolute, 设置了元素的position属性后，我们才能使用top, bottom, left, right属性，否则定位无效。 

###### static

 设置为静态定位position: static;，这是元素的默认定位方式，也即你设置与否，元素都将按正常的页面布局进行。按照元素在 HTML出现的先后顺序从上到下，从左到右进行元素的安排。 

###### relative

 设置为相对定位position: relative，这将把元素相对于他的静态（正常）位置进行偏移 

###### fixed

 设置为固定定位`position: fixed;`，这将使得元素固定不动（即使你上下左右拖动浏览器的滚动条）。
此时元素固定的位置仍由`top, bottom, left, right`属性确定，但相对的是视口（viewport，就是浏览器的屏幕可见区域）
如下的代码将会在浏览器右下角固定放置一个按钮元素： 

```
<!-- HTML -->
<div class="broad">占位区域。请将浏览器窗口改变大小，看看右下角的按钮发生了什么？</div>
<div class="example-fixed">这个按钮是固定的</div>
<!-- CSS -->
.example-fixed {
  position: fixed;
  bottom: 40px;
  right: 10px;
  padding: 6px 24px;
  border-radius: 4px;
  color: #fff;
  background-color: #9d0f0f;
  cursor: pointer;
  box-shadow: 0 3px 3px 0 rgba(0,0,0,0.3), 0 1px 5px 0 rgba(0,0,0,0.12), 0 3px 1px -2px rgba(0,0,0,0.2);
}
.broad {
  height: 5000px;
  width: 5000px;
  padding: 20px;
  background-color: darkkhaki;
}
```

###### absolute

 设置为绝对定位`position: absolute;`，将使元素相对于其**最近设置了定位属性（非static）的父元素**进行偏移。
如果该元素的所有父元素都没有设置定位属性，那么就相对于``这个父元素 。

## 7.溢出

当元素内容超过其指定的区域时，我们通过溢出`overflow`属性来处理这些溢出的部分。
溢出属性有一下几个值：

- visible 默认值，溢出部分不被裁剪，在区域外面显示
- hidden 裁剪溢出部分且不可见
- scroll 裁剪溢出部分，但提供上下和左右滚动条供显示
- auto 裁剪溢出部分，视情况提供滚动条

## 8.浮动

 在一个区域或容器内，我们可以设置`float`属性让某元素水平方向上向左或右进行移动，其周围的元素也会重新排列 

 让图片向右浮动即可，代码如下 

```
<html>
<head>
  <style>
    .example-float-right {
      float: right;
    }
  </style>
</head>
<body>
  <img src="https://mdbootstrap.com/img/Photos/Others/placeholder1.jpg" class="example-float-right" alt="">
  <p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Quidem, architecto officiis, repellendus
  corporis obcaecati, et commodi quam vitae vel laudantium omnis incidunt repellat qui eveniet fugiat totam
  modi nam vero!</p>
</body>
</html>
```

 一个浮动元素会尽量向左或向右移动，直到它的外边缘碰到包含框或另一个浮动框的边框为止。
浮动元素之后的元素将围绕它。 

## 9.不透明度

 我们可以用`opacity`对任何元素（不过常用于图片）设置不透明度。
值在`[0.0～`1.0]之间，值越低，透明度越高。

## 10.组合选择器

 前面我们学习了 CSS有三种选择器：元素、id 和 class 。但我们也可以进行组合，以得到简洁精确的选择。 

###### 后代选择器

 以空格作为分隔，如：`.haha p` 代表在`div`元素内有`.haha`这种类的所有元素 。

###### 子选择器

 也称为直接后代选择器，以`>`作为分隔，如：`.haha > p` 代表在有`.haha`类的元素内的直接``元素。 

## 11.伪类和伪元素

伪类（pseudo-class）或伪元素（pseudo-element）用于定义元素的某种特定的状态或位置等。
比如我们可能有这样的需求：

- 鼠标移到某元素上变换背景颜色
- 超链接访问前后访问后样式不同
- 离开必须填写的输入框时出现红色的外框进行警示
- 保证段落的第一行加粗，其它正常
- ...

 使用伪类/伪元素的语法如下： 

```
/* 选择器后使用 : 号，再跟上某个伪类/伪元素 */
selector:pseudo-class/pseudo-element {
  property:value;
}
```

