#:selection

>设置对象被选中时的样式<br/>


> **::selection只能修改text-shadow,background-color,color**<br/>

> 兼容性 IE11不支持::selection


```
	<style>	
		p::selection{
			color: deeppink;
		}
	</style>
	
	<p>我是第一个p标签,<br/>我是第一个p标签的第二行。</p>	
```
