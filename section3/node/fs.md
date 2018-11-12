#fs-文件系统
>fs 模块提供了一些接口用于以一种类似标准 POSIX(可移植操作系统接口（Portable Operating System Interface of UNIX，缩写为 POSIX ）) 函数的方式与文件系统进行交互。

###属性和方法

`fs.readdir(path, callback)`:
#####异步读取目录的内容。 回调有两个参数 (err, files)，其中 files 是目录中文件名的数组，不包含 '.' 和 '..'。

`fs.readdirSync(path)`:
#####异步读取目录的内容，返回目录中文件名的数组。

`fs.rename(oldPath, newPath, callback)`:
#####异步修改文件名。 回调有一个参数 (err)，oldPath, newPath 可以相对路径或绝对路径。

`fs.createReadStream(path)`:
#####读取流数据。

```
// 流数据

const fs = require('fs');

// 可以读取json的内容
let stream = fs.createReadStream('./package.json');
    stream.on('data', chunk => {
        console.log('finished chunk:' + chunk);
    });

// 可以读取js的内容    
let otherStream = fs.createReadStream('./helloWorld.js');
    otherStream.on('data', chunk => {
        console.log('other chunk:' + chunk);
    });
```

###如何把一张图片流到客户端：

```
    const http = require('http');
    const fs = require('fs');

    http.createServer((req, res) => {
        res.writeHead(200, {'Content-Type': 'image/png'});
        fs.createReadStream('./node.png').pipe(res); // 设置一个从读取流到写出流的管道
    }).listen(3000,'127.0.0.1');

    console.log('Server running at http://localhost:3000/');
```