#               HTML学习总结

## 1.何为HTML

HTML是超文本标记语言（HyperText Markup Language)的缩写，是为“网页创建和其他可在浏览器中看到的信息”设计的一种标记语言。

------

## 2.关于HTML中标签的使用

标签有开始标签和结束标签

开始标签：包含元素的名称，被左右角括号包围。表示元素从这里开始或者开始起作用。例如:<p>。

结束标签：与开始标签相似，只是在其元素名之前加了一个斜杠。例如：</p>。

由开始标签，内容，结束标签便组成了一个完整的元素。例如：

`<p>这是一个完整的元素</p>`

<font size=3 color="red">HTML中常用标签</font>

``<h1></h1>:标题标签，分1~6级，1最大6最小``

``<hr/>:水平分割线``

``<p></p>:段落标签``

``<img/>:用于添加图片的``

``<a></a>:超链接，属性href链接地址``

``<ul></ul>:无序列表，属性type``

``<ol></ol>:有序列表，属性有type``

``<table></table>:表格，属性border指定边框，height指定高，with指定宽，bgcolor背景色，align对齐方式``

`<br/>:换行`

`<pre></pre>:网页中格式和标签中一样。`

等等。

------

## 3.网页背景的相关设置

1. 背景图片的设置

`<body background="图片地址"><body>`

但是这样弄出来的背景图不怎么好看，有很多张。

<img src="C:\Users\86176\AppData\Roaming\Typora\typora-user-images\1615718298909.png" alt="1615718298909" style="zoom: 25%;" />

还有一个办法可以解决这个问题

```html
` <head><style>` 

`body {
				background: url(1.jpg) no-repeat center center fixed;
				/*兼容浏览器版本*/
        -webkit-background-size: cover;
				-o-background-size: cover;        
				background-size: cover;
			} `

`<style><head>`
```

<img src="C:\Users\86176\AppData\Roaming\Typora\typora-user-images\1615719773608.png" alt="1615719773608" style="zoom: 25%;" />

2. 背景颜色的设置

```html
<body style="background-color: chartreuse;"><body>
   
```

当你输入完background-color时会自动出现颜色供你选择

<img src="C:\Users\86176\AppData\Roaming\Typora\typora-user-images\1615720875934.png" alt="1615720875934" style="zoom:25%;" />

------

## 4，超链接的制作

1. 文字及字母超链接制作

   ```html
   <a href="https://www.baidu.com/" target="_blank">百度一下</a>
   ```

2. 图片超链接的制作

   前面学过标签的嵌套，只需要在<a>标签中加上一个<img>标签就行。
   
   ```html
   <a href="https://www.baidu.com/" ><img src="picture//11ha.jpg.JPG"></a>
   ```

## 5，表格制作

```html
<table>
    <tr>
      <th>Firstname</th>
      <th>Lastname</th>
      <th>Age</th>
    </tr>
    <tr>
      <td>Jill</td>
      <td>Smith</td>
      <td>50</td>
    </tr>
    <tr>
      <td>Eve</td>
      <td>Jackson</td>
      <td>94</td>
    </tr>
  </table>
```

其中<tr>为行，<td>为行中元素，<th>为表头元素会加粗。



