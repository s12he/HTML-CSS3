[TOC]

# CSS3盒模型

box-sizing: content-box(标准)|border-box(怪异);

## 标准模型


默认情况下，元素的宽度与高度计算方式如下：

width(宽) + padding(内边距) + border(边框) = 元素实际宽度

height(高) + padding(内边距) + border(边框) = 元素实际高度

## 怪异模型

将padding(内边距) + border(边框)的宽度也包含在width值中，即

width(宽)=元素实际宽度

用法：

在元素上设置 `box-sizing: border-box`; 

则 padding(内边距) 和 border(边框) 也包含在 width 和 height 中。

box-sizing: border-box(怪异)|content-box(标准);


# 多列

column  美['kɑ:lem]  列、圆柱


可以将文本内容设计成像报纸一样的多列布局

注意：不要指望使用该属性实现div布局，比较困难      

CSS3 多列属性:

`columns`             /* column-width 和 column-count 的简写*/

`column-count`    /*需要分割的列数*/

`column-width`    /*列的宽度,要求较多，没啥用*/

`column-gap`          /*列与列间的间隙,默认值未明确给出，IE为16px*/ **相当于是margin-right**

`column-rule`         /*column-rule-* 所有属性的简写*/ **相当于是border-right**

`column-rule-style`   /*列与列间的边框样式*/

`column-rule-width`   /*两列的边框厚度*/
 
`column-rule-color`   /*两列的边框颜色*/

`column-span`:1|all        /*元素跨越多少列*/

兼容性：IE10及以上、谷歌、火狐支持

# CSS3 弹性盒子

flex是Flexible box弹性盒子的缩写。

兼容性：IE10及以上、谷歌、火狐支持

之前页面布局得使用浮动、盒子模型、定位实现，而且部分特殊布局，比如绝对居中布局不太好做。于是w3c在2009年推出了弹性布局方案。[链接](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

弹性盒子是 CSS3 的一种新的布局模式。

弹性盒子由弹性容器(Flex container)和弹性子元素(Flex item)组成。

弹性容器外及弹性子元素内是正常渲染的。弹性盒子只定义了弹性子元素如何在弹性容器内布局。

弹性子元素通常在弹性盒子内一行显示。默认情况每个容器只有一行。

## 在父级盒子中定义，目的是让子盒子拥有弹性盒子(container)：
### display:flex;           /*块元素*/

### flex-direction属性定义子盒子的方向（X方向即主轴方向排列子元素）
取值：

+ **row** (默认:left to right)
+ **row-reverse**(相当于将元素反转过来:right to left)
+ **column**(从上到下)
+ **column-reverse**(从下到上)

### justify-content 属性应用在弹性容器(父元素)上，把弹性项(子元素)沿着弹性容器的主轴线（main axis）对齐。
取值：justify-content:flex-start(默认值)|flex-end|center|space-between|space-around;
      
+ **flex-start：**
>弹性项目向行头紧挨着填充。这个是默认值。第一个弹性项的main-start外边距边线被放置在该行的main-start边线，而后续弹性项依次平齐摆放。
>
>人话：子元素在主轴开始位置，富裕空间在主轴结束位置。

+ **flex-end：**
>弹性项目向行尾紧挨着填充。第一个弹性项的main-end外边距边线被放置在该行的main-end边线，而后续弹性项依次平齐摆放。
>
>人话：与flex-start相反，子元素在主轴结束位置，而富裕空间在子元素开始位置。

+ **center：**
>弹性项目居中紧挨着填充。（如果剩余的自由空间是负的，则弹性项目将在两个方向上同时溢出）。
>
>人话：子元素在主轴中间位置，富裕空间在主轴两侧

+ **space-between：**
>弹性项目平均分布在该行上。如果剩余空间为负或者只有一个弹性项，则该值等同于flex-start。否则，第1个弹性项的外边距和行的main-start边线对齐，而最后1个弹性项的外边距和行的main-end边线对齐，然后剩余的弹性项分布在该行上，相邻项目的间隔相等。
>
>人话：富裕空间平均分配在每两个子元素之间。

+ **space-around：**
>弹性项目平均分布在该行上，两边留有一半的间隔空间。如果剩余空间为负或者只有一个弹性项，则该值等同于center。否则，弹性项目沿该行分布，且彼此间隔相等（比如是20px），同时首尾两边和弹性容器之间留有一半的间隔（1/2*20px=10px）。
>
>人话：富裕空间平均分配在每个元素的两侧。
            
### align-items

可以理解为单行子元素在父容器中的垂直方向的对齐方式

即纵轴方向的富裕空间管理（留白）

取值：stretch(默认值)|align-items:flex-start|flex-end|center|baseline;

+ **stretch：**元素被拉伸至纵轴起始结束位置，如果该元素不写高度则无富裕空间
+ **flex-start:** 元素在纵轴起始位置，富裕空间在纵轴结束位置
+ **flex-end:** 元素在纵轴结束位置，富裕空间在纵轴开始位置
+ **center:** 元素在纵轴中间位置，富裕空间在纵轴两侧（上下）位置
+ **baseline:** 元素根据纵轴文字上的基线对齐。
                

## 在子元素中使用(item)：

flex是flex-grow、flex-shrink（收缩）、flex-basis的简写

### flex-grow 属性用于指定弹性子元素如何分配空间。可简写为flex
>即：盒子的弹性空间
>
>如果有3个子元素，第一个为flex:2,其他为1，则表示前者占2/4,后两者各占1/4.
>
>注意：使用后，该子元素的宽度值将失效

### order:子元素排序
>取值：阿拉伯数字<integer>：用整数值来定义排列顺序，数值小的排在前面。可以为负值
        





