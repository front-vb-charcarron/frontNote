#process-进程
> `process`对象是一个全局变量，它提供当前Node.js进程的有关信息，以及控制当前Node.js进程。因为是全局变量，所以不需要`require()`。

###属性和方法

`process.cwd()`: 
#####是当前执行node命令时候的文件夹地址 ——工作目录。

`process.env`: 
#####返回一个包含用户环境信息的对象。
#####可以修改这个对象：

```
    // 在命令行输入
    node -e 'process.env.foo = "bar"' // 但不会生效

    // 下面这种方法会生效
    process.env.foo = 'bar';
```

#####在process.env新增属性会转换成字符串。

```
    process.env.test = null;
    console.log(process.env.test);
    // => 'null'
    process.env.test = undefined;
    console.log(process.env.test);
    // => 'undefined'
```
#####用`delete`删除process.env的属性

```
    process.env.TEST = 1;
    delete process.env.TEST;
    console.log(process.env.TEST);
```

#####在window系统下，环境变量是不区分大小写的。

```
    process.env.TEST = 1;
    console.log(process.env.test);
    // => 1
```

#####在vue-cli可以使用process.env来切换开发环境api和测试环境api。
