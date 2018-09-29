#javascript设计模式

### 鸭子类型

> has -a 和 is -a的区别，不关注对象本身是什么，而是关注对象做什么(行为)。

```	
	var duck = {
		ducksinging:function(){
			console.log('嘎嘎嘎');
		}
	}
	
	var chicken = {
		ducksinging:function(){
			console.log('嘎嘎嘎');
		}
	}
	
	var choir = [];		//合唱团
	
	var joinChoir = function(animal){
		if(animal && typeof animal.ducksinging === 'function'){
			choir.push(animal);
			console.log('恭喜加入合唱团');
			console.log('合唱团已有成员数量：' + choir.length);
		}
	}
	
	joinChoir(duck);	// 恭喜加入合唱团
	
	joinChoir(chicken); // 恭喜加入合唱团
```

###多态

> 1. 向不同对象发送同一条信息会有不同的反馈。
> 2. javascript本身就是动态型语言，所以变量装不同类型的值，这本身就体现了多态。
> 3. 多态可以通过继承来实现。
> 4. 多态还可以通过条件分支来表现(if语句)。


```
	var makeSound = function(animal){
		animal.sound();
	}


	var Duck = function(){};
	
	Duck.prototype.sound = function(){
		console.log('嘎嘎嘎');
	}
	
	var Chicken = function(){};
	
	Chicken.prototype.sound = function(){
		console.log('咯咯咯');
	}
	
	
	makeSound(new Duck());
	makeSound(new Chicken());
```







###AOP

> 面向切面编程。
> 把与核心业务逻辑无关的功能抽离出来。

用函数实现AOP

```
	Function.prototype.before = function(beforefn){
		var self = this;
		return function(){
			beforefn.apply(this,arguments);
			return self.apply(this,arguments);
		}
	}

	Function.prototype.after = function(afterfn){
		var self = this;
		return function(){
			var ret = self.apply(this,arguments);	//调换了顺序
			afterfn.apply(this,arguments);
			return ret;
		}
	}

	var func = function(){
		console.log(2);
	}

	func = func.before(function(){
		console.log(1);
	}).after(function(){
		console.log(3)
	});

	func();
```







###装饰者模式

> 给对象动态增加职责

```
	var plane = function(){}
	
	plane.prototype.fire = function(){
	console.log('发射普通子弹')
	}
	
	var MissileDecorator = function(plane){
	this.plane = plane;
	}
	
	MissileDecorator.prototype.fire = function(){
	this.plane.fire();
	console.log('发射导弹')
	}
	
	var AtomDecorator = function(plane){
	this.plane = plane;
	}
	
	AtomDecorator.prototype.fire = function(){
	this.plane.fire();
	console.log('发射原子弹')
	}
	/*链式结构*/
	var plane = new plane();
	plane = new MissileDecorator(plane); //this.plane指向plane的实例
	plane = new AtomDecorator(plane);//this.plane指向MissilDecorator的实例
	
	plane.fire();
```


###AOP装饰函数

```
	Function.prototype.before = function(beforefn){
			var self = this;
			return function(){
				beforefn.apply(this,arguments);
				return  self.apply(this,arguments);
			}
		}

	document.getElementById = document.getElementById.before(function(){
		alert(1);
	});

	var btn = document.getElementById('button');
	console.log(btn);
```


###对象池

> 复用池中对象, 没有分配内存和创建堆中对象的开销, 没有释放内存和销毁堆中对象的开销, 进而减少垃圾收集器的负担, 避免内存抖动; 不必重复初始化对象状态

```
		// 通用对象池

		var objectPoolFactory = function(createObjFn){
			var objectPool = [];
			return{
				create:function(){
					var obj = objectPool.length == 0? createObjFn.apply(this,arguments):objectPool.shift();
					return obj;
				},
				recover:function(obj){
					objectPool.push(obj);
				}
			}
		}

		var iframeFactory =  objectPoolFactory(function(){
			var iframe = document.createElement('iframe');
			document.body.appendChild(iframe);

			iframe.onload = function(){
				iframe.onload = null;	//防止iframe重复加载的bug
				iframeFactory.recover(iframe) //iframe加载完成之后回收节点
			}

			return iframe;
		});

		var iframe1 = iframeFactory.create();
		iframe1.src = 'http://baidu.com';

		var iframe2 = iframeFactory.create();
		iframe2.src = 'http://QQ.com';

		setTimeout(function(){
			var iframe3 = iframeFactory.create();
			iframe3.src = 'http：//163.com';
		},3000);
```

