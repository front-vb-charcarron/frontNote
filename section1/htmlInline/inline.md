#行内元素
>- 行内元素只占本身大小,可以跟其他共处一行 但并不能设置宽高(除了这几位**替换元素**:img、audio、video、canvas)等<br/>	
>- ps:然而img、audio、video、canvas其实是行内块元素,只是w3c默认把行内块元素归为行内元素。


###常用的行内元素
- a
- span
- b
- i
- del
- sup
- sub
- em
- br
- strong
- mark


###关于行内元素布局的特点
```
	**当行内元素并排紧贴时,行内元素之间会有个缝隙**
	解决方案：给其父元素的font-size：0,若元素需要设置font-size 再在自行设置。
```

