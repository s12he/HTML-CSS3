**CSS3基本原理：**

1. 使用@keyframes

2. animation 属性绑定@keyframes 规则

### @keyframes 规则定义动画样式

@keyframes规则内指定一个CSS样式和动画将逐步从目前的样式更改为新的样式。


语法：

	@keyframes animationname {
		keyframes-selector {css-styles;}
	}

keyframes-selector	必需的。动画持续时间的百分比。

合法值：取值：0-100%、from (和0%相同)、to (和100%相同)

实例：当动画为 25% 及 50% 时改变背景色，然后当动画 100% 完成时再次改变

	@keyframes myfirst
	{
	    0%   {background: red; left:0px; top:0px;}
	    25%  {background: yellow; left:200px; top:0px;}
	    50%  {background: blue; left:200px; top:200px;}
	    75%  {background: green; left:0px; top:200px;}
	    100% {background: red; left:0px; top:0px;}
	}

### animation 所有动画属性的简写属性，除了 animation-play-state 属性。

实例：

	div{
	    animation: myfirst 5s linear 2s infinite alternate;
	    /* Safari 与 Chrome: */
	    -webkit-animation: myfirst 5s linear 2s infinite alternate;
	}

所有animation属性:

>`animation-name`: myfirst;/*@keyframes动画名称*/
>
>`animation-duration`: 5s;/*动画完成一个周期所花费的秒或毫秒。默认是 0。*/
>
>`animation-timing-function`: linear;/*动画的速度曲线。默认是 "ease"。*/
>
>`animation-delay`: 2s;/*动画何时开始。默认是 0*/
>
>`animation-iteration-count`: infinite;/*动画被播放的次数。默认是 1。*/值n、infinite（无限次）*/
>
>`animation-direction: alternate`;/*动画是否在下一周期逆向地播放。默认是 "normal"。也就是偶数次会改变动画方向，动画交替的执行*/    
>
>`animation-play-state`: running;/*动画是否正在运行或已暂停，值running、paused*/
>
>`infinite`:无限次
>
>`alternate`:交替的，轮流的。走之字形




