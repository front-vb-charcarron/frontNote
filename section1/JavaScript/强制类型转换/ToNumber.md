#ToNumber

>#####ES5规范9.3节定义的抽象操作， 将非数字值当作数字来使用，比如数学运算。

###基本类型转换数字的规则：
#####1. `true`转为`1`，`false`转为`0`。
#####2. `undefined`转为`NaN`。
#####3. `null`转为`0`。
#####4.  对`string`的处理，尝试转为数字运算，如果不能计算则返回`NaN`。

>#####`ToNumber`对以0开头的十六进制数并不按十六进制处理(按十进制处理)。

###对象转数字的规则:
#####5. 对象(包括数组)会首相转换为相应的基本类型值，如果返回的是非数字类型则再遵循以上规则将其强制转为数字。为了强制转换为相应的基本类型值，抽象操作`ToPrimitive`(ES5规范9.1节)会首先(通过内部操作DefaultValue, ES5规范8.12.8节)检查该值是否有`valueOf()`方法。如果有并且返回基本类型，就使用该值进行强制类型转换。如果没有就使用`toString()`的返回值(如果存在)来进行强制类型转换。如果`valueOf()`和`toString()`均不返回基本类型值，会产生`TypeError`错误。例如：
```
	// 从ES5开始，使用Object.create(null)创建的对象[[Prototype]]属性为null,
	// 并且没有valueOf()和toString()方法，因此无法进行强制类型转换。
	
	var a = {
		valueOf: function() {
			return "42";
		}
	};
	
	var b = {
		toString: function() {
			return "42";
		}
	};
	
	var c = [4, 2];
	c.toString = function() {
		return this.join(""); // "42"
	};
	
	Number(a);       // 42
	Number(b);       // 42
	Number(c);       // 42
	Number("")       // 0
	Number([])       // 0
	Number(["abc"]); // NaN
```

