---
layout: post
title: "github pages 域名切换为主机域名"
---

首先要感谢James Dennes (GitHub Staff)为我解答了这个问题。

这是他回复的邮件：

Hi there,

You need to convert your project page to a user page:
<h3>Rename your blog repository to xpi.github.io</h3>
<h3>Move the content into the master branch</h3>
Your site will then be a user page, served at http://xpi.github.io.

Thanks,
James

简单明了，把git库命名为主机名，把gh-pages分支下的东西移到master，然后等个几分钟就能从xpi.github.io登录了。

