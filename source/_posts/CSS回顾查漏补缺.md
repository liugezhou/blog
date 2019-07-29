---
title: CSS回顾查漏补缺
date: 2019-07-29 22:33:54
updated: 2019-07-29 20:58:54 #手动添加更新时间
categories:
- web前端
- HTML/CSS
tags: flex
---
###### 作为一个前端开发者来说，对CSS的熟悉是基础中的基础，然而由于我们一些书写习惯的问题，导致一些很简单的布局会走一些弯路，所以：实时的对自己的CSS布局掌握查漏补缺显得是尤为的重要，本篇博文便是回顾一些CSS的基础，对基础内容进行巩固。
<!--more-->
#### max-width
> max-width属性摘代码的时候看到的比较多，但是我本身在写代码的时候缺极少用到。  
> 这个属性可以很好的使浏览器来处理小窗口的情况，而且在移动设备上显得尤为重要，  
> 特别是一个布局想在PC和移动端适配显示的时候。

#### box-sizing
> 这是一个很有用处的属性，当你设置一个元素为box-sizing:border-box时，此元素的内边距和边框便不再增加它的宽度了。

    -webkit-box-sizing:border-box
       -moz-box-sizing:border-box
            box-sizing:border-box

#### absolute
> 这个之所以提出来，是因为我之前用到此属性的时候，模棱两可。
> 此 `position:absolute` 是相对于最近的 `postion` 祖先元素的，比较常用的是父元素设置为`posotion:relative`时在使用。
> 若没有属性为`position`的祖先元素，则此属性是指相对于文档的`body`元素。

#### 文字多列布局

    .three-column {
        padding: 1em;
        -moz-column-count: 3;
        -moz-column-gap: 1em;
        -webkit-column-count: 3;
        -webkit-column-gap: 1em;
        column-count: 3;
        column-gap: 1em;
     }

#### 今天先到此处
