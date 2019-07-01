## 																																											基本命令

el:'id值'；

data：{

数据：数据值

}

methods：{

方法如   add：function（）{

}

}

###a标签链接

<a  v-bind：href="  " >    </a>

###按钮点击事件

v-on：click =“方法”     可改写为@click = “方法”；

v-on：dblclick =“方法”     可改写为@dblclick = “方法”；

### 事件修饰符

once 只有一次有效果

stop  停止

prevent 阻止默认事件

````html
			<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
		#box{
			width: 400px;
			height: 400px;
			border: 1px solid #ccc;
			text-align: center;
			line-height: 400px;
		}
	</style>

</head>
<body>
	<div id="app">
		<p>{{ message }}</p>
		<!-- <input type="text" v-model="message"> -->
		<p>{{ name }}</p>
		<a v-bind:href="web">aaaa</a>
		<p>我今年{{ age }}岁了</p>
		<button @click='add'>加一岁</button>
		<button @click='jian'>减一岁</button>
		<button @dblclick='add'>加一岁</button>
		<button @dblclick='jian'>减一岁</button>
		<p>{{ hao() }}</p>

		<div id="box" @mousemove='updataxy'>{{x}},{{y}} <span @mousemove.stop=''>ssssssss</span></div>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			message: '啊啊啊啊',
			name:'你好',
			web:'http://www.baidu.com',
			age:'30',
			x:0,
			y:0
		},
		methods:{
			add: function () {
				this.age++
			},
			jian: function () {
				this.age--
			},
			hao: function () {
				return 'good good';
			},
			updataxy: function () {
				this.x = event.offsetX;
				this.y = event.offsetY;
			}
			
		}
	})
````



### 键盘事件以及键值修饰符

@keyup.enter="方法名"

@keyup.alt.enter="方法名"

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
	
	</style>

</head>
<body>
	<div id="app">
		<input type="text" @keyup.enter='anxia'>
		<input type="text" @keyup.alt.enter='anxia'>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			
		},
		methods:{
			anxia: function () {
				console.log('你正在输入你的姓名')
			}

		}
	})

</script>
````

### 双向数据绑定

v-model="el 定义的啥就写啥"

ref="随机写"

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>

	</style>

</head>
<body>
	<div id="app">
		<input type="text" v-model='name'><span>{{name}}</span>
        <input type="text" ref='names' @keyup='logname'><span>{{namess}}</span>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			name:'',
			namess:''
		},
		methods:{
            logname:function(){
                this.namess = this.$refs.names.value;																																																																			
            }
		}
	})

</script>
````



### render

### computed     计算属性

computed  更有效的提高计算机的性能

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>

	</style>

</head>
<body>
	<div id="app">
		<button @click="a++">addToA</button>
		<button @click="b++">addToB</button>
		<p>{{ a }}</p>
		<p>{{ b }}</p>
		<p>{{addToA}}</p> <!-- 方法后面不能加（） -->
		<p>{{addToB}}</p> <!-- 方法后面不能加（） -->
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			a:0,
			b:0,
			age:20
		},
		 //影响性能
		methods:{    
            // addToA:function(){
            //     return this.a+this.age;
            // },
            // addToB:function(){
            //     return this.b+this.age;
            // }
		},

		computed:{
            addToA:function(){
                return this.a+this.age;
            },
            addToB:function(){
                return this.b+this.age;
            }
		},
	})

</script>
````

### 动态绑定css样式

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
		span{
			width: 300px;
			height: 300px;
			background-color: red;
			font-size: 50px;
		}
		.changeColor span{
			background-color: green;
		}
		.changeLenght span:after{
			content: 'lenght';
			margin-left:50px;
		}
	</style>

</head>
<body>
	<div id="app">
		<h1>实例1</h1>
		<!-- 改变颜色  -->
		<!-- <div v-on:click="changeColor = !changeColor" v-bind:class="{changeColor:changeColor}">
			<span>color</span>
		</div> -->

		<!-- 改变长度 -->
		<!-- <div @click="changeLenght = !changeLenght" v-bind:class="{changeLenght:changeLenght}">
			<span>sssssss</span>
		</div> -->

		<h1>实例2</h1>
		<button @click="changeColor = !changeColor,changeLenght = !changeLenght">按钮</button>
		<button @click="changeLenght = !changeLenght">按钮</button>
		<div v-bind:class="compColor">
			<span>sssssss</span>
		</div>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			changeColor:false,
			changeLenght:false
		},
		
		methods:{    
          
		},

		computed:{
            compColor:function () {
            	return {
            		changeColor:this.changeColor,
            		changeLenght:this.changeLenght
            	}
            }
		},
	})

</script>
````

### v-if      v-else-if    v-show

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
		
	</style>

</head>
<body>
	<div id="app">
		<button @click="error = !error">错误提示</button>
		<button @click="success = !success">成功提示</button>
		<!-- <p v-if="error">连接错误：404</p>
		<p v-else-if="success">连接成功：200</p> -->


		<!-- 占位标签  显示display：none -->
		<p v-show="error">连接错误：404</p>
		<p v-show="success">连接成功：200</p>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			error:false,
			success:false
		},
		
		methods:{    
          
		},

		computed:{
            
		},
	})

</script>
````

### 插值表达式

作用：绑定viewmodel 中的 data  methods    2，输入绑定的值

### 指令

指令（directive）：内置指令   2自定义指令  3组件 component

v-text 





### 循环遍历指令   v-for     

(值，下表)

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>

	</style>

</head>
<body>
	<div id="app">
		<ul>
			<li v-for="a in age">{{a}}</li>
		</ul>
		<ul>
            
			<li v-for="(b,index) in user">{{index}}.{{b.name}} - {{b.age}}</li>
		</ul>
        	<!-- 防止多个div标签  可以将div 切换成 template -->
		<template v-for="(b,index) in user">
			<h3>{{index}},{{b.name}}</h3>
			<p>{{b.age}}</p>
		</template>

		
		<template v-for="(b,index) in user">
			<!-- key 属性值  val 属性 -->
			<div v-for="(key,val) in b">
				<p>{{val}} - {{key}}</p>
			</div>
		</template>
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			age:["姚垚奇","有一种","有疑问"],
			user:[
				{"name":"yyq","age":18},
				{"name":"yyq1","age":187},
				{"name":"yyq2","age":188}
			]
		},
		
		methods:{    
           
		},

		computed:{
           
		},
		watch:{
			
		},
	})

</script>
````



### 事件绑定指令

v-on:     / @

### 属性绑定指令     v-bind

v-bind：属性名     / :属性名

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>

	</style>

</head>
<body>
	<div id="app">
		<img v-bind:src="dizhi" alt="">
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			dizhi:"image/5555.png"
		},
		
		methods:{    
           
		},

		computed:{
           
		},
		watch:{
			
		},
	})

</script>
````



表单绑定指令

v-model

form element ：

1  input   textarea    text  pass  radio  CheckBox

2  select

3  watch

### watch

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>

	</style>

</head>
<body>
	<div id="app">
		<input type="text" v-model="age">
	</div>

</body>
</html>
<script>
	new Vue({
		el:'#app',
		data:{
			age:5000
		},
		
		methods:{    
           
		},

		computed:{
           
		},
		watch:{
			"age":(n,o)=>{
				console.log(n,o)
			}
		},
	})

</script>
````

### 生命周期

第一阶段：创建期 1、beforeCreate 2、created：实例创建完成。

第二阶段：挂载期 1、beforeMount 2、mounted：页面一已生成了ready。

第三阶段： 更新期 1、beforeUpdate 2、updated

第四阶段：销毁期 1、beforeDestroy 2、destroyed

### 创建多个实例化对象

修改实例化中的内容： 写一个方法调用  2  在最后修改

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
		
	</style>

</head>
<body>
	<div id="app-one">
		<h2>{{title}}</h2>
		<p>{{green}}</p>
	</div>
	<div id="app-two">
		<h2>{{title}}</h2>
		<p>{{green}}</p>
		<button v-on:click="ChangeTitle">改名字</button>
	</div>
</body>
</html>
<script>
	let one = new Vue({
		el:'#app-one',
		data:{
			title:"第一个app"
		},
		
		methods:{    
           
		},

		computed:{
           green:()=>{
			   return "第一个";
		   }
		},
		watch:{
			
		},
	})
	
	let two = new Vue({
		el:'#app-two',
		data:{
			title:"第2个app"

		},
		
		methods:{    
			//写一个方法调用 修改别的实例化中的内容
	       ChangeTitle:()=>{
			   one.title = "我要改名字";
		   }
		},
	
		computed:{
	       green:()=>{
	       			   return "第er 个";
	       }
		},
		watch:{
			
		},
	})
	// 直接在最后修改想要修改的内容
	two.title="发生变化了";

</script>
````

### 初识组件

需要写一个Vue.component（“标签名”，{  template：`写标签`  }）

````html
Vue.component("yyq",{
		template:`<p>{{name}}大家好这是我的女朋友@XXX<button @click="changename()">修改</button></p>`,
		data:function(){
			return {
				name:'姚垚奇'
			}; 
		},
		methods:{
			changename: function (){
				this.name = '对对对:'
			}
		}
	})
````



data 是一个函数  数据需要return出去   data：function（）{ return {  数据：值  }   }

````html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>Document</title>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	<style>
		
	</style>

</head>
<body>
	<div id="app-one">
		<yyq></yyq>
	</div>
	<div id="app-two">
		<yyq></yyq>

	</div>
</body>
</html>
<script>
	//暴露在外 一个修改全部修改
	// var data={
	// 	name:'wwww'
	// };
	// Vue.component("yyq",{
	// 	template:`<p>{{name}}大家好这是我的女朋友@XXX<button @click="changename()">修改</button></p>`,
	// 	data:function(){
	// 		return data; 
	// 	},
	// 	methods:{
	// 		changename: function (){
	// 			this.name = '对对对:'
	// 		}
	// 	}
	// })
	
	Vue.component("yyq",{
		template:`<p>{{name}}大家好这是我的女朋友@XXX<button @click="changename()">修改</button></p>`,
		data:function(){
			return {
				name:'姚垚奇'
			}; 
		},
		methods:{
			changename: function (){
				this.name = '对对对:'
			}
		}
	})
	
	
	new Vue({
		el:'#app-one',
		
	})
	
	new Vue({
		el:'#app-two',
		
	})
	
</script>
````

### Vue CLI  脚手架

脚手架时webpack搭建的开发环境

使用ES6语法

打包和压缩js为一个文件

项目文件在环境中编译而不是在浏览器

实现页面自动刷新

 ### src流程及根组件

index.html ->  main.js ->app.vue

App.vue 包括三个  1  模板 HTML标签 template 里面 **有且只能有一个**根标签

​				2行为  处理逻辑   想让两个组件之间有关联 必须用import  并且注册

​				3 样式   解决样式

###组件嵌套



先建立一个vus文件  写上三步 模板   行为    样式   然后在main.js中引用 并全局注册  最后在App.vue中 写上标签名

必须在main.js中 全局注册  Vue.component("标签名字",组件名字);    前面必须加**import 组件名 from '组件地址'**

### 传值   传引用

传值    string  number   boolean     自己改变自己的 互不影响

引用 array  object    一个改变全改变

###  父传子

**父组件负责数据和逻辑**  **子组件负责渲染页面**

在父组件App.vue 中设置 在传给需要的子组件

要注意加v-bind：XX="XX"

在子组件中写props：{ 

​	XX：{

​		type：值类型             array  string number 

​	}

}

### 事件传值 子传父      

**使用事件传值**

：输入             @输出

注册事件$emit("事件名字","要传的内容")

### 插槽 

默认插槽      <slot></solt>

### 路由

​																			