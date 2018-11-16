[TOC]

# 线条的样式(属性+方法)

+ 线条末端的属性：

    **lineCap**="butt(默认值)|round|square"

+ 线条交点的样式：

    **lineJoin**="miter（默认值）|bevel|round"

+ 设置线条为虚线:

    **setLineDash([虚线的长度,虚线间的间隔])**

+ 虚线的偏移量属性:

    **lineDashOffset=数值**

# 文字

+ 空心字:(x:横坐标,y:纵坐标,maxw:最大宽度,maxh:最大高度)

	**pen.strokeText( text, x, y, maxw, maxh)**

+ 实心字:

	**pen.fillText( text, x, y, maxw, maxh)**

# 渐变

>使用：将得到的渐变赋值给fillStyle或strokeStyle
>
>x0,y0指的是渐变的起点，x1,y1指的是渐变的终点
>
>生成渐变的方法：`var clg = pen.createLinearGradient(x0,y0,x1,y1)`
>
>给渐变添加色标(0~1之间): `clg.addColorStop(色标，颜色)`

# 图片绘制
+  图片的来源（导入图片）
>a、直接获取img标签
>
>b、使用JS生成一个img对象，再通过src属性导入一张图片
>

+ 绘制（显示到画布上）
>cxt.drawImage(图像对象,x,y) 
>
>例子:
>
>     var can=document.getElementById("can");
>      var pen=can.getContext("2d"); 
>      var oImg=document.createElement("img");
>      oImg.src="img/toy.png";
>       // 调用绘制方法
>       window.onload=function(){
>        // 将img标签变成对象
>        pen.drawImage(oImg,0,0);
>        // drawImage(oImg,70,0,图片宽度,图片高度);
>        pen.drawImage(oImg,70,0,50,50);
>        // drawImage(oImg,70,0,图片宽度,图片高度);
>        // drawImage(img,sx,sy,sw,sh,x,y,w,h);//被切的图片的位置、大小，放置到坐标和大小
>       }	


