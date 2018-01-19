---
title: 重温js
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
```
    