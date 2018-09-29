#未定义类型(undefined)

> 用于区分空对象和未定义对象

> 定义了undefined的变量，意味着已经为变量分配好内存，但里面没有存储东西。

> 所有未赋值的变量默认值都是undefined。

###注意

`null == undefined //true`但 是， `null === undefined //false`


###拓展

#####1.大多是开发者倾向于将`undefined`(未定义)等同于`undeclared`(未声明),但在Javascript中事两码事
```
	var a;
	
	a; // undefined
	b; // ReferenceError: b is not defined
```

>#####这里浏览器其实提示的并不准确，因为b并没有声明，应该使用undeclared比较好。


#####2.`undefined`和`null`不同，undefined是一个标识符可以当做变量赋值和使用
```
	function foo() {
		undefined = 2 // 这是非常糟糕！
	}
	
	foo();
	
	function foo() {
		'use strict';
		undefined = 2; // TypeError!
	}
	
	foo();
```
>#####建议不要这样做，这在设计上欠考虑。

#####3.`void`运算符
>##### 是`void`后的变量或者数面量为undefined。

```
	var a = 42;
	console.log(void a, a); // undefined 42
```
