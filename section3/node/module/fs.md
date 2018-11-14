#fs-文件系统
>fs 模块提供了一些接口用于以一种类似标准 POSIX(可移植操作系统接口（Portable Operating System Interface of UNIX，缩写为 POSIX ）) 函数的方式与文件系统进行交互。

###属性和方法

`fs.readdir(path, callback)`:
#####异步读取目录的内容。 回调有两个参数 (err, files)，其中 files 是目录中文件名的数组，不包含 '.' 和 '..'。

`fs.readdirSync(path)`:
#####异步读取目录的内容，返回目录中文件名的数组。

`fs.rename(oldPath, newPath, callback)`:
#####异步修改文件名。 回调有一个参数 (err)，oldPath， newPath 可以相对路径或绝对路径。
#####`fs.rename`不只修改文件名，也能复制移动文件，触发了`fs.rename`，可改变`fs.watch()`的事件类型参数。
#####`fs.rename`与`fs.writeFile`不同，不能像`fs.writeFile`重写文件内容，但`fs.writeFile`也能做到`fs.rename`做到的事。


######利用`fs.readdir()`和`fs.rename()`把名字包含'-'的图片替换成'_':

```
const fs = require('fs');
const src = './icons';

fs.readdir(src, function(err, files) {
	if (err) {
		console.log(err);
	}
	files.forEach(function(file) {
		if (/_/.test(file)) {
			let oldPath = src + '/' + file,
				newPath = src + '/' + file.replace(/_/g, '-');
				console.log('newPath', newPath);
			fs.rename(oldPath, newPath, function(err) {
				if (!err) {
					console.log('done!');
				} else {
					console.log(err);
				}
			});
		}
	});
});
```

`fs.writeFile(file, data, callback)`:
#####异步地写入数据到文件，如果文件已经存在，则覆盖文件。 data 可以是字符串或 buffer。callback参数err，file参数可以是路径可以是字符串。

`fs.readFile(path, callback)`:
#####异步读取文件，callback有两个参数(err, data), data是Buffer类型，调用`toString()`即可变成字符串。

######利用`fs.readFile()`和`fs.writeFile()`修改文件内容：
```
    // 修改index.html文件内容
    const fs = require('fs');
    const path = require('path');
    fs.readFile(path.resolve(__dirname, 'index.html'), (err, html) => {
        if (err) {
            console.log(err);
        }
        let tpml = html.toString();
        fs.writeFile('second.html', tpml, err => {
            if (err) {
                console.log(err);
            }

            console.log('文件已经保存');
        });
    });
```

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

`fs.mkdir(path, callback)`:
#####异步地创建目录，callback有一个参数error，但是不能一次生成多层文件夹，需要多次叠加调用。

`fs.mkdirSync(path, callback)`
#####同步地创建目录，callback有一个参数error，同样也不能一次生成多层文件夹，需要多次叠加调用。

######利用`fs.mkdirSync()`生成多层目录：
```
    let dir = './dir/subdir/father/son';

    const mkMutiDir = (dir) => {
        let fragments = '';
        dir.split('/').forEach((subdir, i) => {
            fragments += '/' + subdir;
            if (i === 0) {
                fragments = fragments.slice(1);
                return;
            }
            console.log(fragments);
            fs.mkdirSync(fragments, err => {
                if (err) throw err;
            });
        });

        console.log('finished', fragments);
    };

    mkMutiDir(dir);
```

`fs.watch(filname, callback)`
#####监视 filename 的变化，filename 可以是一个文件或一个目录。监听器回调（callback）有两个参数 (eventType, filename)。 eventType 可能是 'rename' 或 'change'，filename 是触发事件的文件的名称。在大多数平台，当目录中一个文件出现或消失时，就会触发 'rename' 事件。fs.watch 的接口不是 100％ 跨平台一致的，且在某些情况下不可用。
