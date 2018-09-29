#background-position

>设置背景图片的位置。


###属性
|值|描述|
| :---: | :---: |
|百分比|按百分比确定背景位置，可以负值。|
|px|按长度确定背景位置，可以为负值。|
|center|横向和纵向居中，|
|left|横向上从左开始填充。|
|right|横向上从右开始填充。|
|top|纵向上从上开始填充。|
|bottom|纵向上从下开始填充。|

###设置4个值的语法(css3提供)
>在长度和百分比前添加left right top bottom


```
		background:url(test1.jpg) no-repeat right 20px bottom 20px;
		//在容器右下方，并距离容器右边20px,距离容器底边20px
```



>ps:设置3个值的语法则(方向 方向 数值/百分比)
