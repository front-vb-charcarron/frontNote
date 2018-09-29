#replace()

> String基本包装类型的方法


> replace(匹配的字符串,要替代的字符串) 替换 


> ps:replace是创建一个新的字符串,而非覆盖原本的字符串。


```
	var str1 = 'This is a String eie String string';
	var str7 = str1.replace('String','bluej');
			console.log(str1);
			console.log(str7);
	var str7 = str1.replace(/String/ig,'bluej');
			console.log(str7);
```