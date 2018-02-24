---
title: 重温js——变量、作用域和内存问题
date: 2018-01-22 10:06:49
tags:
---
1. 基本类型与引用类型
    基本类型：简单的数据段
    引用类型：可能由多个值构成的对象，是保存在内存中的对象。

2. 对于引用类型的值，我们可以为其添加属性和方法，也可以改变和删除其属性和方法。

    ```
    var person = new Object();
    person.name = 'maolin.yang';
    console.log(person.name); //maolin.yang

    //但是不能给基本类型的值添加属性，尽管不会导致任何报错。
    var name = 'maolin.yang';
    name.age = 25;
    console.log(name.age) //undefined

    //故只能给引用类型的值动态的添加属性
    ```
3. 复制变量值
    ```
    var num1 = 5;
    var num2 = num1;

    console.log(num2) //5,num1,num2相互独立

    var obj1 = new Object();
    var obj2 = obj1;
    obj2.name = 'maolin.yang';

    console.log(obj1.name)//maolin.yang
    //obj1,obj2指向同一对象，因此改变一个变量，就会影响另一变量的值
    ```

4. 传递参数
    ```
    function setName(obj){
        obj.name = 'maolin.yang';
        obj = new Object();
        obj.name = 'maolin';
    }
    var obj={};
    setName(obj);
    obj.name;// maolin.yang

    //函数内部修改参数值，原始的引用仍然未改变。
    ```
4. 变量检测
    要检测变量是不是基本数据类型，是数值，字符串，布尔还是undefined，`typeof`是个不错的选择，但是对于对象和null，typeof都会返回oject
    判断是不是引用类型的实例，`instanceof`是个不错的选择
    ```
    console.log(obj instanceof Object); //obj是Object嘛
    console.log(obj instanceof Array); //obj是Array嘛
    console.log(obj instanceof RegExp); //obj是Object嘛
    ```
    所有引用类型的值都是Object的实例，在检测引用类型值和构造函数时，instanceof始终返回true，
    用instanceof 检测基本数据类型值时，始终返回false，因为基本数据类型值不是对象。

5. 执行环境与作用域
    执行环境
    作用域链，是为了保证对执行环境有权访问的所有变量和函数的有效访问。
    全局变量
    局域变量
    
6. 没有块级作用域

    ```
    if(true){
        var color = 'red';
    }
    console.log(color);// red

    //其他语言中，color会在if语句执行完之后将其销毁
    ```
    



