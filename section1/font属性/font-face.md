#font-face


>要导入字体库，首先层叠样式表找个空白的地方



```
	@font-face {
			font-family:tb;
			src: url('font/iconfont.eot'),;
				url('font/iconfont.eot?#iefix') format('embedded-opentype'),;
				url('font/iconfont.woff') format('woff'),
				url('font/iconfont.ttf') format('truetype'),
				url('font/iconfont.svg') format('svg');
```


###然后就不要管上面了。


###正确的步骤

1. 导入字体的iconfont.css样式表。
2. 新建font文件夹复制粘贴以.eot,.svg,.ttf,.woff结尾的文件。
3. 修改iconfont.css里的font-face引入路径
4. 像这样`<i class="iconfont 图片名字"></i>`调用。


>ps:由于font-family是字体，所以可以使用改变字体的样式来改变font-family的图标。