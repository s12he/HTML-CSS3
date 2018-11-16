[TOC]

# CSS3变换：
使用transform，可以实现元素的移动、缩放、转动、拉长或拉伸。值主要有以下4个：

## translate(x,y);
>移动元素。元素从其当前位置移动，根据给定的 left（x 坐标） 和 top（y 坐标）的位置参数
>
>比如：transform: translate(100px,100px);
>
>可拆分为：translateX(50px);translateY(100px);
>
>注意：transform: translate(100%,100px);如果单位是100%，则是以自身为参考，刚好移出本身宽度

## rotate(度数)
>旋转元素。元素顺时针旋转给定的角度。允许负值，元素将逆时针旋转。
>
>比如：transform:rotate(60deg);

## scale(x,y);
>拉伸缩放元素。
>
>比如:scale(2,4); 将元素拉伸至原来的2倍（宽）、4倍（高）
>
>可拆分为：scaleX();scaleY();

## skew(x,y); 
>倾斜元素。元素翻转给定的角度，根据给定的水平线（X 轴）和垂直线（Y 轴）参数：
>
>比如:skew(30deg,45deg)
>
>可拆分为：skewX();skewY();

可以将多个值合并在一起，用空格隔开。

## transform-origin 属性
>在使用了transform才能使用该属性（后3个）
>
>设置元素转换的基点位置：
>
>语法:transform-origin：x y;
>
>x的取值为left、center、right、px、%
>
>y的取值为top、center、bottom、px、%
>
>默认旋转中心为transform-origin：50% 50%;

# CSS3过渡：

>transition，通常是与变换样式一起使用，表明在节点间变换如何过渡
>
>transition-property  要运动的样式  （all || [attr] || none）
>
>transition-duration 运动时间(必填)
>
>transition-delay 延迟时间
>
>transition-timing-function 运动形式 
>
>ease：（逐渐变慢）默认值
>
>linear：（匀速）
>
>ease-in：(加速)
>
>ease-out：（减速）
>
>ease-in-out：（先加速后减速）

总结（记住）：

1. 动画一般是用户触发，所以会加在hover上或使用JS动态添加一个class来响应用户操作：比如鼠标摸上去或点击某个按钮等

+ transition属性不仅仅只是服务于transform属性，还服务于其他的任何可以实现位移或者状态改变的样式，比如盒模型。

+ transform只能用于块级和行内块级

+ 只有开始和结束两个状态（类似于鼠标摸上去和鼠标离开）。





