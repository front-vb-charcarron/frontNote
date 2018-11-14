#net-网络
>net 模块提供了创建基于流的 TCP 或 IPC 服务器(net.createServer())和客户端(net.createConnection()) 的异步网络 API。

`net.createServer(callback)`：
#####创建一个新的TCP或IPC服务，callback有一个参数socket，可以在回调里面监听socket的一些事件。