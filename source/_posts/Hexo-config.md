---
title: Hexo config
date: 2022-04-15 23:07:30
categories:
- 博客
tags: 
- 博客
- hexo
---

## 1.主配置文件

### 1._config.yml 

~~~ yaml
# Site 主题
title: Pltukz's blog
subtitle: Keep thinking
description: It's never too late to learn.
keywords:
author: Kens
language: zh-CN
timezone:

~~~

​	<!-- more -->

```yaml
   # Deployment
   ## Docs: https://hexo.io/docs/one-command-deployment
   deploy:
     type: git  
     repo: https://github.com/pltukz/pltukz.github.io.git
     #repo: https://gitee.com/pltukz/pltukz.git
     branch: master
```

~~~ yaml
# 这一段默认就有的
index_generator:
  path: ''
  per_page: 5
  order_by: -date

# 归档页面
archive_generator:
  per_page: 50
  yearly: true
  monthly: true
————————————————
版权声明：本文为CSDN博主「小镇攻城狮」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/awt_fudonglai/article/details/107435089
~~~



### 2.source 文件夹

​       _posts文件夹放文档

​	   _data 放css和js

​				footer放js

​				styles放css

​	 其他放一点themes中不能git上去但是需要修改的文件

## 2.themes next 文件

### 1._config.yml

1. 开放一些自定义文件，放在blog的source文件夹内启动

~~~ yaml
# Define custom file paths.
# Create your custom files in site directory `source/_data` and uncomment needed files below.
custom_file_path:
  #head: source/_data/head.njk
  #header: source/_data/header.njk
  #sidebar: source/_data/sidebar.njk
  #postMeta: source/_data/post-meta.njk
  #postBodyEnd: source/_data/post-body-end.njk
  #footer: source/_data/footer.njk
  footer: source/_data/footer.swig
  #bodyEnd: source/_data/body-end.njk
  #variable: source/_data/variables.styl
  #mixin: source/_data/mixins.styl
  style: source/_data/styles.styl
~~~

2. 设置主题

~~~ yaml
# Schemes
#scheme: Muse
#scheme: Mist
scheme: Pisces
#scheme: Gemini
~~~

3. 设置左边菜单栏

~~~ yaml
# External url should start with http:// or https://
menu:
  home: / || fa fa-home
  about: /about/ || fa fa-user
  tags: /tags/ || fa fa-tags
  categories: /categories/ || fa fa-th
  archives: /archives/ || fa fa-archive
  #schedule: /schedule/ || fa fa-calendar
  #sitemap: /sitemap.xml || fa fa-sitemap
  #commonweal: /404/ || fa fa-heartbeat
~~~

4. 设置页脚

``` yaml
# Powered by Hexo & NexT
  powered: false
```

5. 设置文字样式

``` yaml
font:
  enable: true

  # Uri of fonts host, e.g. https://fonts.googleapis.com (Default).
  host:

  # Font options:
  # `external: true` will load this font family from `host` above.
  # `family: Times New Roman`. Without any quotes.
  # `size: x.x`. Use `em` as unit. Default: 1 (16px)

  # Global font settings used for all elements inside <body>.
  global:
    external: true
    family: Noto Serif SC
    size: 

  # Font settings for site title (.site-title).
  title:
    external: true
    family:
    size: 2

  # Font settings for headlines (<h1> to <h6>).
  headings:
    external: true
    family:
    size:

  # Font settings for posts (.post-body).
  posts:
    external: true
    family:

  # Font settings for <code> and code blocks.
  codes:
    external: true
    family:

```



### 2.languages

配置一些文案，可以用find+grep反查引用文档，更快熟悉整体页面构成



### 3.layput/archive.njk

里面放了“归档”中，文章数量不同而导致的提示语不同代码

比如我只有两篇文章，则会提示“嗯。。继续加油”



### 4.source/js

可以放之前开放中引用的具体js脚本



### 5.source/css

_common/components/post 下的post-fotter.styl可以注释

.post-eof 把文章间隔去除
