# Math

##Math常用属性

Math.round(3.6) //四舍五入 

random()              //返回0-1之间的随机数 

max(num1, num2)     //返回较大的数 

min(num1, num2)     //返回较小的数

 abs(num)          //绝对值 

ceil(19.3)        //向上取整“20”

 floor(11.8)     //向下取整“11” 

pow(x,y)         //x的y次方 

sqrt(num)   //开平方 

## 十进制转16进制或8进制 

十进制转其他 ：

 var x=110; alert(x); 

alert(x.toString(8)); 

alert(x.toString(32)); 

alert(x.toString(16));  

# Date对象

Date对象用于处理日期和时间，Date对象记录着从1970年1月1日00:00:00开始以来的毫秒数。

 ## Date对象的定义

 var myDate=new Date() ;            //Date 对象自动使用当前的日期和时间作为其初始值。 

##创建Date对象同时指定日期和时间：

 new Date("month dd,yyyy hh:mm:ss");

 new Date("month dd,yyyy"); 

new Date(yyyy,mth,dd,hh,mm,ss); 

new Date(yyyy,mth,dd);

 new Date(ms); 

## 日期对象的函数 

###获取时间：

 getDate() 		//返回天

 getDay() 		//返回星期几 ，**从0开始**

 getHours() 		//返回小时数 

getMinutes() 		//返回分钟数 

getMonth() 		//返回月份值 ，**从0开始** 

getSeconds() 		//返回秒数 

getTime() 		//返回完整的时间 ，**毫秒数**

 getFullYear() 		//返回年份 

###设置时间

setDate()		 //改变Date对象的日期 

setHours() 		//改变小时数

 setMinutes() 		//改变分钟数

 setMonth() 		//改变月份，**从0开始**

 setSeconds() 		//改变秒数 

setTime()		 //改变完整的时间，**毫秒数** 

setYear()		 //改变年份 

## 日期转换 

###字符串转换时间戳：

 **Date.parse**(日期字符串或日期对象) //返回自1970年1月1日起至参数日期止的毫秒数 

###Date转换为字符串：

 **toTimeString()**

 // 把 Date 对象的时间部分转换为字符串。 

**toDateString()** 

//把 Date 对象的日期部分转换为字符串。

 **toUTCString()** 

//根据世界时，把 Date 对象转换为字符串。

 **toLocaleString()** 

//根据本地时间格式，把 Date 对象转换为字符串。

 **toLocaleTimeString()** 

//根据本地时间格式，把 Date 对象的时间部分转换为字符串。

 **toLocaleDateString()** 

//根据本地时间格式，把 Date 对象的日期部分转换为字符串。 

## 定时器

###setInterval（回调函数，毫秒数）

设置每隔指定的毫秒数执行一次回调函数，返回定时器编号。

###clearInterval（定时器编号）

清除定时器设置。 

###setTimeout（回调函数，毫秒数） 

设置在指定的毫秒数后执行一次回调函数，返回定时器编号。 

###clearTimeout （定时器编号）

清除定时器设置。 注：因为只执行一次回调函数，所以为达到不停执行回调函数的效果必须在回调函数中再次设置。 

# BOM

## Window对象的属性 

 Document对象。

 history对象。

 Location对象 

Screen对象

 **name** 浏览器窗口的名字 

defaultStatus 		设置或返回窗口状态栏中的默认文本。

 status		 设置窗口状态栏的文本 

## location对象 

###ocation对象的属性

href属性		 控制浏览器地址栏的内容

 hostname		 设置或返回当前 URL 的主机名。

### location对象的方法 

reload()		方法 刷新页面 

reload(true) 		刷新页面，不使用缓 

## history对象 

###属性 ：

 length 		返回浏览器窗口历史列表中的 URL 数量。

### 方法 ：

 back() 		加载 history 列表中的前一个 URL。

 forward() 		加载 history 列表中的下一个 URL。

 **go()	**	 加载 history 列表中的某个具体页面，或者要求浏览器移动到指定的页面数量（负数为后退，正 数为前进） 

## navigator对象 

appName 	浏览器名称 

appVersion 	浏览器版本

 platform操作系统     	  注：最新的浏览器已经全面放弃以上这些属性

 userAgent 	用户代理信息，通过该属性可以获取浏览器及操作系统信息 

## document对象 

**每个载入浏览器的 HTML 文档都会成为 Document 对象。**

 Document 对象使我们可以从脚本中对 HTML 页面中的所有元素进行访问 

Document 对象是 Window 对象的一部分，可通过 window.document 属性对其进行访问 

###Document对象的属性 

all[] 		提供对文档中所有 HTML 元素的访问。是数组类型 

forms[] 		返回对文档中所有 Form 对象引用。是数组类型

 body 		提供对  元素的直接访问。

 URL 		返回当前文档的 URL。

 bgColor属性：	可以改变文档的颜色；（ document.bgColor="gray";） 

###Document对象的函数(方法) 

getElementById()		 返回对拥有指定 id 的第一个对象的引用。 

getElementsByName() 		返回带有指定名称的对象集合。

 getElementsByTagName() 		返回带有指定标签名的对象集合。

 write() 		向文档写 HTML 表达式 或 JavaScript 代码。 

## Window对象的方法 

**alert(“”)** 		显示带有一段消息和一个确认按钮的警告框。 

**confirm(“”)** 		显示带有一段消息以及确认按钮和取消按钮的对话框。

 **prompt(“”)** 		显示可提示用户输入的对话框。

 **open(“url”,”name”)** 		打开一个新的浏览器窗口或查找一个已命名的窗口。

 **showModalDialog** 		(“打开窗口的url”,”窗口名”,”窗口特征”)(chrome不支持) 

**close()** 		关闭浏览器窗口。 （ FF不支持）

 **focus ()** 		窗口失去焦点 

**setInterval()** 		按照指定的周期（以毫秒计）来调用函数或计算表达式。

 **clearInterval()** 		取消由 setInterval() 设置的 timeout。

 **setTimeout()** 		在指定的毫秒数后调用函数或计算表达式。

 **clearTimeout()** 		取消由 setTimeout() 方法设置的 timeout。

 **moveBy()** 		可相对窗口的当前坐标把它移动指定的像素。

 **moveTo()** 		把窗口的左上角移动到一个指定的坐标。

 **resizeBy()** 		按照指定的像素调整窗口的大小

 **resizeTo()** 		把窗口的大小调整到指定的宽度和高度。

 **scrollBy()** 		按照指定的像素值来滚动内容。

 **scrollTo()** 		把内容滚动到指定的坐标。 

## 对话框

**confirm(“”)** 		显示带有一段消息以及确认按钮和取消按钮的对话框。 确认框，一般在删除时，会使用。 

**prompt(“”)** 		显示可提示用户输入的对话框。 

## 打开窗口

**window.open(“url”,”name”,”窗口特征”) 打开一个新的浏览器窗口或查找一个已命名的窗口。** 

###窗口特征： 

 **width=pixels** 		窗口的文档显示区的宽度。以像素计。

 **height=pixels** 		窗口文档显示区的高度。以像素计

 **left=pixels** 		窗口的 x 坐标。以像素计。

 **top=pixels** 		窗口的 y 坐标。 location=yes|no|1|0 是否显示地址字段。默认是 yes。

 **menubar**=yes|no|1|0 		是否显示菜单栏。默认是 yes。 (需要父窗口菜单栏处于显示状态) 

**resizable**=yes|no|1|0 		窗口是否可调节尺寸。默认是 yes。

 **scrollbars**=yes|no|1|0 		是否显示滚动条。默认是 yes。

 **status**=yes|no|1|0 		是否添加状态栏。默认是 yes

 **titlebar**=yes|no|1|0 		是否显示标题栏。默认是 yes。

 **toolbar**=yes|no|1|0 		是否显示浏览器的工具栏。默认是 yes。

# DOM

## 查询元素节点 

**getElementById()**			 //获取特定 ID 元素的节点 

**getElementsByTagName()** 		//获取相同标签名的元素节点，返回数组，使用[0]来获取

 **getElementsByName()** 		//获取相同name属性的元素节点，不是所有标签都有name属性，某些低版 本浏览器会有兼容性问题

 **getElementsByClassName()** 		//获取相同class属性的节点列表 IE8及以下不支持 

## 通过层级关系访问节点 

**parentNode** 		父节点。

 **childNodes** 		当前节点包含的所有子节点(文本和元素节点都有)。

 **firstChild** 		当前节点的第一个子节点。

 **lastChild** 		当前节点的最后一个子节点。 

**previousSibling** 		访问前一个同胞节点。

 **nextSibling** 		访问后一个同胞节点。 

## 通过层级关系访问元素节点 

**parentNode** 		父节点

 **children** 	当前节点的所有子节点(只有元素节点)，即所有的元素类型的子节点

 **firstElementChild** 	当前节点的第一个元素类型的子节点。

 **lastElementChild** 		当前节点的最后一个元素类型的子节点。 

**previousElementSibling** 	访问前一个同胞元素类型的节点。

**nextElementSibling** 	访问后一个同胞元素类型的节点。 

## 节点的增删改 

**document.createElement(HTML标签名)**    		//创建一个元素节点 

**document.createTextNode(文字**)     		//创建一个文本节点 

**node.appendChild(newChild)**       //newChild 被添加到孩子列表中的末端。

 **node.insertBefore(newChild, referenceNode)** 			// 将 newChild 节点插入到 referenceNode 之前。 

**node.removeChild(oldChild)** 			//删除 oldChild子节点。

 **node.replaceChild(newChild, oldChild)** 			//用newChild节点替换oldChild节点 

## 表格的增删改 

###表上的行、列集合

 tab.rows[index]; //取得表中的某一行 

row.cells[index]; //取得行中某一列

 ### 插入

 tab.insertRow(index); //插入新行并返回新行

ndex为插入位置不写插入到表末 row.insertCell(index); //插入新列并返回新列，

index为插入位置不写插入到行末

### 删除

 tab.deleteRow(index); 

row.deleteCell(index);  

## window.onscroll 页面滚动事件 

###取得滚动条位置 

document.body.scrollTop //谷歌(设为0页面回到顶部) 

document.documentElement.scrollTop //标准 

###兼容写法 

document.documentElement.scrollTop || document.body.scrollTop 

###页面可见区域高度

 document.body.clientHeight（如果出现问题用document.documentElement.clientHeight） 

###取得某元素距离外层元素的距离， 

外层元素必须定位，否则就会找外外层，直到body obj.offsetTop （不能设置，仅能获取）

### 设置元素高度使用 

obj.style.top 