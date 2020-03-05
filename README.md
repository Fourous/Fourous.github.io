博客搭建是基于Jekyll 

更多细节查看官网：[Jekyll](http://jekyllcn.com/)

博客源码基础修改自

 [ByBlog](https://github.com/qiubaiying/qiubaiying.github.io)

[nimo-markdown-cv](https://github.com/wodeni/nimo-markdown-cv)

### [查看博客戳这里 👆](http://qiubaiying.github.io)

如果觉得写得可以，麻烦点一点Star :wink::wink::wink::wink::wink:

#下面是正文

## 本地启动调试

### jekyll环境

在本地需要安装jekyll环境，jekyll环境依赖于Ruby，所以要先安装Ruby，这里使用MAC演示，Win也差不多，就是需要配置环境变量

```bash
brew install ruby #这里MAC应该自带了Ruby的，可以Ruby -V看一下
gem install jekyll bundler # 安装jekyll
jekyll new my-blog #这里使用jekyll创建一个模版和环境，如果直接拷贝这个项目改的话，直接省略这一步
bundle install # 安装需要的包，一般是通过gemfile来安装的，这里配置都在config.yml里面
bundle exec jekyll serve # 本地启动jekyll当然这里也可以直接使用jekyll serve来启动，注意当前路径
# 默认端口是4000，直接浏览器打开localhost：4000就可以本地预览，如果改动的话需要刷新浏览器
```



### 更改配置

主要配置文件都在_config.yml文件里面，直接修改文件基本就行

``` bash
title: Fourous # 网站名称，这个会出现在浏览器的URL里面
SEOTitle: fourous # 和搜索有关的名称
header-img: img/home-bg.jpg # 主页图片
email: fourousky@gmail.com # 右边bar的邮箱名称
description: "C’est la vie." # 网站描述
keyword: "github,fourous,java,设计模式,skyWalking,grafana" # 搜索时候出现关键字
url: "http://Fourous.github.io"          # 你的访问网站连接
baseurl: ""      # for example, '/blog' if your blog hosted on 'host/blog'
github_repo: "https://github.com/Fourous/Fouorus.github.io.git" # you code repository
```

如果不知道怎么搭建GitHub Page的可以看官方博文 :fist_right:[关于 GitHub Pages](https://help.github.com/cn/github/working-with-github-pages/about-github-pages)

### 撰写博文

目前改装的代码里面嵌入了feature功能，所以在写文章时候需要加入一些触发代码，来进行标识

目前每一篇markdown里面加入如下

```
---
layout:     post
title:      Spring和SpringMVC区别
subtitle:   Spring和SpringMVC
date:       2019-12-13
author:     Fourous
header-img: img/home.jpg
catalog: 	 true
tags:
    - Spring
    - java
```

可以试一试，很容易摸清楚

### 侧边栏

对于侧边栏也就是网页右边的个人介绍以及图片等等，代码里面体现就是sideBar配置也在_config.yml里面

配置如下：

```bash
# Sidebar settings
sidebar: true                           # 是否开启sidebar功能
sidebar-about-description: "成功不必在我，而功力不必唐捐"
sidebar-avatar: /img/avatar.png      # 这里相对路径只想文件夹/img
```

### 评论功能

评论功能主要是基于GitTalk做的，你评论内容都在GitHub也就是你自己的GitHub repo里面

配置也是在_config.yml里面

```bash
gitalk:
  enable: true    #是否开启Gitalk评论
  clientID: e0cd032**e0837d***                            #生成的clientID
  clientSecret: 94fa8c0***f4b780e0d69ba3a750a2e****   #生成的clientSecret
  repo: Fourous.github.io    #仓库名称
  owner: Fourous    #github用户名
  admin: Fourous
  distractionFreeMode: true #是否启用类似FB的阴影遮罩

```

如果不知道gitTalk的，可以看一下这几个博文

[Gitalk 是一个基于 GitHub Issue 和 Preact 开发的评论插件](https://github.com/gitalk/gitalk/blob/master/readme-cn.md)

[个人博客评论插件之gittalk](https://juejin.im/post/5d7734b5518825680e34cabf)

### 简历排版

单纯的Markdown写出来的建立很难排版得像Word一样，用Latex又过于繁杂了，所以目前一般这种拍版都是基于MarkDown和CSS做的

参考博文

[Markdown 适合写个人简历吗？ - 尼莫的回答 - 知乎]( https://www.zhihu.com/question/20546890/answer/323888961)

在GitHub上，也是使用基于jekyll开源做的排版引擎

## 更改博客

要再更改得更加完美点，需要更加细致改动

### 编译流程

详细涉及的技术栈较多，不赘述过多，首先Jekyll是基于Markdown做的排版，然后将你在_post文件夹里面的markdown文字排成Html文件生成到 _site文件夹，这里不单单会组装当前的Markdown，也会将你定义的Title和foot等HTML组装进去，相当于复用了一部分代码，每次写的博文都会自动加工成一个复合页面，当然，这里也会导致每次加载时候很慢

### 复用文件夹

主要复用文件夹都在 _layout和 _include里面，存放着页面顶端的样式例如Head.html nav.html ，简历排版样式在CSS文件夹，引入了BootStrap样式表，更加美观，还有字体在font文件夹里面，

所以我们如果需要改动title样式，使上面的切换每一个页面改变应该到这两个文件夹里面更改

## 致谢

* 博客框架：[Hux](https://github.com/Huxpro/huxpro.github.io)  [nimo-markdown-cv](https://github.com/wodeni/nimo-markdown-cv)

* 感谢 Jekyll、Github Pages 和 Bootstrap!

* Markdown [emoji](https://www.webfx.com/tools/emoji-cheat-sheet/)

