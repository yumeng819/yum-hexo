---
title: es6之let&const
date: 2019-09-25
categories: 技术
tags: [教程]
comments: true
---

之前声明变量用 var 那为什么要有let 和 const呢?
### var的缺点
1、污染全局变量 
2、变量提升 （在未声明之前 会预先定义）
```
console.log(a)
var a = 1;
// undeined
```
3、可以被定义多次
4、不能声明常量
5、默认不会产生作用域

既然var有这些问题，let和const做了处理

### let的特性
1、不会污染全局变量（不再挂载到window）
2、不存在变量提升
3、同一个作用域下不可以重复定义
4、let+{}可以产生一个作用域,可以用它来解决异步循环的问题

```
let a = 1;
{
    console.log(a);
    let a = 2;  //暂存死区
}
// a is not defined
```
### const特性
声明一个只读的常量，只要变量不改变就用const


