---
title: CSS实现单行和多行文本溢出，省略号显示
comment: true
date: 2020-04-23 13:03:11
tags:
 - CSS
---
### 1. 单行文本溢出，省略号显示

**实现代码：**

```css
overflow: hidden;
text-overflow:ellipsis;
white-space: nowrap;
```

<!-- more -->

**示例代码：**

```html
<head>
  ...
  <style>
    div {
      width: 150px;
      border: 1px solid #ddd;
      overflow: hidden;
      text-overflow:ellipsis;
      white-space: nowrap;
    }
  </style>
</head>
<div>
  单行文本溢出，省略号显示
</div>
</body>
```

**效果图：**

![单行文本溢出](https://img-blog.csdnimg.cn/20200410171817714.png)

### 2. 多行文本溢出，省略号显示

- 方式1：

**实现代码：**

```css
display: -webkit-box;
-webkit-box-orient: vertical;
-webkit-line-clamp: 2;
overflow: hidden;
```

**示例代码：**

```html
<head>
  ...
  <style>
    div {
      width: 150px;
      height: 44px;
      border: 1px solid #ddd;
      display: -webkit-box;
      -webkit-box-orient: vertical;
      -webkit-line-clamp: 2;
      overflow: hidden;
    }
  </style>
</head>
<div>
    多行文本溢出，省略号显示；多行文本溢出，省略号显示
</div>
</body>
```

**效果图：**

![多行文本溢出](https://img-blog.csdnimg.cn/20200410172408997.png)

**适用范围：**

因其使用了 WebKit 的 CSS 扩展属性，该方法适用于 WebKit 浏览器及移动端

**注释：**

 1. `-webkit-line-clamp` 用来限制在一个块元素显示的文本的行数。 为了实现该效果，它需要组合其他的 WebKit 属性。常见结合属性：
 2. `display: -webkit-box` 必须结合的属性，将对象作为弹性伸缩盒子模型显示 。
 3. `-webkit-box-orient` 必须结合的属性，设置或检索伸缩盒对象的子元素的排列方式 。

- 方式2：

**实现代码：**

```css
div {
  position: relative;
  line-height: 20px;
  max-height: 40px;
  overflow: hidden;
}
div::after{
  content: "...";
  position: absolute;
  bottom: 0;
  right: 0;
  padding-left: 40px;
  padding-right: 5px;
  background: -webkit-linear-gradient(left, transparent, #fff 65%);
  background: -o-linear-gradient(right, transparent, #fff 65%);
  background: -moz-linear-gradient(right, transparent, #fff 65%);
  background: linear-gradient(to right, transparent, #fff 65%);
}
```

**示例代码：**

```html
<head>
  ...
  <style>
    div {
      position: relative;
      width: 150px;
      border: 1px solid #ddd;
      line-height: 20px;
      max-height: 40px;
      overflow: hidden;
    }
    div::after{
      content: "...";
      position: absolute;
      bottom: 0;
      right: 0;
      padding-left: 40px;
      padding-right: 5px;
      background: -webkit-linear-gradient(left, transparent, #fff 65%);
      background: -o-linear-gradient(right, transparent, #fff 65%);
      background: -moz-linear-gradient(right, transparent, #fff 65%);
      background: linear-gradient(to right, transparent, #fff 65%);
    }
  </style>
</head>
<body>
<div>
  多行文本溢出，省略号显示；多行文本溢出，省略号显示
</div>
</body>
```

**效果图：**

![多行文本溢出](https://img-blog.csdnimg.cn/20200410174055864.png)

**适用范围：**

适用范围广，可结合 js 进行优化

**注释：**

 1. 将 height 设置为 `line-height` 的整数倍，防止超出的文字露出。
 2. 给 `div::after` 添加渐变背景可避免文字只显示一半。
 3. 由于 IE6-7 不显示 `content` 内容，所以要添加标签兼容 ie6-7（如：`<span>…<span/>`）；兼容 IE8 需要将 `::after` 替换成 `:after` 。
