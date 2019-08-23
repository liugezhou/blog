---
title: iconfont在小程序端的使用
date: 2019-07-17
categories:
- web前端
- 小程序
tags: 
- 小程序
- iconfont
---
### 背景
> 最近自己在写一个小程序，在使用iconfont的时候，出了一点小问题，解决的过程是简单、高效的。  
> 想到之前就使用过iconfont，不过当时只是一笔带过。而今考虑到在项目中小icon的使用广泛，有必要简单总结一下使用iconfont方面的。
> 这篇博文不属于技术范畴，只能说是一个小小的技能吧--在个人开发中可以起到一个很好的技能拓展。
> <!-- more -->
### 概念
> 我们在开发过程中会用到很多的小图标，作为一个不会PS的前端，或者没有美工经验的前端，`iconfont-阿里巴巴矢量图标库`里面有很多的小图标可供我们选择使用。

### 范围
> `iconfont-阿里巴巴矢量图标库`地址：https://www.iconfont.cn/
> 可供web端、Android、iOS端使用。
> 官方文档的使用说明很明确：https://www.iconfont.cn/help/detail?spm=a313x.7781069.1998910419.d8d11a391&helptype=code
> 本文章只讨论小程序端关于Unicode的使用

### 应用
> 这里记录两种使用方法，可直接看最后的在线链接使用，两步搞定。
> 
### 本地使用
##### 步骤一
> - 将选好的小图标进行代码下载（此下载文件为1️⃣）
> - 打开这个平台[transfonter.org/](transfonter.org)
> - 点击Add fonts按钮,加载ttf格式的那个文件
> - 将下边的base64 encode改为on
> - 点击Convert按钮 进行转换
> - 转换后点击download下载，（此文件为2️⃣）
##### 步骤二
> - 在小程序本地新建 icon.wxss文件，并在app.wxss引入
> - 下载下来的文件（文件2️⃣）中有个 stylesheet.css文件，将其中代码copy至icon.wxss（注意这一步也可以直接在你新建的项目中找到在线连接、直接复制copy到stylesheet中也可以）
> - 将下载的文件1️⃣中除了@font-face中的其它部分，copy至icon.wxss便可使用
> - 在wxml中：`<text class="iconfont icon-time" style="font-size:30rpx;color:black"></text>`

### 在线链接使用
> - 将选好的小图标进行代码下载
> - 下载好的文件中`iconfont.css`种所有代码copy至iconfont.wxss
> - 在网站你的项目中找到在线链接，copy该`@font-face`替换`iconfont.css`中的`@font-face`