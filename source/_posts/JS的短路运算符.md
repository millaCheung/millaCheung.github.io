---
title: 'JS的短路运算符'
date: 2019-12-13 16:00:52
tags:
 - JavaScript
comment: true 
---
## JS的短路运算符
在JS函数中我们经常会使用到短路运算符，主要是逻辑与（&&） 和 逻辑或（||）。

<!-- more -->

#### 1. 逻辑与 && 的运算方式

```javascript
var a = 3 && 5;
console.log(a);  //返回的结果为 5
```
如果逻辑与运算符左边的值布尔转换后为true，那么返回右边的值（不管右边的值是真还是假）。
```javascript
var a = false && 5;
console.log(a);  //返回的结果为 false

var a = null && 5;
console.log(a);  //返回的结果为 null
```
如果逻辑与运算符左边的值布尔转换后为false，那么返回左边的值，但是当逻辑与的左边为 null/NaN/undefined ，结果就会得到null/NaN/undefined。 
#### 2. 逻辑或 || 的运算方式
```javascript
var a = false || 5;
console.log(a); //返回的结果为 5
```
如果逻辑或运算符左边的值布尔转换后为false，那么返回右边的值（不管右边的值是真还是假）。
```javascript
var a = true || 5;
console.log(a); //返回的结果为 true

var a = null || null;
console.log(a); //返回的结果为 null
```
如果逻辑或运算符左边的值布尔转换后为true，那么返回左边的值，如果两个操作数都是是null/NaN/undefined，返回null/NaN/undefined。
