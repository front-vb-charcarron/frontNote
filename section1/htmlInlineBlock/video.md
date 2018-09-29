#video标签
>视频标签



|属性名|描述|
| :---: | :---: |
|src|文件源|
|loop|循环播放|
|autoplay|自动播放|
|preload|预加载|
|controls|控制面板|
|width|视频播放器的宽度|
|height|视频播放器的高度|



###常规用法
```html
	<video src="xxx.mp4" preload autoplay controls width="300" height="200">
		<source src="xxx.mp4" type="video/mp4"></source>
		<source src="xxx.mp4" type="video/mpeg"></source>
		<source src="xxx.mp4" type="video/avi"></source>
		<p>您的浏览器不支持video标签</p>
	</video>
```


###关于微信h5视频类型推广页面的问题：


|属性|属性值|描述
| :---: | :---:|:---: |
|preload|none|禁止了自动加载，由用户决定加载的时机|
|webkit-playsinline|true|是ios 10中设置可以让视频在小窗内播放，也就是不是全屏播放|
|playsinline|true|微信浏览器支持小窗内播放|
|x-webkit-airplay|allow|这个属性应该是使此视频支持ios的AirPlay功能|
|x5-video-player-type|h5|启用H5播放器,可以让视频全屏播放并不显示进度条，并且支持在视频上叠放任意元素，但在安卓上会有一下的闪屏.|
|x5-video-player-fullscreen|true|全屏设置,它有两个属性值，ture和false，true支持全屏播放，false不支持全屏播放|
|x5-video-orientation|portraint|播放器支持的方向，landscape横屏，portraint竖屏，默认值为竖屏|

> android视频能在本地服务器测试播放 ，而ios需要上传到服务器在微信内置浏览器才能正常播放(貌似是因为合法域名，可以尝试phpStudy来转一下域名测试)。
> 视频格式为H.264,码率能影响视频的质量。
> 如果想要在微信端自动播放视频可以使用wx.ready();
