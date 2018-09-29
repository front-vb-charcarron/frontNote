#class和id

###class
>- 通常称为类，可以给一个或者多个元素添加样式<br/>
>- 与id不同,以.+class值来设置样式。<br/>
>- 类可以重复使用。<br/>
>- 一个标签拥有一个唯一的class.



```
	<style type="text/css">
				.colorBlue{
					color: skyblue;
				}
				
				.colorRed{
					color: red;
				}
				
				.backgroundBlack{
					background-color: black;
				}
			</style>
	<!-- 类的重用-->
	<div class="colorBlue backgroundBlack">测试div11</div>
	<a href="" class="colorRed">我的字体颜色是红色</a>
```


###id
>- 以#+id值来设置样式。
>- 一个页面只能有一个id值。




```
		<style>
			#div3{
					color: green;
				}
		<style>	
		
		<div id="div3">
			我是一个id为div3,唯一名字的一个div
		</div>
```

###class、id和元素选择器的**优先级**

```
	id>class>元素选择器>*
```