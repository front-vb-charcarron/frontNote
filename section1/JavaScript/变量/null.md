#空对象(null)
> 表示该变量已经从内存中移除，不存在该变量。
> 常常用于切断变量是对象的引用。

```
	var obj = new Object();
	obj = null;
```

###undefined和null具体的区分
	
|类型|描述|
| :---: | :---: |
|undefined|指没有值，即从未赋值。|
|null|指空值，曾经赋过值但目前没有值|


###注意
1， `null == undefined //true`
2. 唯一一个用`typeof null === "object" // true`的基本类型。
3. 如果意在变量为对象的时候，可以用null初始变量。