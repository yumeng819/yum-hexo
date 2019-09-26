---
title: 实现一个简单的深拷贝
date: 2019-09-26
categories: 技术
tags: [教程]
comments: true
---
## 实现一个简单的深拷贝
那什么是深拷贝呢？什么是浅拷贝呢？
浅拷贝 拷贝的是引用地址 

```
let arr = [1,2,3,[4]];
let newArr = arr.slice(3);
newArr[0][0] = 10;// 改变newArr的值，arr也会改变，即slice是浅拷贝
console.log(arr) // [ 1, 2, 3, [ 10 ] ]

```
深拷贝 拷贝地址中的内容 