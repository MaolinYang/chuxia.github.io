---
title: css
date: 2018-02-09 16:27:02
tags:
---
#### css 布局
1. display属性
    a. block
    b. none,常会联系到visibility
    c. inline-block
    d. list-item,table,flex

2. margin:auto
    margin:0 auto;实现水平居中

3. max-width
    处理浏览器小窗口情况，所有主流浏览器，包括IE7+在内都支持

4. 合模型
    元素的边框和内边距不包括在width内，
    box-sizing:content-box;设置之后元素的内边距和边框不会增加它的宽度，支持IE8+

    box-sizing:border-box;

    ```
        * {
    -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
            box-sizing: border-box;
    }
    ```

5. position
    static: 默认值，不会被特殊的定位
    relative: 相对定位，添加top,right,bottom,left属性之后会偏离其正常位置，其他元素的位置不会受到该元素的影响发生位置改变来弥补偏离后的间隙。

    fixed:固定定位，相对于窗口的定位，意味着即便页面滚动，它还是会留在相同的位置。使用固定定位后，不会保留在页面中原有的位置，————脱离文档流
    
    absolute:绝对定位，相对于最近的“positioned”祖先元素，如果没有“positioned”祖先元素，那么它是相对于文档的 body 元素，并且它会随着页面滚动而移动。

6. float
    可用于实现文字环绕图片

7. clear
    被用于控制浮动
    clear:left,清除左浮动
    clear:right,清除右浮动
    clear:both,清除左右浮动

8. 清除浮动
    解决方案：https://stackoverflow.com/questions/211383/what-methods-of-clearfix-can-i-use
    ```
        overflow:auto;
        zoom:1; // 支持IE6

        .container::after {
            content: "";
            display: block;
            clear: both;
        }
    ```

9. inline-block布局
    vertical-align属性会影响到inline-block元素
    
二、css基础
    1. css选择器（基础选择器，复杂选择器）
        标签选择器
        类选择器
        ID选择器

    2. html中引入css的方法
    ```
        行内式：
            <p style="color:red"></p>

        内嵌式：
            <head>
                <style>
                    p{font-size:14px;}
                </style>
            </head>

        外部引入式：
            @import url('reset.css')

        链接式：
            <link href="./reset.css" type="text/css" rel="stylesheet">
    ```
        内嵌式
        外部引入 
    3. css继承特性，层叠特性
    