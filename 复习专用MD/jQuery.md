# jquery

## ��ں���

````javascript
$(function () {
		

	})
````



## jQuery���$��ͻ

����ں���ǰд�� **jQuery.onConflict ();**ע���Ժ��$Ҫд��**jQuery**

�Զ���

 **yyq = jQuery.onConflict ();**

## ʲô��jquery����

jQuery�������һ��α����

ʲô��α���飿  ��0--length-1������ ����length����

## ��̬����     ʵ������

**��̬����** ��ֱ����Ӹ���ľ��Ǿ�̬����       ��̬����ͨ����������

````javascript
//����һ����
		function Aclass() {
			
		}
		//��Ӿ�̬����
		Aclass.staticMethod = function () {
			alert('staticMethod ��˼�Ǿ�̬����');
		}
		//ͨ����������
		Aclass.staticMethod();
````



**ʵ������**������������һ��ʵ������   ����һ��ʵ��������һ������   ͨ�����ʵ������      

````javascript
//����һ����
		function Aclass() {
			
		}
		//���ʵ������
		Aclass.prototype.instanceMethod = function () {
			alert('instanceMethod ��˼��ʵ������');
		}
		//����һ��ʵ��������һ������
		var a = new Aclass();
		//ͨ�����ʵ����������
		a.instanceMethod();
````

##jQuery.each����

**ԭ��JS��foreach����**  ֻ�ܱ�������  ���ܱ���α����        



````javascript
var arr = [1,3,5,7,9];
	//��һ�������Ǳ�������Ԫ��
	//�ڶ��������Ǳ�����������
	arr.forEach(function (value,index) {
		console.log(index,value);
	});
````

**jQuery�е�each����**    ���ܱ�������  ���ܱ���α����

````javascript
var obj = {0:1,1:3,2:4,3:5,4:7, length:5};
	//��һ�������Ǳ�����������
	//�ڶ��������Ǳ�������Ԫ��
	$.each(obj,function (index,value) {
		console.log(index,value);
	});
````

## jQuery.map����

ԭ��JS��map����

````javascript
var arr = [1,3,5,7,9];
	//��һ�������Ǳ�������Ԫ��
	//�ڶ��������Ǳ�����������
	//����������������Ǳ������ĸ�����
	arr.map(function (index,value,array) {
		console.log(index,value,array);
	})
````

jQuery�е�map����

````javascript
var obj = {0:1,1:3,2:4,3:5,4:7, length:5};
	//map�еĲ���
	//��һ����Ҫ����������/α����
	//�ڶ�����û����һ������֮��ִ�лٵ�����
	//�����еĲ���
	//��һ�������Ǳ�������Ԫ��
	//�ڶ��������Ǳ�����������
	$.map(obj,function (value,index) {
		console.log(value,index);
	})
````

## jQuery�е�each��̬������map��̬��������ͬ��Ͳ�ͬ��

**��ͬ��**

���ܱ��������α����

**����**

1��each��̬����Ĭ�Ϸ���ֵ�ǣ�����˭�ͷ���˭

map�еľ�̬�������˷��ص���һ��������

2��each��̬������֧���ڻٵ�����ֵ�жԱ�����������д���

map��̬���������ڻٵ�������ͨ��return�Ա�����������д���Ȼ������һ���µ����鷵��

## jQuery��������̬����

### $.trim();

���ã�ȥ���ַ������˵Ŀո�

��������Ҫȥ���ո���ַ���

����ֵ��ȥ���ո�֮����ַ���

eg��

````javascript
var str = '    yyq    ';
var res = $.trim(str);
console.log('str');
````

### $.isWindow

���ã��жϴ���Ķ����ǲ���window����

����ֵ��true/false

### $.isArray

���ã��жϴ���Ķ����ǲ���һ��������

����ֵ��true/false

### $.isFunction

���ã��жϴ���Ķ����ǲ���һ��������������

����ֵ��true/false

**ע��**��jQuery��ܱ����Ͼ���һ������

## holdReady��ͣ�¼�

holdReady��true�������ƿں���ǰ ֹͣ��ǰ����ִ��

holdReady��false��ִ�е�ǰ��ͣ�ĺ�������



## jquery����ѡ����

:**empty**   �����ҵ�û���ı� ��û����Ԫ�صı�ǩ

 ````javascript
var  $div = $("div:empty");
 ````



**:parent**  �����ҵ����ı����ݻ�����Ԫ�ص�ָ��Ԫ��

````javascript
var  $div = $("div:parent");
````

**:contains("text")**   �ҵ�**����**ָ�����ݵ�div    ע���ǰ���

````javascript
var  $div = $("div:contains('text')");
````

**:has(selector)** �����ҵ�����ָ����Ԫ�ص�Ԫ��

````javascript
var  $div = $("div:has(��ǩ��)");
````

## �������Խڵ�

DOM.serAttribute("��������","����ֵ")��

DOM.getAttribute("��������"	)��

## ���Ժ����Խڵ������

�κζ���������   ��ֻ��DOM����������Խڵ�

## jquery�򵥶���

show��������ʾ        hide����������          toggle�������л�

**չ��**  slideDown������չ��   slideUp����������   slideToggle�������л�չ��

**�������**

����������

 **$(window).scroll(function () {**
		**var offset = $('html,body').scrollTop();**
		 **})**

## jquery�е�attr ����

�����**��ȡ**    console.log$('span').attr('class');    �����ҵ��˶��ٸ�span ��ǩ  ֻ���ӡ��һ��classֵ

�����**����**   $('span').attr('class','box'); j ���ҵ���ȫ��span��ǩclassֵ����Ϊbox     ������õ����Բ�����  ������һ��          �µ����Ժ�����ֵ

## jquery�е�removeAttr ����

 $('span').removeAttr('class');     ��ɾ���ҵ����е�span��ǩ��classֵ  ��ɾ�����ֱ����class�����ÿո�����ͺ�

## jQuery��prop����

prop����    �ص��attr����һ��

removeProp����    �ص��removeAttr����һ��

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

�ٷ��Ƽ��ڲ������Խڵ��ʱ������true ��false���������Ǹ������Խڵ㡣�� checked ��selected��disabled��ʹ��prop��������ʹ��attr������

## jQuery��������ط���

addClass   �������

removeClass  ɾ������

toggleClass   �л�����

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
	<button>����</button>
	<button>ɾ��</button>
	<button>�л�</button>
	<div></div>
</body>
</html>
````



## jquery�� �ı��������

html   �൱��js�е�innerHTML

text  �൱��js�е�innerTEXT

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
				$("div").html('<p>���Ƕ��䣬<span>����span</span></p>')
			}
			btn[1].onclick = function () {
				console.log($("div").html());
			}
			btn[2].onclick = function () {
				$("div").text('<p>���Ƕ��䣬<span>����span</span></p>')
			}
			btn[3].onclick = function () {
				console.log($("div").html());
			}
			btn[4].onclick = function () {
				$("input").val('�Ҿ�����');
			}
			btn[5].onclick = function () {
				console.log($("input").val());
				
			}
		})
	</script>
</head>
<body>
	<button>����HTML</button>
	<button>��ȡHTML</button>
	<button>����text</button>
	<button>��ȡtext</button>
	<button>����value</button>
	<button>��ȡvalue</button>
	<div></div>
	<input type="text">
</body>
</html>
````



## jquery ����css��ʽ



#  ��ν�ȡ��ҳ

Ctrl+shift +  p     Ȼ������capture

# SASS



**����**  �б�����Ե��﷨ �ܼ򻯴�����

д���ĵ�ʱ��scss����ʶ����Ҫ������뷽ʽ

scss��дע�ͱ���Ҫ/**/

###�����ࣨ��ʽ��

````scss
/*���岿��*/
@.����{
  ��ʽ����
}

/*���벿��*/
@extend .����;
````

###Ƕ��

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

###����

````scss

/*
  ����  ��ֵ��
 $width:300px
 */
@mixin ������(�β�){
   width: $width;
   height: $height; 
}


//����
@include ������(ʵ��);
````



###�ж�

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

1����Ŀ��ʼ��

?	gulp init -y

2��ȫ�ְ�װ

nmp install gulp -g

3�����ص�����������

nmp install gulp --save-dev

4��

�Լ���devDependencies��������Ҫ�Ĳ�������Լ��汾

5���ܻ���

nmp install

6���ڵ�ǰĿ¼�²����Ƿ�װ�ɹ�

gulp -v

## ����gulp���б���

1��gulp�����в������ǻ���gulpfile�ļ��� 

>����gulpfile.js�ļ�

2����gulpfile.js�ļ��л���Ҫ�õ�gulpģ�����gulp��������ȵ���let gulp = require��""��;

3����������  

gulp.task�����������ơ���[����������,"����ʹ�����������"]��function����{

?	}����

4��src��Դ�ļ�·��

dest��Ŀ���ļ�·��

pipe�����ͣ��ܵ�

gulp.task('copyHTML',function(){

return gulp.src("�ļ�·��").pipe(gulp.dest("Ŀ���ļ���"))��

})

5��



# DOM

## DOM�ڵ�

DOM�����ã�
��JavaScript����HTML��
��������JavaScript�л�ȡ���飩����ӣ��޸ģ�ɾ��
1��**���飺��JavaScript�л�ȡHTML��**
document.getElementById()
document.getElementsByName()
document.getElementsByTagName() ͨ����ǩ����html
document.getElementsByClassName()

����DOM���Ľṹ���ڵ��ϵ��**��ȡ**
ĳ���ڵ�.**firstChild**; //ĳ���ڵ�ĵ�һ���ӽڵ㣨�����ո�
ĳ���ڵ�.**lastChild**;**
ĳ���ڵ�.**childNodes;**
ĳ���ڵ�.**parentNode;**
ĳ���ڵ�.**previousSibling;**
ĳ���ڵ�.**nextSibling;**

ĳ���ڵ�.**firstElementChild**; //��һ��Ԫ�ر�ǩ���������ո�
ĳ���ڵ�.**lastElementChild;**
ĳ���ڵ�**.children;**
ĳ���ڵ�.**parentNode;**
ĳ���ڵ�.**previousElementSibling;**
ĳ���ڵ�.**nextElementSibling;**

//2)��**���**
document.createElement(��ǩ��);
document.createTextNode();

���ڵ�.appendChild(�ӽڵ�)

//3)��**ɾ��**
���ڵ�.removeChild(�ӽڵ�)

Ҫɾ���Ľڵ�.remove();

//4)��**�޸�**
���ڵ�.replaceChild(�½ڵ㣬�ɽڵ�);

## DOM0�� ��DOM2�� ���¼�

````javascript
window.onload = function(){
	//1��DOM0������ͬ���͵��¼���ֻ�ܰ�һ���¼�������
	$("btn01").onclick = function(){
		alert('��1----------���ұ�������');
	}

	//�ڶ��������ѵ�һ������������
	$("btn01").onclick = function(){
		alert('��2----------���ұ�������');
	}

	//2��DOM2������ͬ���͵��¼����ܰ󶨶���¼�������
	$("btn01").addEventListener('click',function(){
		alert('��1----------���ұ�������');
	},false);
	
	$("btn01").addEventListener('click',function(){
		alert('��2----------���ұ�������');
	},false);
	
}

function $(id){
	return document.getElementById(id);
}

````



## DOM  2���¼�ð��

````javascript
//DOM2������֧��ð�ݣ���֧�ֲ��񡣵�������������Ϊfalse���ͱ�ʾ�¼�ð�ݣ�
	$("meBox").addEventListener("click",function(){
		console.log("�ұ�����");
	},false);
	
	$("fatherBox").addEventListener("click",function(){
		console.log("�ְֱ�����");
	},false);
	
	$("grandpaBox").addEventListener("click",function(){
		console.log("үү������");
	},false);

````

