#html
> 超文本标记语言hypetext markup language

- 超文本,指文本、音频、视频、链接、图片等等的内容
- 标记语言，表示这门语言会有类似箭头标记的风格，指明每个内容的具体区域
- 并且它是一门语言，所以会有自己的语法


###head标签
>头部标签专门存放我们看不到的内容： 例如meta标签、标题title、样式的引入


###meta标签 
- 元素可提供有关页面的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词。
- 标签位于文档的头部，不包含任何内容。<meta> 标签的属性定义了与文档相关联的名称/值对


###body标签
>页面上可视元素的父元素

- 有自己的内边距和外边距
- 严格上来说body是一个块级元素

###base标签
>- base标签的作用,其实就指定了一个路径前缀，在该页面中出现的所有相对路径，都会自动凭接上这个一个路径前缀。
>- 设置了base标签后不需要出只需要进。

```
	<!DOCTYPE html>
	<html>
		<head>
			<meta charset="UTF-8">
			<title>base</title>
			<base href="/20170721HTML/" />
		</head>
		<body>
			<img src="img/map.jpg" alt="" />
		</body>
	</html>
```
