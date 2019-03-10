---
title: "MySQL Pretty Print in Command Line"
date: 2019-03-10T18:16:43+08:00
author: "hp.huang"
draft: false
categories: [database]
tags: [mysql,sql]
---

# Introduction

By default, the output of mysql in the console may be ugly when the screen is too small or the count of fields are large in the table. see the figure.

![prettify_unformat](/images/mysql/prettify_unformat.jpg)

There are 2 alternative to prettify the output in the console.

## 1. Display Records Vertically

use `\G` option rather than `;`. 

```
SELECL * FROM user\G
```

![prettify_slash_g](/images/mysql/prettify_slash_g.jpg)

## 2. Using Pager

```
pager less -SFX
SELECL * FROM user;
```
![prettify_pager](/images/mysql/prettify_pager.jpg)

**Advanced**

Mysql provides [user-specifc options file](https://dev.mysql.com/doc/refman/5.5/en/option-files.html) which allows mysql client read user's default configuration when connecting to mysql server. 

The location of config file is at `~/.my.cnf`. 

Here is an example:
```
[client]
pager='less -SFX'
```

* -S: Single line, don't skip line when line is wider than screen, instead allow to scroll to the right.
* -F: Quit if one screen, if content doesn't need scrolling then just send to stdout.
* -X: No init, disables any output "less" might have configured to output every time it loads.
