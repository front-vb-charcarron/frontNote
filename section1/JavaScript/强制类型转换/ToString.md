#ToString

>#####ES5规范9.8节定义的抽象操作ToString，它负责处理非字符串到字符串的强制类型转换。


###基本类型值的字符串化规则：
#####1. `null` 转换为  `"null"`
#####2. `undefined` 转换为  `"undefined"`
#####3. `true` 转换为  `true`
#####4. 数字的字符串化遵循通用规则，但是极大和极小的数字则会用指数形式：
```
	// 1.07 连续乘以七个 1000 
	var a = 1.07 * 1000 * 1000 * 1000 * 1000 * 1000 * 1000 * 1000;
	
	// 七个1000一共21位数字
	a.toString(); // "1.07e21"
```
###对象的字符串化规则：
#####5. 对于普通对象，除非自行定义，否则`toString()`(Object.prototype.toString())返回内部属性[[Class]]的值, 如"[object Object]"。__(对象强制类型转换为string是通过ToPrimitive)__
#####6. 数组的`toString()`，方法经过重新定义，将所有单元字符串化以后再使用','连接起来：
```
	var a = [1,2,3];
	
	a.toString(); // "1,2,3"
```

>#####`toString()`可以被显示调用，或者在需要字符串化时自动调用。


###JSON字符串化
#####1.工具函数`JSON.stringify(...)` 在将JSON对象序列化为字符串时，也用到了`ToString`。(但是JSON.stringify也并未非严格意义上的强制类型转换。)
#####2.JSON字符串化和`toString()`效果基本相同，只不过序列化的结果总是字符串：
```
	JSON.stringify(42);   // "42"
	JSON.stringify("42"); // ""42""(含有双引号的字符串)
	JSON.stringify(null); // "null"
	JSON.stringify(true); // "true"
```
#####3.JSON字符串化不能序列化不安全的JSON值(undefined、function、 symbol和对象的循环引用)：
```
	JSON.stringify(undefined); 					// undefined
	JSON.stringify(function() {});  			// undefined
	
	JSON.stringify(
		[1, undefined, function() {}, 4]		// "[1, null, null, 4]"
	);                              
	JSON.stringify(
		{ a: 2, b: function() {} }				// "{ "a": 2}"
	);
```


>#####在对象中遇到undefined、 function和symbol时会自动将其忽略，在数组中则会返回null，对包含循环引用的对象执行`JSON.stringify(...)`会报错。

#####4. 可以通过定义`toJSON(..)`返回安全JSON值，再进行字符串序列化。
```
	var o = {};
	
	var a = {
		b: 42,
		c: o,
		d: function() {}
	};
	
	// 在a中创建一个循环引用
	o.e = a;
	
	// 循环引用在这里会产生错误
	// JSON.stringify(a);
	
	// 自定义的JSON序列化
	a.toJSON = function() {
		// 序列化仅包含b
		return { b: this.b };
	};
	
	JSON.stringify(a); // "{"b": 42}"
```

#####5. `JSON.stringify(...)`不太为人所知但却非常有用的功能。

+ 可选参数`replacer`，它可以是数组或者函数，用来指定对象序列化过程中哪些属性应该被处理，哪些应该被排除，和`toJSON(...)`很像。
```
	var a = {
		b: 42,
		c: "42",
		d: [1,2,3]
	};
	
	JSON.stringify(a, ["b", "c"]);  	// "{"b":42, "c": 42}"
	
	JSON.stringify(a, function(k, v) {
		if (k !== c) return v;
	});
```

>##### 字符串化是递归的。


+ 可选参数`space`，用来指定输出的缩进格式， space为正整数时是指定每一级缩进的字符数，它还可以是字符串。
```
	var a = {
		b: 42,
		c: "42",
		d: [1,2,3]
	};
	
	JSON.stringify(a, null, 3); 
	
	/*
	 * {
		   "b": 42,
		   "c": "42",
		   "d": [
			  1,
			  2,
			  3
		   ]
		}
	 */
	
	JSON.stringify(a, null, "-----");
	
	/*
	 * {
		-----"b": 42,
		-----"c": "42",
		-----"d": [
		----------1,
		----------2,
		----------3
		-----]
		}
	 */
```