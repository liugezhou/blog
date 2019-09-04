---
title: 一、Vue-cli脚手架安装以及项目初始化
date: 2019-01-05 00:00
updata: 2019-08-11 18:43
categories:
- Vue2.0开发企业级移动音乐APP
tags: 移动音乐APP
---
##### 本章节分为两个部分，第一部分简单介绍下Vue-cli的脚手架安装，第二部分介绍下项目目录以及图标字体、公共样式等资源的准备。
---
<!--more-->
### 一、Vue-cli脚手架安装
>在进行项目初始化安装cli前，我们先在github上新建一个空的项目，项目名字自起。
我新建gitHub地址为：https://github.com/liugezhou/liugezhou_music
### 将gitHub上新建的项目克隆到本地
>打开终端，cd到DeskTop，执行命令git clone  git@github.com:liugezhou/liugezhou_music.git
### Vue-cli脚手架的安装
---
>cli脚手架安装前请确认你的电脑已经安装了`node`、`webpack`,并且对node的使用有一些基础知识储备。
我的vue版本号为：`2.9.6`，webpack版本号为`7.14.2`.

>+ 第一步、 现在Vue-cli的版本已经到3.x了，但是由于课程是基于2.x的，所以我们在全局安装vue-cli脚手架的时候，使用的命令是：
```
$ npm install -g vue-cli
```
>+ 第二步、cd 到DeskTop，终端中执行命令(这一步需要选择几项，不展开叙述)
```
$ vue init webpack liugezhou_music
```
>+ 第三步、cd到项目中
```
#安装项目依赖包-node_modules
npm install
```
>第四步、项目启动
```
npm run dev
```
项目启动效果如图：
![music.png](https://upload-images.jianshu.io/upload_images/2054455-a7de0cd49a1cc0af.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
### 脚手架安装小结
----
>首先确保你的电脑安装了`node`、`webpack`和`git`，以及一款开发工具，推荐使用`VSCode`。

>篇幅虽小，但是理解其中每一行代码并做到手动从零搭建每一步也是需要下一点的时间去操作，还有关于脚手架生成的文章目录也未做详细介绍，这里也需要刚开始学习脚手架的同学去花一点时间，去理解每一个文件的作用。
---
### 二、项目目录介绍以及图标字体、公共样式等资源的准备。
##### 1、新建分支chapter1
>项目初始化好后，开始代码的编写，首先在git上`新建一个chapter1分支`，用来提交本节项目代码。
新建好分支后，在本地项目中`git pull`一下，拉取最新分支。
然后执行`git checkout chapter1`,切换到当前分支，现在我们便可以在本分支下进行项目的开发
##### 2、项目初始化
>可直接在  
https://github.com/liugezhou/liugezhou_music/tree/chapter1 这里查看当前章节完整代码。
与cli脚手架工具相比，主要做了以下修改：
+ build/webpack.base.conf.js --------添加common别名
+ src目录重新部署，主要下添加字体、样式、图片等文件夹：
  >`api`:跟后端请求相关代码，包括ajax和jsonp的请求，目前为空
  >`common`:一些通用资源，包括font字体文件、image图片、js、`stylus通用样式文件`(本节重要)
  >`components`:公共组件
  >`router`:路由
  >`store`：与vuex相关代码
  >`App.vue`、`main.js`
+ package.json中添加stylus、stylus-loader依赖(vue-cli脚手架默认是不会安装的)。
##### 3.分支提交(为了代码分级的阅读方便)
>本分支开发完成后，需要将chapter1的代码提交到远程分支，并合并到主分支，依次执行代码如下：
```
git add .
git commmit -m 'finish chapter1'
git push
git checkout master
git merge chapter1
git push
```
---
本节完。
2019.01.05

####  2019.08.11复习总结
> 1.由于项目用了eslint语法检查，本节修改了一下`.eslintrc.js`文件，多加了两行
> ```
>   'eol-last': 0, //不检查新建文件末尾是否有空行
>    'space-before-function-paren': 0 // 方法前后有无空格不检查
>  ```
> 2.项目路径别名在`build/webpack.base.config.js`中的resolve/alias下修改。


>关于本节如果你有任何问题可以在下方留言。
>如有疑问请添加我的微信号：18231133236。欢迎交流！  
>更多内容，请访问的我的个人博客：[https://www.liugezhou.online](https://links.jianshu.com/go?to=https%3A%2F%2Fwww.liugezhou.online).
