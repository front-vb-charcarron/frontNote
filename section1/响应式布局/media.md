#媒体查询
>在不同尺寸设备宽度下，应用不同的样式。

###两种写法

```
	<link rel="stylesheet" href="css/index768.css" media="screen and (max-width:768px)"/>
	<link rel="stylesheet" href="css/index991.css" media="screen and (min-width:768px) 
	and (max-width:991px)"/>
```

```
	
	@media screen and (min-width:1200px){
	    .son{
	        width: 25%;
	    }
	    
	}
```


###不同屏幕下的阀值

```
	超小屏幕  < 768px
	小型屏幕  768px < x < 992px
	中型屏幕 992px < x < 1200px
	大型屏幕 1200px < x 
```