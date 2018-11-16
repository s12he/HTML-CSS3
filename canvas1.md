[TOC]

# 画图步骤:画布

	<canvas id="can" width="400" height="400">您的浏览器不支持canvas画图</canvas>

1. 默认宽高:300*150.单位不能用百分比表示,canvas会将百分值当成数值显示
2. 为避免异常，应使用属性来设置canvas宽高，而不是能用css设置
3. 在标签内部插入一些提示文字，这样当浏览器不支持该标签时会将提示内容显示出来

# 画笔

	var c=document.getElementById("canvas");
    var ctx=c.getContext("2d");
	
当前唯一的合法值是2d,是一个CanvasRenderingContext2D 对象，使用它可以绘制图形到canvas元素中

	检测getContext 的支持性
            if(c.getContext){
                var ctx=c.getContext("2d");
                //todo..
            }

# 绘制形状的方法(是画笔对象中的方法，使用画笔调用)
### 1.只支持一种原生的图形绘制方法：矩形
>+ 空心矩形: `ctx.strokeRect(x, y, width, height)`
>+ 实心矩形: `ctx.fillRect(x, y, width, height)`
>+ 清除现有矩形的某一个部分: `ctx.clearRect(x, y, width, height)`

>x,y 表示离画布左上角的坐标(0,0)

>width,height 是绘制的矩形的大小

### 2.使用路径绘制图形(直线、矩形、圆形)
+ 主要的方法
>先声明要画路径: `ctx.beginPath()`
>
>起点: `ctx.moveTo(20,20)`
>
>下一个起点（如果是直线，则是终点）: `ctx.lineTo(40,50)`
>
>通过线条来绘制图形轮廓: `ctx.stroke()`
>
>填充路径的内容区域生成实心的图形: `ctx.fill() `
>
>声明路径画完: `ctx.closePath()`

+ 画三角形
>     ctx.beginPath()
      ctx.moveTo(x,y) //起点
      ctx.lineTo(x,y) //下一个起点（如果是直线，则是终点）
      ctx.lineTo(x,y) //下一个起点（如果是直线，则是终点）
	  ctx.lineTo(x,y) //如果要闭合三角形，最后一个点要和第一个点重叠）
      ctx.stroke();   //每次路径画完后，如果要看到该路径，需要描边或填充
      ctx.fill(); 
	  ctx.closePath()

+ 画有轮廓有填充的矩形
>     ctx.beginPath()
>     ctx.rect(x,y,width,height)
>     ctx.stroke();
>     ctx.fill(); 
>     ctx.closePath()

+ 画圆弧
>ctx.arc(x, y,半径, 开始弧度,结束弧度, anticlockwise)
>
>anticlockwise 是否是逆时针：值为true时逆时针，false为顺时针[默认值]
>
>`角度=弧度*180/Math.PI`
>
>`弧度=角度*Math.PI/180`
>
>`2π弧度=360度`
>
>实例:
>
>     ctx.beginPath();
>     ctx.arc(250,250,200,0,2*Math.PI,true);
>     ctx.fill();

# 设置画笔的样式和颜色
+ 设置颜色(默认是黑色)
> `ctx.fillStyle = color`      设置图形的填充颜色
> 
> `ctx.strokeStyle = color`     设置图形轮廓的颜色

+ 设置画笔大小
>`ctx.lineWidth = 5`

+ 设置画布透明,值的范围为0~1
>`ctx.globalAlpha=0.5`