###视口(viewport)

|viewport|描述|
| :---: | :---: |
|视觉视口|设备的物理可视区域|
|布局视口|默认980px宽度用于布局的视口|
|完美视口|与设备大小一致的布局视口|

	
```
	一般做移动端设置
	<meta name="viewport" content="width=device-width,
	initial-scale=1,minimum-scale=1,maximum-scale=1,user-scalable=no"/>
	即可。
```

> 为什么iphone6的布局视口是375px而设计图是750px?

```
 	因为iphone的屏幕是Retina屏(视网膜屏),
 	即所说的2k屏/3k屏等（其原理是用2个/3个像素去显示一个像素，使得屏幕更为细腻。）,
 	如果用375px作为设计图的话，图片会变得模糊，所以设计图是750px。
```