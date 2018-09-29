#input标签
>- 接受来自用户的数据，以创建基于web的表单交互控制。
>- 因其type属性不同，所以是个多样化的标签。
>- ps:最多花样的标签,大概没有之一。


###input基本属性
|属性名|描述|
| :---: | :---: |
|type|定义input不同的类型。|
|name|定义input不同的名字,防止产生冲突|
|value|定义提交到后台的信息，一般会用字母或者数字来填写，但有些input类型的value定义不同，例如button,submit这样的按钮类型|
|id|标记input，可以与label联动|
|size|input的宽度|
|readonly|是否只读|
|maxlength|输入字符的最大长度|
|disable|是否禁用|
|placeholder|提示语|

>ps:只要不是用户输入的值都要给该控件设置一个默认值(value)


###type属性
|属性名|值|描述|
| :---: | :---: | :---: |
|type|text|输入普通的文本,例如username等。|
|type|password|输入密码,值会根据浏览器不同以圆点或星号显示。|
|type|submit|向后台提交表单，以按钮的形式显示。|
|type|radio|单选框，以圆点小框显示，常用来选择性别,可与label标签联动。|
|type|checkbox|多选框，也可与label标签联动。|
|type|number|限制只能输入数字的文本框。|
|type|file|上传文件的文本框,若要多重上传文件设置multiple。|
|type|search|定义搜索文本框,可与submit一起用。|
|type|image|定义图像作为按钮。|
|type|hidden|提交不需要用户参与和修改的数据。|

#####hidden类型
```
		<!--
			还是会按照正常的数据进行提交，只不过不需要用户的参与和修改而已
		-->
		<form action="">
			<input type="hidden" name="ip_address"  value="127.0.0.1" />
			<input type="submit" value="提交"/>
		</form>
```

>ps:- file类型的input在使用时，要在form标签里指定method为post并设置enctype属性为multipart/form-data，
>   - file类型的input还可以添加accept属性来限制上传文件的类型


```
	<input accept="image/gif, image/jpeg, audio/mp3"/>
```


###与label联动
>radio与label的联动


```
		<input type="radio" name="sex" id="man" value="" />
		<label for="man">男</label>
		<input type="radio" name="sex" id="women" value="" />
		<!--防止冲突 name属性-->
		<label for="women">女</label>
```

>checkbox与label联动



```
		<input type="checkbox" name="che" id="num1" value="" />
		<label for="num1">1</label>
		<input type="checkbox" name="che" id="num2" value="" />
		<label for="num2">2</label>
		<input type="checkbox" name="che" id="num3" value="" />
		<label for="num3">3</label>
```
