---
title: CSS选择符
date: 2018-08-12
categories:
- web前端
- HTML/CSS
tags: 
    - CSS3
---
##### 今天对新知识的学习充满了疲惫，来点简单的小点心学习，对CSS3的选择器做一个小小的总结。
>###### 小黑板：CSS是Cascading Style Sheet（层叠样式表）的缩写，CSS不需要编译,可以直接由浏览器执行(属于浏览器解释型语言)。
#### 1.* ：通用选择器。
>我们一般的页面开发都会用到的一行代码：
`{ margin: 0; padding: 0; }`
这是最基本的清除默认CSS样式方法。
#### 2.属性选择器。
>1️⃣ `a[lmz] { color: green; }`
匹配具有某属性的标签，例如实例中是匹配具有lmz属性的a标签。
`2️⃣ [class*=lmz] { color: #1f6053;  }`
属于属性选择器，匹配元素的属性class中所有含有lmz的标签。正则匹配
`3️⃣[class^=lmz] { color: #1f6053;  }`
属于属性选择器，匹配元素的属性class中以lmz的标签。正则匹配
`4️⃣[class$=.lmz] { color: #1f6053;  }`
匹配属性中以.lmz结尾的标签，正则匹配，也是属性选择器的一种
`5️⃣[class~=lmz] { color: #1f6053;  }`
匹配属性中具有多个空格分隔的值、其中一个值等于“lmz”的元素
#### 3.伪对象选择符。
>before 和after是在选择的标签之前或者之后插入内容，一般用于清除浮动，但是对于IE6、IE7是不可用的
#### 4.*:not(p) { color: green; }。
>选择除了（）中选择器之外的标签元素。
#### 5.X:nth-child(n) | X:nth-last-child(n) | X:nth-of-type(n)
>`li:nth-child(3) { color: red; }`
匹配X元素中从头数第几个标签，例如上面的代码是匹配的是第三个li标签。
`li:nth-last-child(2) { color: red; }`
与上一个选择器相反，这个选择器是倒序匹配第几个标签，上面的代码的意思是匹配倒数第二个li标签
`ul:nth-of-type(3) { border: 1px solid black; }`
与:nth-child()作用类似，但是仅匹配使用同种标签的元素
`ul:nth-last-of-type(3) { border: 1px solid black; }`
与:nth-last-child() 作用类似，但是仅匹配使用同种标签的元素
#### 6.overflow
>##### 取值：
>`visible`：
对溢出内容不做处理，内容可能会超出容器。
`hidden`：
隐藏溢出容器的内容且不出现滚动条。
`scroll`：
隐藏溢出容器的内容，溢出的内容可以通过滚动呈现。
`auto`：
当内容没有溢出容器时不出现滚动条，当内容溢出容器时出现滚动条，按需出现滚动条。textarea元素的overflow默认值就是auto。
`clip`：
与hidden一样，clip也被用来隐藏溢出容器的内容且不出现滚动条。不同的地方在于，clip是一个完全禁止滚动的容器，而hidden仍然可以通过编程机制让内容可以滚动。

##### 欢迎关注我的简书文章：[六个周](https://www.jianshu.com/p/1da967b0a495)