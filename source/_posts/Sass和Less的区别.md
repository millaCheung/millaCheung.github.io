---
title: Sass和Less的区别
comment: true
date: 2020-04-22 16:25:56
tags: 
 - CSS
 - Less
 - Sass
---
## 1. Sass&Less是什么？
[Less](https://less.bootcss.com/)（Leaner Style Sheets 的缩写） 是一门向后兼容的 CSS 扩展语言

[Sass](https://www.sass.hk/)，作为“世界上最成熟、最稳定、最强大的专业级CSS扩展语言”

<!-- more -->

## 2. 两者异同
**相同之处:**

1、混入(Mixins)——class 中的 class；

2、参数混入——可以传递参数的 class，就像函数一样；

3、嵌套规则——class 中嵌套 class，从而减少重复的代码；

4、运算——CSS 中用上数学；

5、颜色功能——可以编辑颜色；

6、名字空间(namespace)——分组样式，从而可以被调用；

7、作用域——局部修改样式；

8、JavaScript 赋值——在 CSS 中使用 JavaScript 表达式赋值。

**不同之处:**

| 类别 | Sass                        | Less                                      |
| ---- | --------------------------- | ----------------------------------------- |
| 安装 | Sass 的安装需要安装 Ruby 环境 | Less 基于 JavaScript 需要引入 Less.js 来处理代码输出 css 到浏览器，也可以在开发环节使用 Less，然后编译成 css 文件，直接放在项目中 |
| 使用 | 复杂                        | 简单                                        |
| 功能 | 复杂                        | 简单                                         |
| 处理机制 | 通过服务端处理            | 通过客户端处理，解析相比 Sass 稍慢              |
| 变量 | 以 $ 开始                    | 以 @ 开始                                   |
| 文件后缀 | .sass 或 .scss             | .less                                      |

1、Less 在 JS 上运行，Sass 在 Ruby 上使用。

Sass 基于 Ruby，需要安装 Ruby。Less 和 Sass 在 Ruby 中构建相似，但它已被移植到 JavaScript 中。为了使用 LESS，我们可以将适用的 JavaScript 文件上载到服务器或通过脱机编译器编译 CSS 表。

2、编写变量的方式不同。

Sass 使用 $，而 Less 使用 @。

3、在 Less 中，仅允许循环数值。

在 Sass 中，我们可以遍历任何类型的数据。但在 Less 中，我们只能使用递归函数循环数值。

4、Sass 有 Compass，Less 有 Preboot

Sass 和 Less 有可用于集成 mixins 的扩展（在整个站点中存储和共享 CSS 声明的能力）。

Sass 有适用于 mixins 的 Compass，其中包括所有可用的选项以及未来支持的更新。

Less 有 Preboot.less，Less Mixins，Less Elements，gs 和 Frameless。Less 的软件支持比 Sass 更加分散，导致许多不同的扩展选项可能不会以相同的方式运行。对于项目，我们可能需要所有列出的扩展以获得与 Compass 类似的性能。
