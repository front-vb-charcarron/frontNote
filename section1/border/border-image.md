#border-image

>为边框添加图片。



|属性|值|描述|
| :---: | :---: | :---: |
|border-image-slice|number/percentage(不允许负值),fill(保留裁剪后的中间区域)，排铺遵循border-image-repeat|边框背景的裁剪方式|
|border-image-source||图片路径|
|border-image-width|浮点数、百分比、px/都不允许负值|边框背景的宽度|
|border-image-outset|px,浮点数/都不允许负值|边框背景的扩展|
|border-image-repeat|stretch(拉伸)、repeat(平铺超过会被截断)、round(平铺正好铺满)|边框背景的平铺方式|


###复合语法
`border-image:source slice width width outset repeat`
`border-image: url(img/border.png) 27 27 stretch;`
##注意
**border-width,不用添加px**

##border-image原理：
>九宫格  图片要求 ：长宽是3的倍数。<br/>

>border-width,是针对原图，然后进行拉伸或平铺等其他方式<br/>

>实际渲染根据边框宽度决定。
