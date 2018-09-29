#font

>设置或检索对象中的文本特性。该属性是复合属性。<br/>
>包含了font-style,font-variant,font-weight,font-size,line-height,font-family6个属性<br/>
>由于这6个属性从远古时代就有了，所以不存在兼容性问题。<br/>
>**若设置了font属性，再单个设置6个属性，即使font属性缺少设置的属性，但也无效。**



###语法
```
	font: [font-style] [font-variant] [font-weight] [font-size] [line-height] [font-family];
	
	
```

#####注意
**只有font属性的缩写才要按照顺序。**

```
	<style>
		font:italic small-caps bold 50% /100px "微软雅黑","黑体","宋体";
	</style>
	
	<div class="test">测试字体bgg</div>
```