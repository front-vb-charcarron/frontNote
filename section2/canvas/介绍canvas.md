# canvas 
 > 中文意思：画布，是HTML5新增的元素。
 > 常用来画2d图像、做动画、也是前端游戏引擎的底层。
 

### 基本用法

```
	<!-- 在html 插入 -->

	<canvas id="canvas" width="100" height="100">
		<!-- 在此插入后备内容，例如： -->
		你的浏览器不支持canvas !
	</canvas>


```


### canvas 与 svg

	1.  canvas 和 svg 最主要的区别是，canvas使用的是位图(以像素构成的)，而svg使用的是矢量图(以坐标进行存储的)，
	位图和svg的区别，就是位图放大化会到像素点，即所谓的失真，而svg放大看不到像素的，依然跟放大前一样。

	2.  svg 比 canvas 出色的地方就是，svg可以通过dom来获取图片信息，而canvas没办法做到。

	3.  canvas比svg出色的地方，在绘制方面会比svg要快速，可处理视频和图像。


### canvas 的 js库

	1. three.js(canvas的三维图像是建立在一种叫WebGl的技术，three.js则是使用这项技术的js库)。

	2. Impact(canvas关于游戏的js库)。

	3. Easel(创建动画的辅助型js库)。