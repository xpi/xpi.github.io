---
layout: post
title: 两分钟建立一个github页面
description: github页面初衷是用于作为repo的页面文档 
---
<h3>首先有一个github帐号</h3>
<br>
<h3>新建一个repo</h3>
<br>
<h3>在本地建立一个与repo同名的文件夹</h3>
<br>
<p>
xpi$ cd blog
<br>
xpi$ git init

<br>
xpi$ echo "hello xpi" > index.html

<br>
xpi$ git add .

<br>
xpi$ git commit -m "first commit"

<br>
xpi$ git remote add origin https://github.com/xpi/blog.git

<br>
##xpi$ git push origin gh-pages
</p>
