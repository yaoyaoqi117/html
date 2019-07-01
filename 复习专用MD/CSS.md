# 一、css选择器

## *1基础选择器

​		id、class、html标签选择器

## *2、8种高级选择器

​		通配符 *

​		后代选择器  div p

​		交集选择器  span.s1     **标签名叫span 且class都叫做d1**

​		并集选择器  div，p

​		子元素选择器  div>p

​		序列选择器  ul li:first-child    ul li:last-child

​		相邻兄弟选择器	h3 + p

​		普通兄弟选择器	div~p

# 二、css定位

## 相对定位、绝对定位、固定定位

 position：relative；相对定位

​		元素会根据自己原来的位置位移，并且不会脱离标准文档流。

​		作用：

​			1.微调元素位置

​			2作为**绝对定位**参考点

### position：absolute； 绝对定位

​		绝对定位元素会**脱离标准文档流**

​		**tip**：子绝父相、子绝父绝   一般情况下使用**子绝父相**

###  position:fixed ; 固定定位

​		 固定定位针对的是浏览器窗口，以浏览器窗口为参考进行位移。常见的功能，例如**返回顶部，**广告....

### position：sticky粘性定位

粘性定位是相对定位和固定定位的结合体，当元素处于屏幕范围之内，元素的定位就相当于是相对定位，而元素一旦脱离了屏幕范围那么元素的定位属性就会类似于固定定位





# 三、 z-index 层级关系

​		分两种情况：
  	 		 1 如果单纯的比较两个发生位置冲突的标签，**那么谁的z-index值大，谁就在上面**
   			 2 如果发生位置冲突的是两个子元素，那么最应该看的是父元素的层级关系，父元素的					层级也就是z-index值小，那么子级层级再高也没有办法改变。

​			3. 两个父元素比较层级的时候，如果其中一个父元素的层级z-index没有设置，那么子级是可以通过z-index盖过与之发生冲突的另外一个元素。

# 四、背景图片

1. background-color 背景颜色
  red  #ccc  rgb(23,23,23)
  我们在练习的时候用什么方式表达颜色都无所谓，但是实际开发的时候最好全部使用十六进制。

2. background-image 背景图片  

background-image:url("图片的地址")

3. background-repeat 背景图像是否重复
  值: repeat-x 横轴重复
      repeat-y 纵轴重复 
      no-repeat 不重复

4. ## background-position 图片位置

  **background-position:向右偏移量px 向下偏移量px; 偏移量可以为正也可以为负** 
  ****雪碧图  又称为css精灵****


5. ****background-attachment: fixed; 背景固定 
  **一旦设置了这个属性，那么网页的背景就不会随着网页的滚动而滚动。**

简写:
  background:url() no-repeat center top;

Tip:能使用简写的时候尽可能的使用简写。

# 五、文本属性

1. direction  设置文本方向
    值ltr  rtl  

2. letter-spacing 设置字符间距
  可以为负值 
  单位可以使用px

3. **text-align:center / left(默认) /right(右边) / justify(文本两边居中)**

4. text-decoration 给文本添加修饰
  none  取消文本的默认样式。 
  underline 加上一条下滑线
  overline 上划线
  line-through 穿过文本的一条线 


5. text-indent 缩进元素文本的首行

6. text-transform控制元素当中的字母 
  none (默认)/
  capitalize(文本中的每个单词以大写字母开头。) 
  uppercase（定义仅有大写字母） 
  lowercase(小写字母) 

# 六、 自适应网页效果

​		网页布局中经常要定义元素的宽和高。但很多时候我们希望元素的大小能够根据窗口或子元素自动调整，这就是自适应。
自适应的优点：
		元素自适应在网页布局中非常重要，它能够使网页显示更灵活，可以适应在不同设备、不同窗口和不同分辨率下显示。

​		**1）宽度自适应**
   **元素宽度设置为100%。（块元素宽度默认为100%）**
    **或者不设置宽度（width）;（宽度是父元素的宽度）**
（**2）高度自适应**
        1)自适应元素高度：height:auto;或者不设置;（是子元素撑开父元素的高度） (父元素高度跟随子元素的变化而变化)

​	2)元素高度自适应窗口高度(子元素的高度跟随父元素的变化而变化) -- 开发app页面使用次数较多
    
设置方法：html,body{height:100%;}
         

```html
    <style>
        html,body{height:100%;}
        div {background:red;height:100%;}
    </style>

    <body>
       <div></div>
    </body>
```
   Tip：全屏页面才推荐使用高度100%的方式去开发。
       
注：如果设置子元素的高度跟随父元素的高度变化而变化，那么父元素必须有高度

（3）元素具备最小高度的自适应

  min-height属性：最小高度；(IE6浏览器不识别该属性)
hack1:min-height:value;_height:value;
hack2:min-height:value;  height:auto!important;height:value;

max-width: 最大宽度
max-height: 最大高度

（4）浮动元素父元素高度自适应（高度塌陷）
    当子元素有浮动并且父元素没有高度或者加最小高度（min-height:）的情况下父元素会出现高度塌陷
    hack1：给父元素添加声明overflow:hidden;(触发一个BFC[Block Formatting Context块级格式化上下文],在bfc当中，
    浮动元素也会参与计算。)。
        弊端：会隐藏一些定位在内容区域外侧的元素。
            
    hack2:在浮动元素下方添加空div,并给该元素添加
            声明：div{clear:both; height:0; overflow:hidden;}
                  这种声明方式在写网页的时候，可以有效的兼容ie6，ie6即是高度没有，也会保留大概6px的高度
                  只有height:0;和overflow:hidden;搭配使用才可以解决这样的问题。
            弊端：增加代码的冗余，大量存在一些不必要的元素。
    hack3:万能清除浮动法
    选择符:after{content:"";clear:both;display:block;height:0;overflow:hidden;visibility:hidden;}
            也可以加上 .clearfix{*zoom:1;} 解决ie的问题
Tip:
    *visibility:hidden/隐藏

    *visibility:hidden;和display:none;的区别：
    visibility:hidden;属性会使对象不可见，但该对象在网页所占的空间没有改变，等于留出了一块空白区域，而 display:none属性会使这个对象彻底消失不显示，也不再占用位置。

**Tip：**
    **总结：**
        **开发时，通栏宽度依旧保持100%。**
        **测量版心的宽度**
        **元素包含块设置最小高度**

# 七、input  type类型

text 文本  ；  password  密码； file   文件上传； radio  单选；Checkbox  多选；

hidden 隐藏； button 按钮； image 图片形式的提交按钮；reset 重置； submit 提交按钮；

color 调色板； tel电话号码输入域；email 邮箱；URL 网址输入框；search 搜索域；number 数值输入框；range数值滑动输入框；date 选取日月年输入框；month选取月年输入框；week周年输入框；

time月年输入框；datetime定义选取时间、日月、年的输入域（UTC时间）

datetime-local 定义选取时间、日月、年的输入域（本地时间）





## select   、option    下拉列表

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>下拉列表</title>
</head>
<body>
	<select name="yunhuo" id="">
		<option value="">1</option>
		<option value="">1</option>
		<option value="" selected>2</option>
		<option value="">1</option>
		<option value="">1</option>
	</select>
</body>
</html>
```



# 八、过渡效果

## transition 过渡效果

兼容：IE10以上 谷歌火狐 欧朋 Safari都兼容

相关属性：

​		transition 简写属性

​		transition-property  规定用于参与css过渡的具体属性用，（**逗号**）隔开，1：设置具体的属性 ，如果在本条属性中设置某个属性参与过渡 那么没写的属性就具有过渡效果。      2：如果没有设置具体的属性值，那么都会参与过渡效果，想让所有的属性参与过渡效果可设置为：all;   如果不想参与过渡还要写本条命令  可设置属性值为：none； 

语法：

​	**transition-property 设置具体属性**

​	**all 全部属性参与过渡**

​	**none 都不参与过渡**

​	**property 具体属性值  每个值用逗号隔开**

## transition-timing-fanction  规定过渡效果的时间曲线 默认ease

​	属性值

​		1、cubic-bezier   后面设置的是具体的贝塞尔曲线值{  cubic-bezier：(0,0,1,1); }

​		2、linear   匀速

​		3、ease  规定从慢开始 自然加快 最后慢结束

​		4、ease-in 慢到快   加速

​		5、ease-out  快到慢 减速

​		6、ease-in-out 规定 慢开始  慢结束

## transition-delay  延迟

单位s/ms

在指定时间之后再来执行变化效果

transition：property  duration  timing-function delay;

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p {
            width: 100px;
            height: 100px;
            background-color: lightpink;
            transition:1s width 2s,2s height ,3s background-color;
        }
        p:hover {
            width: 300px;
            height: 300px;
            background-color: red;
        }
    </style>
</head>
<body>
    <p>
    </p>
</body>
</html>
```

transition:1s width 2s,2s height ,3s background-color;       过渡执行时间1S 、  属性、 延迟时间2S

### 过渡效果展示

手风琴

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>手风琴</title>
    <style>
        body {
            margin:0;
            padding:0;
            background-color: #f7f7f7;
        }
        h3 {
            margin:0;
            padding:0;
        }
        .box {
            width: 500px;
            margin:0 auto;
        }
        .list h3 {
            height: 35px;
            line-height:35px;
            padding-left: 30px;
            border-bottom:2px solid #690;
            font-size:14px;
            color: #fff;
            background-color: #369;
            transition: all 0.3s ease 0s;
        }
        .list .pictxt {
            height: 0;
            background-color: lightblue;
            transition: all 0.3s ease 0s;
        }
        .list:hover  h3 {
            background-color: #036;
        }
        .list:hover .pictxt{
            height: 150px;
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="list">
            <h3>今日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>昨日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>前日新闻</h3>
            <div class="pictxt"></div>
        </div>
        <div class="list">
            <h3>去年新闻</h3>
            <div class="pictxt"></div>
        </div>
    </div>
</body>
</html>
```

**transition: all 0.3s ease 0s;        全部参与过渡   过渡时间  贝瑟尔曲线效果   延迟时间；**

#九、css3 2D



**相关属性**:

- transform : 2d/3d之间的转换
- transform-origin : 更改元素的基点  



相关属性值: *位移/旋转/缩放/倾斜*

- **translate(x,y)**   沿着x y 移动元素/ translateX(n)  translateY(n)    
- **scale(x,y)**  缩放  更改元素的宽度和高度 ,将宽度改为原来的x倍，高度改为原来的y倍 / scaleX(n) 更改宽度  scaleY(n)  更改高度
- **rotate(angle)**  旋转 
- **skew(x-angle,y-angle)**  定义2D 倾斜转换 沿着x轴和y轴  / skewX(angle) 沿着x轴转换  skewY(angle) 沿着y轴



**translate(x,y)**  x表示沿着x轴位移的距离， y 表示沿着y轴位移的距离

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        .box {
            width: 600px;
            height: 300px;
            border: 2px solid orange;
            margin: 0 auto;
        }
        .box .d1 {
            width: 100px;
            height: 100px;
            background-color: lightseagreen;
            margin:0 auto;
            transition: 2s;
        }
        .box:hover .d1 {
            transform: translate(100px,100px);
        }
    </style>
</head>
<body>
    <div class="box">
        <div class="d1"></div>
    </div>
</body>
</html>
```



**scale(x,y)**  x表示宽度的倍数  y表示高度的倍数 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>scale</title>
    <style>
        div {
            width: 200px;
            height: 200px;
            background-color: lightpink;
            transition: 2s;
        }
        div:hover {
            transform: scale(0.5,0.5);
        }
    </style>
</head>
<body>
    <div>
    </div>
</body>
</html>
```

**rotate(angle)**

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>rotate</title>
    <style>
        .d1 {
            width: 100px;
            height: 100px;
            background-color: deepskyblue;
            border-left: 2px solid lawngreen;
            border-right: 2px solid gold;
            border-top: 2px solid palevioletred;
            border-bottom: 2px solid royalblue;
            transition: 5s;
            border-radius: 50%;
        }
        .d1:hover {
            transform: rotate(1080deg);
        }
    </style>
</head>
<body>
    <div class="d1">指向谁谁乌龟-></div>
</body>
</html>
```

**skew(x-angle,y-angle)**  倾斜/斜切

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>skew</title>
    <style>
        .playhappy {
            width: 100px;
            height: 100px;
            background-color: aquamarine;
            margin:100px auto;
            /*transition: 2s;*/
        }
        .playhappy:hover {
            transform: skew(0deg,10deg);
        }
    </style>
</head>
<body>
    <div class="playhappy"></div>
</body>
</html>
```



## transform-origin : 更改元素的基点  

### 语法:

**transform-origin:(x轴值,y轴值)**

- x轴: left | center | right | length | % 
- y轴: top | center | bottom | length | %

示例:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>盘它</title>
    <style>
        img {
            width: 300px;
            height: 300px;
        }
        .anim_image {
            transition: all 1s ease-in-out;
            cursor: pointer;
        }
        .anim_image_top {
            position: absolute;
            transform: scale(0,0);
        }
        .anim_box:hover .anim_image_top {
            transform: scale(1,1);
            transform-origin: top right;
        }
        .anim_box:hover .anim_image_bottom {
            transform: scale(0,0);
            transform-origin: bottom left;
        }
    </style>
</head>
<body>
    <div class="anim_box">
        <img src="./images/photo3.jpg" class="anim_image anim_image_top">
        <img src="./images/photo4.jpg" class="anim_image anim_image_bottom">
    </div>
</body>
</html>
```

# 十、雪碧图

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>导航</title>
    <style>
        * {
            margin:0;
            padding:0;
        }
        ul {
            list-style:none;
            width: 1000px;
            height: 40px;
            line-height:40px;
            border:1px solid #ccc;
            margin:0 auto;
        }
        li {
            float: left;
            width: 99px;
            height: 40px;
            border-right:1px dashed #ccc;
        }
        a {
            display: block;
            width: 69px;
            height: 40px;
            text-decoration: none;
            color: #909090;
            font-size:14px;
            background:url('./images/360bg.png') no-repeat;
            padding-left: 30px;
            transition: all .5s linear 0s;
        }
        a:hover {
            color: #3faf0f;
        }
        .home a {
            background-position: 5px -55px;
        }
        .news a {
            background-position: 5px -131px;
        }
        .tv a {
            background-position: 5px -295px;
        }
       .home a:hover {
            background-position: 5px -93px;
        }
    </style>
</head>
<body>
    <ul>
        <li class="home"><a href="#">我的主页</a></li>
        <li class="news"><a href="#">新闻头条</a></li>
        <li class="tv"><a href="#">电视剧</a></li>
    </ul>
</body>
</html>
```



#十一、颜色和渐变

1. rbg、英文单词 、进制 rgba。

  不透明度:
  	rgba
  	opacity: 使用的时候会连字都变得透明

2. 颜色渐变 --- 应用在元素的背景上
  渐变分为两种：线性渐变 和 径向渐变

### linear-gradient() 线性渐变  

线性渐变的初始颜色变化默认是从上到下。而且，渐变必须设置在background的身上。background-image: linear-gradient;


	首先，线性渐变是支持多个颜色渐变的。
		background: linear-gradient(red,yellow,blue,pink);
	
	设置渐变方向：
		background: -webkit-linear-gradient(bottom,red,pink);
	如果在参数里直接设置方向，那么需要加浏览器前缀。
	如果在方向的前面加上to，那么就不需要加浏览器前缀。
		background: linear-gradient(to left,red,pink);
		to left 、 to right 、 to top 、to bottom ,没有to center
	当然，关于方向我们也可以组合来使用：
		to left top 或者top left bottom.....
		
	我们除了设置具体的方向值，还可以通过  angle 来设置角度。
	
		在代码中deg表示角度
			0deg表示从下向上
			如果角度为正，则为顺时针，如果角度为负，则为逆时针。
			
	渐变百分比
		background: linear-gradient(to left,red 10%,black 90%);
		方向：从右到左，
			表示从起始方向开始，从右向左的10%为纯红色，从10%到90%为红色向黑色的渐变色，剩下的
			为纯黑色。
			
		练习：
			红、绿、蓝、黄
			
			灰  绿 灰  绿  
			
	线性渐变在IE:
		filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffff',
		endColorstr='#ff0000',GradientType='1');   
	GradientType = 0 方向是从上向下  1为从左向右
	
	重复线性渐变
		一个渐变的过程已经完成，后续重复的进行这个过程。
		repeating-linear-gradient() ;
	
	## 颜色和渐变



1. rbg、英文单词 、进制 rgba。

  不透明度:
  	rgba
  	opacity: 使用的时候会连字都变得透明

2. 颜色渐变 --- 应用在元素的背景上
  渐变分为两种：线性渐变 和 径向渐变

linear-gradient() 线性渐变  

	Tip：线性渐变的初始颜色变化默认是从上到下。
		而且，渐变必须设置在background的身上。
		
		background-image: linear-gradient;


	首先，线性渐变是支持多个颜色渐变的。
		background: linear-gradient(red,yellow,blue,pink);
	
	设置渐变方向：
		background: -webkit-linear-gradient(bottom,red,pink);
	如果在参数里直接设置方向，那么需要加浏览器前缀。
	如果在方向的前面加上to，那么就不需要加浏览器前缀。
		background: linear-gradient(to left,red,pink);
		to left 、 to right 、 to top 、to bottom ,没有to center
	当然，关于方向我们也可以组合来使用：
		to left top 或者top left bottom.....
		
	我们除了设置具体的方向值，还可以通过  angle 来设置角度。
	
		在代码中deg表示角度
			0deg表示从下向上
			如果角度为正，则为顺时针，如果角度为负，则为逆时针。
			
	渐变百分比
		background: linear-gradient(to left,red 10%,black 90%);
		方向：从右到左，
			表示从起始方向开始，从右向左的10%为纯红色，从10%到90%为红色向黑色的渐变色，剩下的
			为纯黑色。
			
		练习：
			红、绿、蓝、黄
			
			灰  绿 灰  绿  
			
	线性渐变在IE:
		filter:progid:DXImageTransform.Microsoft.gradient(startColorstr='#ffffff',
		endColorstr='#ff0000',GradientType='1');   
	GradientType = 0 方向是从上向下  1为从左向右
	
	重复线性渐变
		一个渐变的过程已经完成，后续重复的进行这个过程。
		repeating-linear-gradient() ;

​	
​	

##radial-gradient:径向渐变

​	方向：
		left top right bottom ，前面要加webkit
		也可以设置具体的值：apx  bpx 
	还可以设置圆的形状：
		正圆:circle
		椭圆:ellipse
		
​		

# JS



