---
title: 纯CSS实现水平轮播效果
comment: true
date: 2019-04-19 18:15:45
tags:
 - CSS
---
以下为只使用CSS实现水平轮播效果代码。

<!-- more -->

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title></title>
		<style type="text/css">
			* {
				margin: 0;
				padding: 0;
			}
			
			#list {
				width: 5464px;
				height: 768px;
				
			}
			
			#box {
				position: relative;
				width: 1366px;
				height: 768px;
				border: 1px solid #000000;
			}
			
			#list img {
				float: left;
				
			}
			
			#btn {
				position: absolute;
				right: 10px;
				bottom: 15px;
			}
			
			#btn a {
				float: left;
				width: 30px;
				height: 30px;
				border: 1px solid #000000;
				margin-right: 5px;
				text-align: center;
				line-height: 30px;
				text-decoration: none;
				background: rgba(0, 0, 0, .5);
				color: white;
			}
			
			#btn a:hover {
				background: #000000;
			}
			
			#box2 {
				width: 1366px;
				height: 768px;
				overflow: hidden;
			}
		</style>
	</head>
	<body>
		<div id="box">
			<div id="btn">
				<a href="#img1">1</a>
				<a href="#img2">2</a>
				<a href="#img3">3</a>
				<a href="#img4">4</a>
			</div>
			<div id="box2">
				<div id="list">
					<img id="img1" src="./imgs/img (1).jpg" />
					<img id="img2" src="./imgs/img (2).jpg" />
					<img id="img3" src="./imgs/img (3).jpg" />
					<img id="img4" src="./imgs/img (4).jpg" />
				</div>
			</div>
		</div>
		
	</body>
</html>
```
![代码内图片](https://img-blog.csdnimg.cn/20191106172151639.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ptMTY0MDExMTMwOA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191106172253788.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ptMTY0MDExMTMwOA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191106172308897.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ptMTY0MDExMTMwOA==,size_16,color_FFFFFF,t_70)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191106172323442.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3ptMTY0MDExMTMwOA==,size_16,color_FFFFFF,t_70)
图片若有侵权，请联系进行删除。
