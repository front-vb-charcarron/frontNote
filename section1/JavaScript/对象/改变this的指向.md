#apply()

apply() 方法调用一个函数, 其具有一个指定的this值，以及作为一个数组（或类似数组的对象）提供的参数。

> 注意：call()方法的作用和 apply() 方法类似，只有一个区别，就是 call()方法接受的是若干个参数的列表，而apply()方法接受的是一个包含多个参数的数组。
语法Edit



###语法
`fun.apply(thisArg, [argsArray]);`




#call()
call() 方法调用一个函数, 其具有一个指定的this值和分别地提供的参数(参数的列表)。

> 注意：该方法的作用和 apply() 方法类似，只有一个区别，就是call()方法接受的是若干个参数的列表，而apply()方法接受的是一个包含多个参数的数组。


###语法


`fun.call(thisArg, arg1, arg2, ...)`




 
#bind()
bind()方法创建一个新的函数, 当被调用时，将其this关键字设置为提供的值，在调用新函数时，在任何提供之前提供一个给定的参数序列。

###语法
`fun.bind(thisArg[, arg1[, arg2[, ...]]])`

###用法
```
	 var bgg = {
	 	name:'bgg'
	 }

	 function fun(name,age){
	 	console.log(name,age);
	 	console.log(this)
	 }

	 fun();
	 fun.bind(bgg,'bgg',18)();
```



> bind 、 call 、 apply 之间最主要的区别是 bind会返回一个绑定函数，并不是立即执行,而call和apply是立即执行的。