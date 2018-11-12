#http-协议
>要使用 HTTP 服务器与客户端，需要 require('http')。

###nodejs搭建简单的web服务器

```
    // get、post都能请求
    const http = require('http');
    
    http.createServer((req, res) => {
        res.writeHead(200, {'ContentType': 'text/plain'});
        res.end('HelloWorld\n');
    }).listen(3000);

    console.log('Server running at http://localhost:3000/');
```