# jquery

## 入口函数

````javascript
$(function () {
		

	})
````



## jQuery解决$冲突

在入口函数前写上 **jQuery.onConflict ();**注意以后的$要写成**jQuery**

自定义

 **yyq = jQuery.onConflict ();**

## 什么是jquery对象

jQuery对象就是一个伪数组

什么是伪数组？  有0--length-1的属性 并有length属性

## 静态方法     实例方法

**静态方法** ：直接添加给类的就是静态方法       静态方法通过类名调用

````javascript
//定义一个类
		function Aclass() {
			
		}
		//添加静态方法
		Aclass.staticMethod = function () {
			alert('staticMethod 意思是静态方法');
		}
		//通过类名调用
		Aclass.staticMethod();
````



**实例方法**：给这个类添加一个实例方法   创建一个实例（创建一个对象）   通过类的实例调用      

````javascript
//定义一个类
		function Aclass() {
			
		}
		//添加实例方法
		Aclass.prototype.instanceMethod = function () {
			alert('instanceMethod 意思是实例方法');
		}
		//创建一个实例（创建一个对象）
		var a = new Aclass();
		//通过这个实例方法调用
		a.instanceMethod();
````

##jQuery.each方法

**原生JS的foreach方法**  只能遍历数组  不能遍历伪数组        



````javascript
var arr = [1,3,5,7,9];
	//第一个参数是遍历到的元素
	//第二个参数是遍历到的索引
	arr.forEach(function (value,index) {
		console.log(index,value);
	});
````

**jQuery中的each方法**    既能遍历数组  又能遍历伪数组

````javascript
var obj = {0:1,1:3,2:4,3:5,4:7, length:5};
	//第一个参数是遍历到的索引
	//第二个参数是遍历到的元素
	$.each(obj,function (index,value) {
		console.log(index,value);
	});
````

## jQuery.map方法

原生JS的map方法

````javascript
var arr = [1,3,5,7,9];
	//第一个参数是遍历到的元素
	//第二个参数是遍历到的索引
	//第三个参数代表的是遍历的哪个数组
	arr.map(function (index,value,array) {
		console.log(index,value,array);
	})
````

jQuery中的map方法

````javascript
var obj = {0:1,1:3,2:4,3:5,4:7, length:5};
	//map中的参数
	//第一个是要遍历的数组/伪数组
	//第二个是没遍历一个数组之后执行毁掉函数
	//函数中的参数
	//第一个参数是遍历到的元素
	//第二个参数是遍历到的索引
	$.map(obj,function (value,index) {
		console.log(value,index);
	})
````

## jQuery中的each静态方法和map静态方法的相同点和不同点

**相同点**

都能遍历数组跟伪数组

**区别**

1、each静态方法默认返回值是，遍历谁就返回谁

map中的静态方法迷人返回的是一个空数组

2、each静态方法不支持在毁掉函数值中对遍历的数组进行处理

map静态方法可以在毁掉函数中通过return对遍历的数组进行处理，然后生成一个新的数组返回

## jQuery中其他静态方法

### $.trim();

作用：去除字符串两端的空格

参数：需要去除空格的字符串

返回值：去除空格之后的字符串

eg：

````javascript
var str = '    yyq    ';
var res = $.trim(str);
console.log('str');
````

### $.isWindow

作用：判断传入的对象是不是window对象

返回值：true/false

### $.isArray

作用：判断传入的对象是不是一个真数组

返回值：true/false

### $.isFunction

作用：判断传入的对象是不是一个函数（方法）

返回值：true/false

**注意**：jQuery框架本质上就是一个函数

## holdReady暂停事件

holdReady（true）加在绕口函数前 停止当前函数执行

holdReady（false）执行当前暂停的函数函数



## jquery内容选择器

:**empty**   作用找到没有文本 有没有子元素的标签

 ````javascript
var  $div = $("div:empty");
 ````



**:parent**  作用找到有文本内容或者子元素的指定元素

````javascript
var  $div = $("div:parent");
````

**:contains("text")**   找到**包涵**指定内容的div    注意是包涵

````javascript
var  $div = $("div:contains('text')");
````

**:has(selector)** 作用找到包涵指定子元素的元素

````javascript
var  $div = $("div:has(标签名)");
````

## 操作属性节点

DOM.serAttribute("属性名称","属性值")；

DOM.getAttribute("属性名称"	)；

## 属性和属性节点的区别

任何对象都有属性   但只有DOM对象才有属性节点

## jquery简单动画

show（）；显示        hide（）；隐藏          toggle（）；切换

**展开**  slideDown（）；展开   slideUp（）；收起   slideToggle（）；切换展开

**对联广告**

监听滚动条

 **$(window).scroll(function () {**
		**var offset = $('html,body').scrollTop();**
		 **})**

## jquery中的attr 属性

如果是**获取**    console.log$('span').attr('class');    无论找到了多少个span 标签  只会打印第一个class值

如果是**设置**   $('span').attr('class','box'); j 将找到的全部span标签class值设置为box     如果设置的属性不存在  将设置一个          新的属性和属性值

## jquery中的removeAttr 属性

 $('span').removeAttr('class');     会删除找到所有的span标签的class值  想删除多个直接在class后面用空格隔开就好

## jQuery中prop属性

prop方法    特点和attr方法一致

removeProp方法    特点和removeAttr方法一致

````HTML
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="node_modules/jquery/dist/jquery.js"></script>
	<script>
		$(function () {
			$("span").eq(0).prop('demo','it666');
			$("span").eq(1).prop('demo','it66');
			console.log($("input").prop("checked"));//ture /false
			console.log($("input").attr("checked"));//checked /undefined
		})


</script>
</head>
<body>
	<span class="span1"></span>
	<span class="span2"></span>
	<input type="text" checked>
</body>
</html>
````

官方推荐在操作属性节点的时，具有true 和false两个数字那个的属性节点。如 checked ，selected，disabled，使用prop（）其他使用attr（）；

## jQuery操作类相关方法

addClass   添加属性

removeClass  删除属性

toggleClass   切换属性

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		.class1{
			height: 100px;
			width: 100px;
			background-color: red;
		}
		.class2{
			border: 10px solid black;
		}
	</style>
	<script src="node_modules/jquery/dist/jquery.js"></script>
	<script>
		$(function () {
			var btn = document.getElementsByTagName('button');
			btn[0].onclick = function () {
				$("div").addClass("class1 class2");
			}
			btn[1].onclick = function () {
				$("div").removeClass("class1 class2");
			}
			btn[2].onclick = function () {
				$("div").toggleClass("class1 class2");
			}
		})
	</script>
</head>
<body>
	<button>增加</button>
	<button>删除</button>
	<button>切换</button>
	<div></div>
</body>
</html>
````



## jquery中 文本相关属性

html   相当于js中的innerHTML

text  相当于js中的innerTEXT

val  

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<style>
		div{
			width: 100px;
			height: 100px;
			border: 1px solid #000;
		}
	</style>
	<script src="node_modules/jquery/dist/jquery.js"></script>
	<script>
		$(function () {
			var btn = document.getElementsByTagName('button');
			btn[0].onclick = function () {
				$("div").html('<p>我是段落，<span>我是span</span></p>')
			}
			btn[1].onclick = function () {
				console.log($("div").html());
			}
			btn[2].onclick = function () {
				$("div").text('<p>我是段落，<span>我是span</span></p>')
			}
			btn[3].onclick = function () {
				console.log($("div").html());
			}
			btn[4].onclick = function () {
				$("input").val('我就是我');
			}
			btn[5].onclick = function () {
				console.log($("input").val());
				
			}
		})
	</script>
</head>
<body>
	<button>设置HTML</button>
	<button>获取HTML</button>
	<button>设置text</button>
	<button>获取text</button>
	<button>设置value</button>
	<button>获取value</button>
	<div></div>
	<input type="text">
</body>
</html>
````



## jquery 操作css样式



#  如何截取网页

Ctrl+shift +  p     然后输入capture

# SASS



**优势**  有编程语言的语法 能简化代码量

写中文的时候scss不能识别需要定义编码方式

scss中写注释必须要/**/

###公共类（样式）

````scss
/*定义部分*/
@.名字{
  样式集合
}

/*导入部分*/
@extend .名字;
````

###嵌套

````scss
.content{
    width: 800px;
    height: 300px;
    
    .content-left{
        float: left;
        
        a{
            text-decoration: none;
            
           &:hover{
            color: yellow;
           }
        }  
    }
    .content-right{
        float: right;
    }
    
````

###函数

````scss

/*
  参数  键值对
 $width:300px
 */
@mixin 函数名(形参){
   width: $width;
   height: $height; 
}


//导入
@include 函数名(实参);
````



###判断

````scss
@mixin test($condition){

  color: if(condition,blue,red);

  color:$color;

}

.First{

  @include test(true);

}

.Second{

  @include test(false);

}

$flag:false;

@if $flag {

    .div{

        color: red;

       }

    }

    

@else { .div{

    color: pink;

}

}

````



# gulp

1、项目初始化

?	gulp init -y

2、全局安装

nmp install gulp -g

3、下载到开发依赖、

nmp install gulp --save-dev

4、

自己在devDependencies配置你需要的插件名称以及版本

5、跑环境

nmp install

6、在当前目录下测试是否安装成功

gulp -v

## 基于gulp进行编译

1、gulp的所有操作都是基于gulpfile文件的 

>创建gulpfile.js文件

2、在gulpfile.js文件中华想要用到gulp模块或者gulp插件必须先导入let gulp = require（""）;

3、创建任务  

gulp.task（”任务名称“，[“依赖任务”,"可以使多个依赖任务"]，function（）{

?	}）；

4、src：源文件路径

dest：目标文件路径

pipe：输送，管道

gulp.task('copyHTML',function(){

return gulp.src("文件路径").pipe(gulp.dest("目标文件夹"))；

})

5、



# DOM

## DOM节点

DOM的作用：
用JavaScript操作HTML。
包括：在JavaScript中获取（查），添加，修改，删除
1）**、查：在JavaScript中获取HTML。**
document.getElementById()
document.getElementsByName()
document.getElementsByTagName() 通过标签查找html
document.getElementsByClassName()

根据DOM树的结构（节点关系）**获取**
某个节点.**firstChild**; //某个节点的第一个子节点（包括空格）
某个节点.**lastChild**;**
某个节点.**childNodes;**
某个节点.**parentNode;**
某个节点.**previousSibling;**
某个节点.**nextSibling;**

某个节点.**firstElementChild**; //第一个元素标签；不包含空格
某个节点.**lastElementChild;**
某个节点**.children;**
某个节点.**parentNode;**
某个节点.**previousElementSibling;**
某个节点.**nextElementSibling;**

//2)、**添加**
document.createElement(标签名);
document.createTextNode();

父节点.appendChild(子节点)

//3)、**删除**
父节点.removeChild(子节点)

要删除的节点.remove();

//4)、**修改**
父节点.replaceChild(新节点，旧节点);

## DOM0级 和DOM2级 绑定事件

````javascript
window.onload = function(){
	//1、DOM0级，在同类型的事件里只能绑定一个事件处理函数
	$("btn01").onclick = function(){
		alert('啊1----------，我被点疼了');
	}

	//第二个函数把第一个函数覆盖了
	$("btn01").onclick = function(){
		alert('啊2----------，我被点疼了');
	}

	//2、DOM2级，在同类型的事件里能绑定多个事件处理函数
	$("btn01").addEventListener('click',function(){
		alert('啊1----------，我被点疼了');
	},false);
	
	$("btn01").addEventListener('click',function(){
		alert('啊2----------，我被点疼了');
	},false);
	
}

function $(id){
	return document.getElementById(id);
}

````



## DOM  2级事件冒泡

````javascript
//DOM2级：既支持冒泡，又支持捕获。第三个参数设置为false，就表示事件冒泡；
	$("meBox").addEventListener("click",function(){
		console.log("我被点了");
	},false);
	
	$("fatherBox").addEventListener("click",function(){
		console.log("爸爸被点了");
	},false);
	
	$("grandpaBox").addEventListener("click",function(){
		console.log("爷爷被点了");
	},false);

````

