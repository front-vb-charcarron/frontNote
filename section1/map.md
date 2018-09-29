#map标签

>用来实现图片热区的标签。


```
	<img src="img/map.jpg" alt="" usemap="#hotmap"/>
		<map name="hotmap">
			<area shape="rect" coords="181,118,278,204" href="http://zhihu.com" alt="知乎" target="_blank"/>
			<area shape="circle" coords="372,181,7" href="http://csdn.net" alt="csdn程序员社区" />
			<area shape="poly" coords="638,276,633,173,526,208" href="http://sports.qq.com" alt="NBA" />
		</map>
```