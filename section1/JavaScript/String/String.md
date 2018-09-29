#String

> 特殊的引用类型，也称基本包装类型。


###为什么string是基本类型却可以像对象一样调用方法?

```
	var s1 = 'some text';
	var s2 = s1.substring(2);
	
	//当代码执行到第二行的时候,后台会执行以下操作
	var s1 = new String('some text');
	var s2 = s1.substring(2);
	s1 = null;
```


