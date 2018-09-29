#font-size
>改变字体的大小。



###属性值

#####根据对象字号进行调节

**h1**`xx-large`

**h2**`x-large`

**h3**`large`

**h4**`medium`

**h5**`small`

**h6**`x-small`

**h7**`xx-small`


```
	p:nth-of-type(1){
			font-size: xx-large;
		}

		p:nth-of-type(2){
			font-size: x-large;
		}

		p:nth-of-type(3){
			font-size: large;
		}

		p:nth-of-type(4){
			font-size: medium;
		}

		p:nth-of-type(5){
			font-size: small;
		}

		p:nth-of-type(6){
			font-size: x-small;
		}

		p:nth-of-type(7){
			font-size: xx-small;
		}
		
		<p>标题h1</p>
		<p>标题h2</p>
		<p>标题h3</p>
		<p>标题h4</p>
		<p>标题h5</p>
		<p>标题h6</p>
		<p>标题h7</p>
		
		
```



#####相对于父对像中字号进行相对调节。

>使用成比例的em单位计算,一般浏览器默认字体16px,所以1em=16px。



#####用长度值指定文字大小。不允许负值。

>也就是px作单位


###用百分比指定文字大小。

>百分比基于其父元素的字体大小，且不为负值。<br/>

>建议最好不要设置小于12px的字体。