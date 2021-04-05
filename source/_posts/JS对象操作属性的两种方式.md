---
title: JS对象操作属性的两种方式
comment: true
date: 2019-10-20 18:11:14
tags:
 - JavaScript
---
## 在 JS 对象中，调用属性一般有两种方法——点和中括号的方法。
**1.使用点方法**

```javascript
var obj = {
    name: "cedric"
}

console.log(obj.name);  // cedric
```

<!-- more -->

**2.使用 [ ] 方法**

```javascript
var obj = {
    name: "cedric"
}

console.log(obj["name"]);  // cedric
```
- 点方法是在对象名后面跟上属性名，而中括号方法里的索引存放的与属性名字相同的字符串。

####	二者区别

 1. 点方法后面跟的必须是一个指定的属性名称，而中括号方法里面可以是变量。例如

```javascript
var obj = {
    name: "cedric"
}

var haha = "name";

console.log(obj.haha);  // undefined
console.log(obj[haha]);  // cedric
```

 2. 中括号方法里面的属性名可以是数字，而点方法后面的属性名不可以是数字
 3. 当动态为对象添加属性时，必须使用 中括号 []， 不可以用点方法
