#form标签
>包裹在table、input标签外层的标签，像提交问卷调查一样提交信息到后台。


###属性
- action

>提交方式

|属性名|描述|
| :---: | :---: |
|method|get|
|method|post|


###get特点


- 在url上拼接form表单里的数据，以？隔开,以&符号拼接不同的数据


###post特点


- 在url没有任何的表单信息，并且需要用服务器接收数据


###get和post区别


- get数据是裸露的，安全性较低 数据量小的
- post 数据相对隐秘，数据量大的

>所以一般传输图片、视频文件都是用post方式。

###拓展

1. 当 POST 请求是通过除 HTML 表单之外的方式发送时, 例如使用 XMLHttpRequest, 那么请求主体可以是任何类型.
2. enctype


	- 当 method 属性值为 post 时, enctype 是提交form给服务器的内容的 MIME 类型(媒体类型) 。可能的取值有:
	- application/x-www-form-urlencoded: 如果属性未指定时的默认值。
	- multipart/form-data: 这个值用于一个 type 属性设置为 "file" 的 <input> 元素。
	- text/plain (HTML5)
	- 这个值可以被 <button> 或者 <input> 元素中的 formenctype 属性重载（覆盖）。
	

>formenctype HTML5
>- 如果button是submit类型，此属性值指定提交表单到服务器的内容类型。可选值：
>- application/x-www-form-urlencoded: 未指定时的默认值。
>- multipart/form-data: 如果使用input标签type属性设置文件，使用此值。
>- text/plain
>- 如果指定此属性，它将重写button的表单拥有者的enctype属性。


3. 可通过打开chrome的Network来查看form提交的情况
	- 200 表示成功完成请求和响应。
	- 300表示请求和响应的过程中出现第三者...
	- 400表示文件丢失。
	- 500表示请求成功但是服务器没有响应。
