# 边框
+ `border-radius` 圆角(掌握：IE9以上支持)

> 值的设置：
>
>border-radius: 10px/20px;'/'左边是水平半径，右边是垂直方向半径
>
>border-radius: 10px 15px 20px 30px;上右下左
>
>border-radius: 10px 20px;左上角和右下角是半径10px，右上角和左下角是20px
>
>border-radius: 10px 20px 40px;左上为10px；右上和左下为20px；右下为40px；
>
>border-radius:50%;椭圆，如果是正方形则是正圆

+ `box-shadow`阴影(掌握：IE9以上支持)

>语法:box-shadow: h-shadow v-shadow blur spread color inset;spread：展开; 伸开；范围
>
>值的设置：
>
>box-shadow:5px 5px;水平、垂直阴影的位置，必需，颜色默认为黑色
>
>box-shadow:5px 5px black;
>
>box-shadow:5px 5px 5px black;模糊距离
>
>box-shadow:5px 5px 5px 5px black;阴影大小
>
>box-shadow:5px 5px 5px 5px black inset;内阴影,该值不要则为外阴影


# 背景图片（移动端常用）


以下3个熟悉都是为background-image服务的。
    
背景图片大小 (IE9)


>`background-size: px|percentage|cover|contain;`
>
>px：设置图片宽高，当宽高比例不一致时，会拉伸图片
>
>percentage：以父元素的百分比来设置，如果只设置一个值，则第二个值会被设置为 "auto"。当宽高比例不一致时，会拉伸图片
>
>cover：图片扩展到足够大，使背景图片覆盖背景区域，不会拉伸图片，直到背景区域填满为止
>
>contain：图片宽度或高度扩大到最大尺寸，使其宽高完全适应背景内容，不会拉伸图片

背景位置 (IE9)

>`background-origin:content-box|padding-box|border-box;`
>
>content-box：背景图像相对于内容框来定位
>
>padding-box ：背景图像相对于内边距框来定位(默认值)
>
>border-box：背景图像相对于边框盒框来定位