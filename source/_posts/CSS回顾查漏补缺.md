---
title: CSS3属性全回顾
date: 2019-07-29 22:33:54
updated: 2019-07-31 16:40:00 #手动添加更新时间
categories:
- web前端
- HTML/CSS
tags: CSS3
---
###### 作为一个前端开发者来说，对CSS的熟悉是基础中的基础。现如今框架眼花缭乱，炫酷的动画、美丽的UI，应接不暇，然而CSS3的本来面目是那么的简单，有很多的CSS3属性虽然特别的常见，但是灵活的运用还是需要我们对基础进行多次的夯实，本篇博客就是来对我们的CSS3的一些属性进行一个大而全的回顾。（可能大多数属性你都烂熟于心、你可以跳过它或者再次做一次温习）
|-webkit-|-ms-|-moz- |
|--|--|--|
<!--more-->

#### CSS边框
> 本节回顾两个属性`border-radius`、`box-shadow`
> 
>   |     属性  |    描述      |        扩展|
>   |-----------|--------------|-------------------|
>   |border-radius|给div元素添加圆角的边框<br>border-radius 属性是一个最多可指定四个 border -*- radius 属性的复合属性<br><br>若跟四个值其顺序是：<br>左上角、右上角、右下角、左下角|~~border-top-left-radius<br>border-top-right-radius<br>border-bottom-right-radius<br>border-bottom-left-radius<br>~~推荐写法:<br>border-radius:20px|
>   |box-shadow|该属性可以设置一个或多个下拉阴影的框<br>语法：<br>box-shadow:h-shadow v-shadow blur spread color inset|`h-shadow`  水平阴影位置--必填值（允许负值）<br>`v-shadow`  垂直阴影位置--必填值（允许负值） <br>`blur`  可选值--模糊距离<br>`spread`  可选值--阴影的大小<br> `color`  可选值-颜色<br>`inset`  可选值 --从外内的阴影（开始时）改变阴影内侧阴影 |
>   |border-image|

#### CSS3背景
>本节回顾以下背景属性：`bacground-image`、 `background-size`、 `background-origin`、 `background-clip`
>
>   |属性  |描述| 扩展|
>   | ---- |---- |----|
>   |background-image|添加背景图片(允许在元素上添加多个背景图像)| background: url(flower.png) right bottom no-repeat, url(summertrack.png) left top repeat;|
>   |background-size|指定背景图像的大小--该大小是相对于父元素的高度和宽度的百分比|background-size:20px 60px;<br>background-size:100% 100%;<br>background-size:cover--保持图像纵横比并将图像缩放成完全覆盖背景定位的最小大小<br>background-size:contain--保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。|
>   |background-origin|该属性指定了背景图像的位置区域|content-box<br>padding-box<br>border-box|
>   |background-clip|该裁剪属性是指从指定位置开始绘制|content-box<br>padding-box<br>border-box|
> 
#### CSS3的渐变
> 对CSS3渐变的高效使用，可以提升网站一个Level。  
> 我们来回顾：线性渐变（Linear Gradients）和径向渐变（Radial Gradients）  

> + 线性渐变（Linerar Gradients）：
> 从上到下（默认）：`background:linear-gradient(red,blue,...)`  
> 从左到右： `background:linear-gradient(to right,red,blue,...)`  
> 从左上角到右下角度： `background:linear-gradient(to right bottom,red,blue,...)`  
> 角度定义：`background:linear-gradient(45deg,red,blue,...)`  
>
> + 径向渐变（Radial Gradients）:
> 颜色结点均匀分布（默认情况下）:`background:radial-gradient(red,green,blue)`  
> 颜色结点不均匀分布：`background:radial-gradient(red 10%,green 20%,blue 30%)`
> 设置形状：`background: radial-gradient(circle | ellipse, red, yellow, green);`

#### CSS3文本效果
> 这里我们来回顾以下文本效果的以下几个属性：`text-shadow`、`text-overflow`、`word-wrap`、`word-break`
> 
>   | 属性 | 描述 | 扩展 |
>   | ---- |---- |----|
>   |text-shadow|文本阴影<br>语法：<br>text-shadow: h-shadow v-shadow blur color;|`h-shadow`  水平阴影位置--必填值（允许负值）<br>`v-shadow`  垂直阴影位置--必填值（允许负值） <br>`blur`  可选值--模糊距离<br>`spread`  可选值--阴影的大小|  
>   |text-overflow|文本溢出属性指定应向用户如何显示溢出内容（clip、ellipsis、string）|clip --修剪文本<br>ellipsis--显示省略号代替被修剪的文本<br>string -- 使用给定的字符串来代表被修剪的文本|  
>   |word-wrap|允许对长的不可分割的单词进行分割并换行到下一行。（normal、break-word）| normal--只在允许的断字点换行<br>break-word--在长单词或URL地址内部进行换行|  
>   |word-break|规定非中日韩文本的换行规则|normal--使用浏览器默认的换行规则。<br>break-all--允许在单词内换行。<br>keep-all--只能在半角空格或连字符处换行。|
> 	
#### 2D转换
> transform:translate(x,y)、rotate(angle)、scale(x,y)、skew(x-angle,y-angle)、matrix()
>移动、旋转、放大缩小、倾斜。
> 不展开叙述。


#### CSS3过渡 || CSS3动画
> + 过渡属性
> `transition`:简写属性，用于在一个属性中设置四个过渡属性。 
> `transition-property`:规定应用过渡的CSS属性的名称。 
> `transition-duration`：定义过渡效果花费的时间。默认为0  
> `transition-timing-function`:规定过渡效果的时间曲线  
> `transition-delay`:规定过渡效果何时开始
>
> + 动画属性
> |属性|描述|
> |---|---|
>|`@keyframse`|规定动画|  
> |`animation`|所有动画的简写属性，除了`animation-play-state`属性 | 
> |语法：|`animation: name duration timing-function delay iteration-count direction fill-mode play-state;`|
> |`animation-name`|规定@keyframes动画的名称 | 
> |`animation-duration`|规定动画完成一个周期所花费封秒或毫秒 |
> |`animation-timing-function`|规定动画的速度曲线：默认为[ease（低速-加快-变慢）] |
>  | 其它值|linear(匀速)、ease-in(动画以低速开始)、ease-out(动画以低速结束)、ease-in-out(动画以低速开始和结束) |
> |`animation-fill-mode`|规定当动画不播放时（当动画完成或者延迟未开始播放时），要应用到的元素的样式。|
> |`animation-delay`|规定动画何时开始  |
> |`animation-iteration-count`|规定动画被播放的次数   [infinite]无限次  |
> |`animation-direction`|规定动画是否在下一周期逆向地播放。默认是[normal]  |
> |animation-direction -- reverse|动画反向播放|
>  |animation-direction --alternate|动画在奇数次（1、3、5...）正向播放，在偶数次（2、4、6...）反向播放。|
>  |animation-direction--alternate-reverse|动画在奇数次（1、3、5...）反向播放，在偶数次（2、4、6...）正向播放|
> |`animation-play-state`|规定动画是否正在运行或暂停。默认是[running]|

#### CSS3多列
> 关于CSS3的多列属性我好像还真没用到过，看到了就记录一下吧。
> 
> |属性 | 描述|
> |------|------|
> |column-count| 指定了需要将一段文字分隔的列数 |
> |column-gap|该属性指定了列与列之间的缝隙 |
> |column-rule-width|指定了两列的边框厚度  |
> |column-rule-style|指定了列与列之间的边框样式（solid \| dotted） |
> |column-rule-color|指定了两列的边框颜色 |
> |column-rule|是上述三个属性的缩写 |
> |column-span| 指定元素跨越所有列|
> |column-width| 指定了列的宽度|

#### CSS3用户界面

> |属性|描述|
> |---|---|
> |resizing|指定一个元素是否应该由用户去调整大小|
> |box-sizing|当你设置一个元素为box-sizing:border-box时，此元素的内边距和边框便不再增加它的宽度了 |
> |outline-offset|对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓|

#### CSS3图片
> + 响应式图片

    img{
        max-width:100%;
        height:auto;
    }

> + 图片文本
>定义图片文本的时候结合position:relative和position:absolute。

> + 响应式图片相册
> 在这里正确用好这几个属性：`box-sizing:border`、`@media`、`clear:both`

#### CSS3弹性盒子-Flex布局
> 之前总结过一篇：[Flex布局](https:/www.liugezhou.online/2018/08/22/Flex布局/)

#### CSS3多媒体查询
> CSS3多媒体类型
>
> |   值   |  描述|
> |-----------|-----------|
> |all|用于所有多媒体类型设备|
> |print|用于打印机|
> |screen|用于电脑屏幕、平板、智能手机等|
> |speech|用于屏幕阅读器|