#search()

> search基本包装类型的方法


> search(正则表达式/字符串),返回匹配首字符的索引



```
	var str1 = 'This is a String eie String string';
	var str12 = str1.search(/s/gi);
	var str13 = str1.search('String');
	console.log(str12);
	console.log(str13);
	console.log(str1.charAt(str12));
```
