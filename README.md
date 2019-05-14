## 前言

<img src="https://www.qqzmly.com/usr/uploads/2019/05/2169730022.jpg" alt="CSS盒子居中三种方法">

CSS盒子居中，我觉得是很有必要学习一下的。特别是第三种方法，奇淫技巧升级版，也是生产环境中非常常见的一种方法，不需要知道宽度，随着祖先元素的变化而变化！

## 1.常规方法

常规方法只需要给盒子设置宽高，利用外边距让它居中！

```html
<div class="box1">常规方法</div>
```

```CSS
.box1{
	width: 200px;
	height: 200px;
	margin: 0 auto;
	background-color: pink;
}
```

## 2.奇淫技巧

奇淫技巧利用定位元素。将祖先元素设为相对定位，子级元素设为绝对定位。left设置为50%；margin-left设置为-宽度的一半。但是**必须得设置宽度，并且得知道宽度值为多少！**

```HTML
<div class="bigbox2">
	<div class="box2">奇淫技巧</div>			
</div>
```

```CSS
.bigbox2{
	position: relative
}
.bigbox2 .box2{
	width: 200px;
	height: 200px;
	background-color: skyblue;
	position: absolute;
	left: 50%;
	margin-left: -100px;
}
```



## 3.奇淫技巧升级版

奇淫技巧利用定位元素和CSS transform属性。将祖先元素设为相对定位，子级元素设为绝对定位。left设置为50%；transform设置为translate(-50%);优点：**不需要知道宽度值为多少！**

```
<div class="bigbox3">
	<div class="box3">奇淫技巧升级版</div>			
</div>
```

```CSS
.bigbox3{
	position: relative;
}
.bigbox3 .box3{
	width: 200px;
	height: 200px;
	background-color: lightseagreen;
	position: absolute;
	left: 50%;
	transform: translate(-50%);
}
```

## 在线代码

GitHub：[**css-box-model-center**](<https://github.com/chengzhihui99/css-box-model-center>)