---
title: CSS小温故
date: 2018-11-04
categories:
- web前端
- HTML/CSS
tags: 
    - CSS3
---
>今天在看一篇文章的时候，遇到了很多经常使用或者很简单却不知道去使用的一些CSS属性，希望可以做个记录，学会对基础知识的掌握程度进行把握。

##### 一、使用CSS画一个扇形

     <style>
        #main{
            height:0;
            width:0;
            border-style:solid;
            border-width:50px;
            border-color:black transparent transparent;
            border-radius:50px;
        }
    </style>
    <body>
        <div id="main"></div>
    </body>
>这个例子我主要是之前没使用过transparent这个属性，它是用来指定全透明色彩的。
##### 二、 box-sizing常用的属性有哪些？分别有什么作用？
>box-sizing这个属性我之前看到过别人使用过这个属性，但是我自己却未使用过，于是对box-sizing做一个简单记录。
`box-sizing`有两个值：`content-box`、`border-box`
常见的是`content-box`（W3C标准盒模型）：若定义一个div，width为100px，它若有padding、border属性，那么这个div最后的实际宽度将为width+2*padding+2*border.
若为`border-box`(怪异盒模型)：同上一个例子，那么这个div的最后width就是100px。
##### 三、清除浮动。
参考链接：https://www.jianshu.com/p/09bd5873bed4
>清除浮动应该是在前端开发中使用比较频繁的，但是我之前并未使用过，也是在阅读他人代码时一笔带过，并未对这个小小的东西进行研究，于是很多代码的布局那真是费煞苦心，写了一堆垃圾代码。
浮动最初设计只是用来实现文字环绕排版的，清除浮动这个东西的主要三个特点：
>1. 脱离文档流。(也就是说浮动不会影响普通元素的布局)
>2. 向左/向右浮动直到遇到父元素或者别的浮动元素。
>3. `浮动会导致父元素高度坍塌`(感受深刻，之前都不知道浮动原来会让父元素的高度坍塌，于是之前总是写margin-top那种写死的方式进行布局)

>解决父元素高度坍塌的方式就是清除浮动，常规的方法是clear清除浮动和BFC清除浮动，推荐clearfix的方式。
这里展开一下说一下，若没有清除浮动会出现的样式：

    // css
    .box-wrapper {
      border: 5px solid red;
    }
    .box-wrapper .box {
      float: left; 
      width: 100px; 
      height: 100px; 
      margin: 20px; 
      background-color: green;
    }

    // html
    <div class="box-wrapper">
      <div class="box"></div>
      <div class="box"></div>
      <div class="box"></div>
    </div>
![父元素高度坍塌.png](https://upload-images.jianshu.io/upload_images/2054455-c018aed4d7f63ec5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
>清除浮动主要有两种方式：clear清除浮动和BFC清除浮动(不做介绍)。

clear清除：

      <div class="box-wrapper">
        <div class="box"></div>
        <div class="box"></div>
        <div class="box"></div>
        <div style="clear:both;"></div>
      </div>
高度坍塌问题解决，这里就不贴图片了。
然而clear清除浮动最佳实践是：

    .clearfix:after {
      display: table;
      content: " ";
      clear: both;
    }
##### 四、CSS3的Gradient。
参考链接：https://www.w3cplus.com/content/css3-gradient
>语法（共三个参数）：（radial）linear-gradient: [top | left |  left top ]  [起点颜色]  [终点颜色]
 >代码:`background: -moz-linear-gradient( top,#ccc,#000);`
>   `background: -webkit-linear-gradient( top,#ccc,#000);`
>  `background: -o-linear-gradient( top,#ccc,#000);`
##### 五、CSS3的制作动画的几个属性：变形（transform）、转换（transition）和动画（animation）。
###### 5.1 Transform
>在[CSS3](http://www.w3.org/TR/css3-roadmap/)中[transform](http://www.w3.org/TR/css3-2d-transforms/)主要包括以下几种：**旋转rotate**、**扭曲skew**、**缩放scale**和**移动translate**以及**矩阵变形matrix**。
语法：`transform : rotate | skew |  scale |  translate | matrix `
###### 5.2 Transition
>[W3C](http://www.w3.org/)标准中对[css3](http://www.w3.org/TR/css3-roadmap/)的[transition](http://www.w3.org/TR/css3-transitions/)这是样描述的：“css的[transition](http://www.w3.org/TR/css3-transitions/)允许css的属性值在一定的时间区间内平滑地过渡。这种效果可以在鼠标单击、获得焦点、被点击或对元素任何改变中触发，并圆滑地以动画效果改变CSS的属性值。”
transition主要包含四个属性值：执行变换的属性：transition-property,变换延续的时间：transition-duration,在延续时间段，变换的速率变化transition-timing-function,变换延迟时间transition-delay.
语法：`transition:[transition-property] || [transition-duration] || [transition-timing-function] || [transition-delay]`
eg:`transition:all 0.5s ease-in`
###### 5.3 Animation
代码以及介绍省略


##### 欢迎关注我的简书文章：[六个周](https://www.jianshu.com/p/2c64fa018a3e)