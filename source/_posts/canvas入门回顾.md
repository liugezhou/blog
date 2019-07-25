---
title: Canvas入门回顾
date: 2018-09-16
categories:
- web前端
- HTML/CSS
tags: 
    - Canvas
---
>canvas我们多少都会有些接触，今天做一个回顾。

>首先，我们知道`<canvas> `是HTML5 中新增的元素，它可以结合JavaScript脚本绘制出各种各样的图形。

#####  一、下面以画一个五角星来简单对其一些方法进行速记
>第一步是定义canvas的长与宽。
```
<canvas id="test" width="800" height="500">
        您的浏览器不支持canvas属性
</canvas>
```
>第二步是获取DOM元素以及获取上下文
```
var dom= document.getElementById("test");
var ctx = dom.getContext("2d");
```
<!--more-->
>第三步画起点
```
ctx.moveTo(100,150);
```
>第四步开始画线的其余几个坐标
```
  ctx.lineTo(400,150);
  ctx.lineTo(130,350);
  ctx.lineTo(250,50);
  ctx.lineTo(350,350);
  ctx.lineTo(100,150);
```
>第五步为五角星填充颜色
```
ctx.fillStyle="red";
ctx.fill();
```
>第六步为五角星添加borderWidth为10px的边框,并添加颜色
```
ctx.lineWidth=10;
ctx.strokeStyle="blue';
stc.stroke();
```
 至此，五角星画图完毕。总结上面我们要对基础的基础几个属性明明白白的。
>`getContext("2d)`
`moveTo()`
`lineTo()`
`fillStyle`
`fill()`
`lineWidth`
`strokeStyle`
`stroke()`

---
##### 二、深入一点点
###### 浏览器支持
>Internet Explorer 9、Firefox、Opera、Chrome 以及 Safari 支持 `<canvas> `及其属性和方法。
注释：Internet Explorer 8 以及更早的版本不支持 `<canvas> `元素
###### 其它属性
1️⃣、整体阴影（以下两个属性要一起使用）
>`shadowStyle`----设置或返回用于阴影的颜色
>`shadowBlur`----设置或返回用于阴影的模糊级别

2️⃣、阴影形状的水平或垂直
>`shadowOffsetX`----设置或返回阴影距形状的水平距离
>`shadowOffsetY`----设置或返回阴影形状的垂直距离
---
##### 三、一些方法
`createLinearGradient() `
>createLinearGradient() 方法创建线性的渐变对象
渐变可用于填充矩形、圆形、线条、文本等等。
提示：请使用该对象作为 [strokeStyle]或 [fillStyle] 属性的值。
提示：请使用 [addColorStop()]方法规定不同的颜色，以及在 gradient 对象中的何处定位颜色

`createPattern()`
>createPattern() 方法在指定的方向内重复指定的元素.
元素可以是图片、视频，或者其他 `<canvas> `元素。
被重复的元素可用于绘制/填充矩形、圆形或线条等等.
```
context.createPattern(image,"repeat|repeat-x|repeat-y|no-repeat");
```
` createRadialGradient()`
>createLinearGradient() 方法创建放射状/圆形渐变对象。
渐变可用于填充矩形、圆形、线条、文本等等。
提示：请使用该对象作为 [strokeStyle] 或 [fillStyle] 属性的值。
提示：请使用 [addColorStop()]方法规定不同的颜色，以及在 gradient 对象中的何处定位颜色

---
##### 四、线条样式
`lineCap`
>lineCap 属性设置或返回线条末端线帽的样式。
`round`和 `square` 会使线条略微变长。默认值为`butt`。

`lineJoin`
>lineJoin 属性设置或返回所创建边角的类型，当两条线交汇时。
注释：值 "miter" 受 [miterLimit](http://www.w3school.com.cn/tags/canvas_miterlimit.asp "HTML 5 canvas miterLimit 属性") 属性的影响。
属性值：`bevel`（斜角）、`round`（圆角）、`miter`（默认尖角）

` lineWidth`
>lineWidth 属性设置或返回当前线条的宽度，以像素计。
---
##### 五、矩形
`rect()`
>rect() 方法创建矩形。使用 [stroke()](http://www.w3school.com.cn/tags/canvas_stroke.asp "HTML5 canvas stroke() 方法") 或 [fill()](http://www.w3school.com.cn/tags/canvas_fill.asp "HTML5 canvas fill() 方法") 方法在画布上实际地绘制矩形。
>语法`context.rect(x,y,width,height)`

`fillRect()`
>fillRect() 方法绘制“已填色”的矩形。默认的填充颜色是黑色。
提示：请使用 [fillStyle](http://www.w3school.com.cn/tags/canvas_fillstyle.asp "HTML5 canvas fillStyle 属性") 属性来设置用于填充绘图的颜色、渐变或模式。

`strokeRect()`
>strokeRect() 方法绘制矩形（不填色）。笔触的默认颜色是黑色。
提示：请使用 [strokeStyle](http://www.w3school.com.cn/tags/canvas_strokestyle.asp "HTML 5 canvas strokeStyle 属性") 属性来设置笔触的颜色、渐变或模式。

`clearRect()`
>clearRect() 方法清空给定矩形内的指定像素。
---
##### 六、路径

>`fill()` : fill() 方法填充当前的图像（路径）。默认颜色是黑色.使用` fillStyle `属性来填充另一种颜色/渐变。
如果路径未关闭，那么 fill() 方法会从路径结束点到开始点之间添加一条线，以关闭该路径，然后填充该路径。

>` stroke()` : stroke() 方法会实际地绘制出通过 moveTo() 和 lineTo() 方法定义的路径。默认颜色是黑色。使用 [strokeStyle](http://www.w3school.com.cn/tags/canvas_strokestyle.asp "HTML5 canvas strokeStyle 属性") 属性来绘制另一种颜色/渐变。

>`beginPath()`:起始一条路径，或重置当前路径.

>`moveTo()` : 把路径移动到画布中的指定点，不创建线条

>`closePath()` : 创建从当前点回到起始点的路径

>`lineTo()` : 添加一个新点，然后在画布中创建从该点到最后指定点的线条.

>`clip()` : clip() 方法从原始画布中剪切任意形状和尺寸。

>`quadraticCurveTo()`: quadraticCurveTo() 方法通过使用表示二次贝塞尔曲线的指定控制点，向当前路径添加一个点。需要两个点，第一个点是控制点，第二个点是结束点。

>`bezierCurveTo()`:bezierCurveTo() 方法通过使用表示三次贝塞尔曲线的指定控制点，向当前路径添加一个点。三次贝塞尔曲线需要三个点。前两个点是用于三次贝塞尔计算中的控制点，第三个点是曲线的结束点。

>`arc()`: arc() 方法创建弧/曲线（用于创建圆或部分圆）

>`arcTo()` : arcTo() 方法在画布上创建介于两个切线之间的弧/曲线。

>`isPointInPath()`: isPointInPath() 方法返回 true，如果指定的点位于当前路径中；否则返回 false。
---
##### 七、转换
>`scale()`:缩放当前绘图至更大或更小.
语法：`ctx.scale(scalewidth,scaleheight);`

>`rotate()`:旋转角度，以弧度计。
如需将角度转换为弧度，请使用 degrees*Math.PI/180 公式进行计算。
举例：如需旋转 5 度，可规定下面的公式：5*Math.PI/180。

>`translate()`: translate() 方法重新映射画布上的 (0,0) 位置。

>`transform`:通过 transform() 添加一个新的变换矩阵。换句话说，transform() 允许您缩放、旋转、移动并倾斜当前的环境。
transform() 方法的行为相对于由 rotate(), scale(), translate(), or transform() 完成的其他变换.
语法：`context.transform(a,b,c,d,e,f);`

参数|描述
--|--
a |水平缩放绘图
b|水平倾斜绘图
c|垂直倾斜绘图
d|垂直缩放绘图
e|水平移动绘图
f|垂直移动绘图
---
##### 八、图象绘制
>`context.drawImage(img,sx,sy,swidth,sheight,x,y,width,height);`
drawImage() 方法在画布上绘制图像、画布或视频。
drawImage() 方法也能够绘制图像的某些部分，以及/或者增加或减少图像的尺寸。

