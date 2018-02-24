---
title: 重温js——基本概念
date: 2017-11-08 11:09:37
tags:
---
新年计划就是：一方面专业知识的沉淀，二是其他方面的继续学习。

#### 1. 变量
 js变量是松散类型的，也就是说可以保存任何类型的数据。

``` 
var message; 
//定义一个变量，该变量可以保存任何值，未经初始化的变量会保存为undefined

```

```
var message = 'hi'; 
//这样初始化的过程就是一个简单的赋值的过程，修改变量值的同时修改变量的类型。

message = 10; 
// 为message重新赋值，同时改变了message的数据类型。有效，但不推荐。

```

```
function test(){
    var message = 'hi';  //局部变量，这个变量在函数退出后就会被销毁。
}

test();
alert(message)// message is not defined;
```

```
function test(){
    message = 'hi'; //全局变量
    //省略了var操作符，message就变成了全局变量，
    //这样只要调用一次test()函数，这个变量就有了定义，就可以在函数外部的任何地方都能被访问到。
}
test();
alert(message) //hi
```
#### 2. 数据类型

5种基本数据类型：Undefined,Null,Boolean,Number,String
还有一种比较复杂的数据类型：Object

```
"object";// 这个值是对象或者null

undefined:typeof 对于未初始化或者未声明的值返回的都是undefined
null: typeof(null) == 'undefined'

Number
if(0.1+0.2 == 0.3){
    console.log('true') //不建议这样子做，因为会有浮点数计算问题
}

NaN:非数值，not a number
NaN 和任何数值都不想等，包括NaN 本身

Object的每个实例都具有以下的属性和方法：
1.Constructor: 保存用于创建当前对象的函数，new Object(),构造函数就是Object()
2.hasOwnProperty: 检查给定的属性在不在当前对象实例中。obj.hasOwnProperty('key')
3.propertyIsEnumerable:  检查给定的属性能否使用for-in语句来枚举
```

#### 3.函数
函数接收到的参数始终都是数组，而不关心数组中有哪些类型的参数。函数内可以通过arguments对象来访问这个数组，从而获取传递给函数的每一个参数。
arguments对象只是与数组类似，并不是Array的实例，只是能够通过arguments[n-1]来访问它的第n个元素，可以通过arguments.length来确定传递进来多少个参数。
arguments对象的长度是由传入的参数个数决定的

js函数没有重载，java中函数有重载，可以为一个函数编写两个签名，只要接受参数的类型和数量不一样即可。
``` 

```

    