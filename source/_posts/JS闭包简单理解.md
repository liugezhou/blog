---
title: JS闭包简单理解
date: 2018-10-15
categories:
- web前端
- JavaScirpt
tags: 
    - 闭包
---
##### 1、先来看一个闭包的代码小例子：

    var scope = "全局scope"; 
    function checkScope() {
    var scope = "内部scope";
    function f() {
        return scope;
    }
    return f();
    }
    checkScope();   //=> "内部scope"
闭包可以捕获到局部变量和参数的外部函数绑定，即便外部函数的调用已经结束。
<!--more-->
[词法作用域的规则，即函数被执行时(executed)使用的作用域链(scope chain)是被定义时的scope chain，而不是执行时的scope chain，就可以很容易的理解闭包的行为了。](https://www.jianshu.com/p/132fb6d485ee)
##### 2、在javascript语言中，闭包就是函数和该函数作用域的组合。从这个概念上来讲，在js中，所有函数都是闭包（函数都是对象并且函数都有和他们相关联的作用域链scope chain）。简单说：闭包就是有权访问另一个函数作用域中变量的函数.
##### 3、在ES6之前，函数只能在全局作用域和函数作用域中声明，不能在块级作用域中声明。没有块级作用域导致很多场景不合理，闭包在一些地方很好解决了这个不合理。
##### 4.闭包的使用场景
>场景描述：假如页面上有5个button,要给button绑定onclick事件，点击的时候，弹出对应button的索引编号。
    
    #html
    <!DOCTYPE html>
    <html>
    <head>
     <meta charset="UTF-8">
    </head>
    <body>
    <button>Button0</button>
    <button>Button1</button>
    <button>Button2</button>
    <button>Button3</button>
    <button>Button4</button>
    </body>
    </html>
    #js
    ...
    var btns = document.getElementsByTagName('button');
    for(var i = 0, len = btns.length; i < len; i++) {
    btns[i].onclick = function() {
        console.log(i);
    }
    }
    ...
通过执行该段代码，发现不论点击哪个button ，均输入4；
这显然不符合我们的需求，我们我们需要修改代码：
1️⃣ 将for循环中的var 变为let
2️⃣Tip： 在ES6之前，没有块级作用域 ，只有函数作用域(即：通过var声明的变量没有块级作用域)。可以采用“立即执行函数”的方式创建作用域。

    for(var i = 0, len = btns.length; i < len; i++) {
    (function(i) {
        btns[i].onclick = function() {
           console.log(i);
        }
    }(i))
    }
##### 5、闭包注意点
>由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。

