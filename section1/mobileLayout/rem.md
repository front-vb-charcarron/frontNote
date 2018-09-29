#rem

>rem 在html根的位置设置font-size，rem就是根据这个font-size来计算的相对单位。


###em 
>相对于父元素的相对单位。


#####em和rem的区别：开关与总闸。


###移动端的适配。
```
	通过js动态算出不同设配的独立视口的逻辑像素。
	
	//移动端头尾的固定
	document.body.style.height = window.innerHeight + 'px';
	//动态求Rem的大小
	function recalc() {
		var clientWidth = document.documentElement.clientWidth;
		if(!clientWidth) return;
		document.documentElement.style.fontSize = 40 * (clientWidth / 750) + 'px';
									//字体大小 = 	  1个rem单位表示多少像素 (设备的宽度  / 设计宽度)  
									
									// 设计字体大小/设计图大小 = 屏幕字体大小/屏幕的大小
	}
	//监听手机是否有横屏
	function initRecalc() {
		recalc();
		var resizeEvt = 'osrientationchange' in window ? 'orientationchange' : 'resize';
		if(!document.addEventListener) return;
		window.addEventListener(resizeEvt, recalc, false);
		document.addEventListener('DOMContentLoaded', recalc, false);
	}
	initRecalc();


```

###拓展
#####vw
```
	把屏幕宽度分成100份，1vw即是屏幕宽度的1%。与rem一样都是相对单位，但兼容性不够rem好。
```