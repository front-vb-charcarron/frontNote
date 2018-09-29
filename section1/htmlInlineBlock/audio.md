#audio标签
>音频标签



|属性名|描述|
| :---: | :---: |
|preload|预加载|
|autoplay|自动播放|
|controls|控制面板|
|loop|循环播放|



可以缩写成 autoplay 等等。。
考虑多文件类型写法
```
<audio src="media/Audio/xxxxx.mp3" controls="controls" preload autoplay loop></audio>
<audio  controls="controls" preload autoplay loop>
<source src="media/Audio/xxxxx.mp3" type="audio/mp3"></source>
<source src="media/Audio/xxxxx.ogg" type="audio/ogg"></source>
<p>您的浏览器不支持音频播放请尽快<a href="http://www.baidu.com"></a></p>
</audio>
```


>尽量使用mp3后缀名，基本可以兼容全部浏览器

解决ios音乐在微信端不能播放的问题:

```
	document.addEventListener("WeixinJSBridgeReady",function(){
		music.play();
	});
```