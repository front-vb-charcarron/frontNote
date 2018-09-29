#select标签
>下拉框


|属性名|描述|
| :---: | :---: |
|name|说明|
|size|下拉列表框的显示行数|
|multiple|是否多选|
|disabled|是否禁用|
|selected|设置默认选中的值|


```		
		
		<select name="city">
			<optgroup label="广东省">
				<option value="广州">广州</option>
				<!--value 提交到后台-->
			</optgroup>
				<option value="深圳">深圳</option>
				<option value="佛山">佛山</option>
		</select>
```

>optgroup 可与label属性一起用。
>select的最后结果就是选中option的value
