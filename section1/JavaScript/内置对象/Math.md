#Math

#####常量

```
	Math.PI //圆周率
	Math.E //自然对数的底数e
	Math.SQRT2 //根号2	
```


#####数学方法

```
	Math.abs(-2); //绝对值
	Math.sin(Math.PI/2)  //正弦函数
	Math.cos(Math.PI/2)  //余弦函数
	Math.tan(Math.PI/2)  //正切函数	
	
```


#####取整

```
	Math.ceil(5.6); //取大整    天花板
		
	Math.floor(5.6); //取小整    地板
		
	Math.round(5.6); //四舍五入
```


#####取小数位

```
	var num = Math.PI;
	console.log(num.toFixed(2));//取几位小数
```


#####基本运算

```
	console.log(Math.max( 4, 5, 6, 7 ));//最大值
		
	var arr = [1,2,3,4,5];
	console.log(Math.max(...arr));
	var max = Math.max.apply(this,arr);
	console.log(max);	
		
	console.log(Math.min( 4, 5, 6, 7 ));//最小值
		
	console.log(Math.pow(3,3)); //求几次方
		
	console.log(Math.random()); //产生随机数
	
	//3的平方 + 4的平方，再开根 等于5
	console.log(Math.hypot(3,4)); //求平方和的根
	
	//Math.cbrt() 函数返回任意数字的立方根.
	
	//Math.trunc() 方法会将数字的小数部分去掉，只保留整数部分。
	//(与parseInt相似，不过parseInt也可以用在字符串上)
```



