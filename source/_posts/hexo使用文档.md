---
title: hexo使用文档
top: false
cover: false
toc: true
mathjax: true
date: 2020-04-15 19:01:12
password:
summary:
tags:
categories:
---

##  首次启动
* 首先把 项目 clone 到本地
* 安装nodejs，建议你直接官网下载最新的编译器，[NodeJS](https://nodejs.org/zh-cn/)
* 检查下版本， 以下为最新版本
```
  $ node --version
  v12.14.1
  
  $ npm -v          
  6.13.4
```

* 安装 hexo , [官网](https://hexo.io/zh-cn/)
```
  # 进入项目目录
  cd blog_dir 

  $ npm install hexo-cli -g
 
  # 如果出错要卸载
  $ npm uninstall hexo-cli -g

  # 安装剩余包
  $ npm install
```

* 安装好之后，执行 `hexo server`  就能跑起来了


## 常见操作

### 1. 写一篇新的

[官方教程](https://hexo.io/zh-cn/docs/writing)，在命令行执行

*  `hexo new post 炒菜-技术教程`

如果你不是一气呵成的话，可以先新建一片草稿（不会在页面上显示）

* `hexo new draft 炒菜-技术教程-草稿版`

<!-- more -->

### 2. 添加一个分类 

在标题部分添加 categories 和 tags

入下图所示

{% asset_img 01_markdown.jpg md %}

则会在对应的页面上产生效果，分别显示为分类和标签

{% asset_img 02_web.jpg web %}


### 3. 上传图片 or 资源(非常重要)
1. 通过步骤1会在 _posts 下面建立对应的文件夹, 比如 建立 "博客.md", 则会出现 "博客" 对一个的文件夹
2. 将资源放在新建的对应的资源文件夹中, 例如 A.jpg，具体关系如下图所示
 
 {% asset_img 3-show.jpg web %}

3. 引用资源的时候，切记不能使用markdown 中的 ![]()

4. 使用资源的时候，参考，[语法](https://hexo.io/zh-cn/docs/asset-folders.html)

```
{% asset_path slug %}
{% asset_img slug [title] %}
{% asset_link slug [title] %}

# 那么在 步骤1的 博客.md 中想展示图片则需要写
# 非常坑，切记不能乱放位置，而且只能用这个语法才能显示图片
{% asset_img A.jpg A图片 %}


```





## FAQ

*  Q: 启动的时候可能看到，`Error: Cannot find module './build/Debug/DTraceProviderBindings'` 
   
     A: 不用管，能够正常使用


*  Q: 我写的文章直接能往master 上推送吗？
 
   A: 理论上咱们是不限制的，但是最好能够在自己分支上改差不多了，再向master提交


