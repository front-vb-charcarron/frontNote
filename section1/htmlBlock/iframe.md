#iframe
>内嵌框架

|属性名|描述|
| :---: | :---: |
|frameborder|框架的宽度|
|scrolling|是否允许窗口内滚动|


>iframe可以搭配form表单,可以实现无刷新提交,做到类似ajax的效果,通过form标签的target属性和iframe标签的name属性结合



```
	<iframe src="http://tmall.com" width="100%" height="100%" frameborder="0" name="ifr"></iframe>
	<form action="reg.php" method="post" target="ifr">
				<input type="text" value=""/>
				<input type="submit" value="submit"/>
	</form>
```
