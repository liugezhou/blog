---
title: CSS3属性回顾
date: 2019-07-29 22:33:54
updated: 2019-07-30 23:38:54 #手动添加更新时间
categories:
- web前端
- HTML/CSS
tags: flex
---
###### 作为一个前端开发者来说，对CSS的熟悉是基础中的基础，然而由于我们一些书写习惯的问题，导致一些很简单的布局会走一些弯路或者对某些属性运用不频繁，所以：实时的对自己的CSS布局掌握查漏补缺显得是尤为的重要，本篇博文便是回顾一些CSS的基础，对基础内容进行巩固。
<!--more-->

#### absolute
> 这个之所以首先提出来，是因为我之前用到此属性的时候，模棱两可。
> 此 `position:absolute` 是相对于最近的 `postion` 祖先元素的，比较常用的是父元素设置为`posotion:relative`时在使用。
> 若没有属性为`position`的祖先元素，则此属性是指相对于文档的`body`元素。

#### 线性渐变
> CSS的线性渐变是真的漂亮，对线性渐变的高效使用，可以提升网站一个Level。  
> 让我们重新回味下两种线性渐变：线性渐变（Linear Gradients）和径向渐变（Radial Gradients）  

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

#### 2D转换
> transform:translate(x,y)、rotate(angle)、scale(x,y)、skew(x-angle,y-angle)、matrix()
>移动、旋转、放大缩小、倾斜。
> 不展开叙述。

#### 3D转换
>  这块回头写

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
>定义图片文本的时候结合上文提到的position:relative和position:absolute。

> + 响应式图片相册
> 在这里正确用好这几个属性：`box-sizing:border`、`@media`、`clear:both`

#### 今天就先到这里吧

