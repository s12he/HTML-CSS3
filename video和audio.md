[TOC]

+ 为什么存在多种视频格式：

因为每个浏览器内置的音视频解码器都不太一样，有些浏览器用的是免费的解码器，有些是收费的，所以导致浏览器之间支持的音视频格式不一样。

+ 为什么每个浏览器的播放界面都不一样：

这是因为H5没有制定统一的视频外观，所以视频外观全部都是由浏览器自定义的。

+ 如何做到兼容性：

在video内嵌套另一个标签source标签

# video标签
HTML5展示视频的标准——video

每个网页显示视频的标准不一样，大多数通过插件（flash）来实现，但并非所有的浏览器都用同一个插件
video 元素支持三种视频格式：MP4, WebM, 和 Ogg

## 标签定义及属性：

**属性：**

1. **width、height**定义宽高 默认300*150（视频拥有）
2. **controls** 	规定标签是否显示视频播放控件 controls='controls'
3. **src**			文件路径
4. **poster**		规定视频加载时显示的照片（视频拥有）
5. **paused**		是否暂停了，true表示暂停，false表示播放了
6. **currentTime**	视频播放到当前哪个时间（可读写）
7. **playbackRate**	视频播放速度（1.0正常播放，0.5半速播放，2.0，2倍播放）
8. **muted**		是否静音
9. **volume**		音量最大为1，静音为0，可每次减少0.3
10. **autoplay**	视频在就绪后马上播放
11. **loop**		设置播放完了是否循环播放  loop="loop"
12. **preload**		如果出现该属性，则视频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。
13. **duration**    媒体总时长（只读）

**方法：**

1. **play()**		播放视频
2. **pause()**		暂停播放
3. **load()**		更改视频源后重新加载视频，通过source更新的源必须重新load才能应用更改

## 实例：利用属性和方法自定义按钮

1. 快进：`v1.currentTime+=2;`
2. 快退：`v1.currentTime-=2;`
3. 2倍速度播放：`v1.playbackRate=2;`
4. 正常播放：`v1.playbackRate=1;`
5. 静音：`v1.muted=true;`
6. 加大声音：`v1.volume+=0.3;`

# audio标签

定义声音，比如音乐或其他音频流,<audio> 元素支持的3种文件格式：MP3、Wav、Ogg属性和方法与video类似

1. **src**		要播放的音频的 URL
2. **autoplay**	音频在就绪后马上播放 
3. **controls**	是否显示控件 
4. **loop**		设置播放完了是否循环播放  loop="loop"
5. **preload**	如果出现该属性，则视频在页面加载时进行加载，并预备播放。如果使用 "autoplay"，则忽略该属性。

# source标签

可以加载多个格式的视频源文件,浏览器会按照它所支持的格式去加载视频

**属性(type)：**

视频 video/ogg、video/mp4、video/webm

音频 audio/ogg、audio/mpeg

**示例：**

	<video id="v1" poster="poster.jpg" controls="controls">
		<source id="sr1" src="movie.webm" type="video/webm"></source>
		<source id="sr1" src="movie.ogg" type="video/ogg"></source>
	</video>

# 控制播放器是否全屏：

	if(element.requestFullscreen) {
       element.requestFullscreen();
     } else if(element.mozRequestFullScreen) {
       element.mozRequestFullScreen();
     } else if(element.msRequestFullscreen){ 
       element.msRequestFullscreen();  
     } else if(element.oRequestFullscreen){
        element.oRequestFullscreen();
    }
    else if(element.webkitRequestFullscreen)
     {
       element.webkitRequestFullScreen();
      }