#a标签
>专门用于链接各个网页的传送门。


###常规用法

```
	超链接标签`<a href="page/index.html" target="_blank">回到首页</a>
	
	
		<a href="http://lol.qq.com">英雄联盟官网</a><br />
		<a href="index.html">跳去首页</a>
		
		<!--
			邮箱链接
		-->
		<a href="mailto:6731910143@qq.com">发送邮件给自己</a>
		<!--
			打电话
		-->
		<a href="tel:13713883527">一键拨号</a>
		<!--
			
		SMS
		
		-->
		<a href="sms:13713883527">发短信</a>
		<!--
			带连接的图片
		-->
		
		<a href="http://www.baidu.com">
			<img src="img/StartupWp.jpg" alt="百度" width="100" height="100"/>
		</a>

```

###锚点
>锚点的应用


```
	<a href="#hash_name">起点</a>
	<a name="hash_name">终点</a>
```
>只要保证锚点名字一致，他们就是cp(可以雌雄同体)



```
<a href="#hash_name" name="hash_name2">起点</a>
<a name="hash_name" href="#hash_name2">终点</a>
```

###a标签格式
>ps:浏览器会自动下载不能识别的文件格式,但不是所有的浏览器都可以


``` 
<a href="a.zip"></a>
```

###拓展
锚点的升级版：`element.scrollIntoView()`：[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/scrollIntoView)
