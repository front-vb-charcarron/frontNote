#switch语句

```
		//switch判断 
			switch(true){
				case (num < 1):
				//case 后面可以跟着数值，比较运算后的结果(布尔值)
					alert(1);
					//完成了分支内的代码后，直接跳出switch
					break;
				case 'name':
					alert(2);
					break;
				default:
					//默认，如果前面分支没有break跳出来也会运行
					alert("以上情况都不符合");
			}
```

> 值得注意的是，运行switch时，比较的是switch()括号里面的boolean值和case的boolean值是否相等，不等则运行default.

> switch同样也可以嵌套。