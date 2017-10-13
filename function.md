>
1. 变量声明提升
所有的声明变量或生命函数都会被提升至当前函数的顶部

2. 函数表达式
var getName=function(){} 与function getName()都是声明语句，区别在于，var getName是函数表达式，function getName是函数声明


---
>
1. js的几种函数：命名函数和匿名函数

区分函数的方法，输出fn.name，有name就是命名函数，没有就是匿名函数

2. 创建函数的几种方式

a. 声明函数
function fn1(){}

b. 创建匿名函数表达式（匿名函数），创建一个变量，这个变量的内容为一个函数，所有声明的匿名函数都是一个新的函数

var fn1=function(){}

c. 创建具名函数表达式，创建一个变量，变量的内容为一个带有名称的函数
var fn1=function test(){},这种方法创建的函数外层只能用fn1不能用test的函数名，test的函数名只能在创建的函数内部使用

d. 自执行函数
(function(){alert(1;)})()
(function fn1(){alert(1);})();

---
>
函数作用域链的问题
测试1：对象内部的函数表达式  
var o={
fn:function(){
	   console.log(fn);
   }
}
o.fn;//error,fn is not defined

测试2：非对象内部的函数表达式
var fn=function(){
	console.log(fn)
}
fn();//function(){console.log()}

结论：对象内部的函数表达式不能访问存放当前的变量，使用var或是非对象内部的函数表达式内可以访问到当前函数的变量

function fun(n,o) {
	console.log(o)
		return {
fun:function(m){
	    return fun(m,n);
    }
		};
}

//下列的输出结果
var a = fun(0);a.fun(1);a.fun(2);a.fun(3);//undefined,?,?,?
var b = fun(0).fun(1).fun(2).fun(3);//undefined,?,?,?
var c = fun(0).fun(1);  c.fun(2);  c.fun(3);//undefined,?,?,?

//第一个fun是函数声明，创建新的函数，返回值是一个对象字面量表达式，属于新的obj,新的对象中包含fun的属性，属于匿名函数表达式

声明的匿名函数是一个新的函数，所有第一个fun和第二个fun函数不同，均为创建新的函数

使用var的是在外部创建了一个fn变量，函数内部寻找不到fn向上级作用域查找fn，而在创建对象内部时，因为没有在函数作用域内创建fn，所以无法访问，最内层的retur出去的fun函数不是第二层fun函数，是最外层的fun函数



