#Object

> 对象(键值对的集合)

###常用写法
```
	var obj = {};
	
	var obj = new Object();
```

###ES6的`Object.is(..)`
#####1.判断两个值是否绝对相等。
```
	var a = 2 / "foo";
	var b = -3 * 0;
	
	Object.is(a, NaN);      //true
	Object.is(b, -0);       //true
	
	Object.is(b, 0);        //false
	
```

#####2.polyfill Object.is(..)
```
	if (!Object.is) {
		Object.is = function(v1, v2) {
			// 判断是否是-0
			if (v1 === 0 && v2 === 0) {
				return 1 / v1 === 1 / v2;
			}
			
			// 判断是否是NaN
			if (v1 !== v1) {
				return v2 !== v2;
			}
			
			// 其他情况
			return v1 === v2;
		};
	}
```
>#####能使用`==`和`===`时，就尽量不要使用Object.is(..)，因为前者效率更高更为通用。

###注意
1. `function`和 `Array`都是对象(其实Object的一个子类型)。
2. 具体来说`function`是可调用对象，原因是内部有`[[Call]]`使其可以调用。
3. `function` 和 `Array`都有“length”属性，对于`function`来说是参数的数量，对于`Array`来说是数组元素的数量。


