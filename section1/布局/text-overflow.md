#text-overflow

>控制内容溢出的样式


###属性值
|clip|当内联内容溢出块容器时，将溢出部分裁剪掉。|
|ellipsis|当内联内容溢出块容器时，将溢出部分替换为(...)。|


但是text-overflow只是用来说明文字溢出时用什么方式显示，
要实现溢出时产生省略号的效果，还须定义强制文本在一行内显示（white-space:nowrap）
及溢出内容为隐藏（overflow:hidden），只有这样才能实现溢出文本显示省略号的效果。


###单行文字溢出
```
	.div3{
			/*单行文字溢出处理*/
		.div1{
				width: 50px;
				background: skyblue;
				/*1禁用换行*/white-space: nowrap;
				/*2超出部分隐藏*/	overflow: hidden;
				/*3 出现省略号1*/	text-overflow: ellipsis;
			}
```

###多行文本溢出
```
	.div2{
				font-size: 16px;
				width: 50px;
				height: 87px;/*多行省略的时候，要注意该高度，最好是等于最大行数乘以行高*/
				background: skyblue;
				overflow: hidden;/*超出内容隐藏*/
				text-overflow: ellipsis;/*设置出现省略号*/
				display: -webkit-box;/*设置为弹性伸缩盒子*/
				-webkit-line-clamp: 4;/*设置内容出现最大行数*/
				-webkit-box-orient: vertical;/*设置排版方向从上到下*/
			}
```


###字母和数字溢出

```
	.div3{
				margin-top: 100px;
				width: 500px;
				background: skyblue;
				white-space: normal;/*可以让中文和单词在遇到容器边界的时候后自动换行，
					数字和字母不符合这个规则
				* */
				word-break: break-all;/*所以这个时候就需要这个玩意出现了，控制非中文字符遇到边界的时候强制断行。*/
				white-space: nowrap;/*禁止所有内容*/
			}
```


