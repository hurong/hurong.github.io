---
title: css3动画过渡等效果(学习记录)
date: 2017-05-15 09:25:41
tags:
categories: css3动画
---

css3过渡
=============

>学习了某个小知识点，过几天我这个小容量脑袋瓜子就又忘得一干二净了，写出来方便以后自己查找，当然也督促自己每天学习新东西，并养成记录的好习惯。加油！

*过渡效果是元素从一种样式转变成另一种样式，IE10以及以上支持，所以写的时候注意兼容性写法*

过渡属性
>参照runoob.com


| 属性           | 描述   |                                           
| :--------   | :-----  |                                          
| transition | 简写属性，用于在一个属性中设置四个过渡属性。|      
| transition-property  | 规定应用过渡的 CSS 属性的名称。|         
| transition-duration        | 定义过渡效果花费的时间。默认是 0。     | 
| transition-timing-function | 规定过渡效果的时间曲线。默认是 "ease"。|
|transition-delay |规定过渡效果何时开始。默认是 0。|

*例子*
```div{
    width:100px;
    height:100px;
    background:red;
    transition:width 2s;
    -webkit-transition:width 2s; /* Safari */
}
div:hover{
    width:300px;
}```