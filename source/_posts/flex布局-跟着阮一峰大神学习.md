---
title: flex布局-跟着阮一峰大神学习
date: 2017-05-04 11:14:59
tags:
categories: css布局
---

flex布局
==========

Flex是Flexible Box的缩写，意为"弹性布局"，用来为盒状模型提供最大的灵活性。
任何一个容器都可以指定为Flex布局。
	```.box{
	display: flex;
	```}	

行内元素也可以使用Flex布局。
```.box{
  display: inline-flex;
```}

Webkit内核的浏览器，必须加上<span style="background: #7FFFD4">-webkit</span>前缀。
```.box{
  display: -webkit-flex; /* Safari */
  display: flex;
```}


