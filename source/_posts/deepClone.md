---
title: 实现一个简单的深拷贝
date: 2019-09-27
categories: 技术
tags: [es6]
comments: true
---
## 实现一个简单的深拷贝
那什么是深拷贝呢？什么是浅拷贝呢？
### 浅拷贝 拷贝的是引用地址 

```Javascript
let arr = [1,2,3,[4]];
let newArr = arr.slice(3);
newArr[0][0] = 10;// 改变newArr的值，arr也会改变，即slice是浅拷贝
console.log(arr) // [ 1, 2, 3, [ 10 ] ]

```
### 深拷贝 拷贝地址中的内容 

```Javascript
// 实现一个简单的深拷贝
// 拷贝对象（函数一般不拷贝）
function deepClone(obj,hash = new WeakMap()){
    // 类型判断
    //null == undefined
    if (obj == undefined) return obj;
    // string number boolean symbol
    if (typeof obj !== 'Object') return obj;
    // 正则 日期 
    if(obj instanceof RegExp) return new RegExp(obj);
    if(obj instanceof Date) return new Date(obj);
    // [] {}
    let val = hash.get(obj);
    if(val){
        return val
    }
    let cloneObj = new obj.constructor; //取当前传入对象的构造函数
    for(let key in obj){
        if(obj.hasOwnProperty(key)){ //实例上的属性
            cloneObj[key] = deepClone(obj[key],hash)
        }
    }
    return cloneObj;
}

let arr = [1,2,3,[4]];
let newArr = deepClone(arr)
newArr[3][0] = 100;
console.log(arr) //[ 1, 2, 3, [ 4 ] ]
console.log(newArr) //[ 1, 2, 3, [ 100 ] ]

let obj = {a:1};
obj.b = obj;
console.log(deepClone(obj)); //{ a: 1, b: [Circular] }

```