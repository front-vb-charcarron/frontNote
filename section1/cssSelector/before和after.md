#before和after

>每个对象天生都带有的两个元素<br/>
>::after, ::before 具有行内元素属性<br/>
>**::before, ::after 前面目标元素不写是默认为html**


```
		
	<style>
		div::before{
			content: '{';
			color: deeppink;
		}
		
		div::after{
			content: "}";
			color: skyblue;
		}
	</style>
		
	<div>测试</div>
```