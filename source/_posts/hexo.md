---
title: 小白级hexo+github搭建
date: 2019-08-12  
categories: 技术
tags: [教程]
comments: true
---
## 小白级hexo+github搭建
### 轻松拥有你的专属博客

> 第一步 你要拥有node和git

> 第二步 Github账户注册

> 第三部 我们就开始来使用hexo啦

```
npm run install hexo -g //安装hexo
hexo -v //检查是否成功
hexo init //初始化项目
npm install //安装组件
hexo g //生成静态文件
hexo s //开启服务
```
在浏览器输入http://localhost:4000/，看到以下页面你就成功了！


#### 接下来我们将Hexo与Github page联系起来


> 新建一个名为你的用户名.github.io的仓库

> 配置

- 首先，ssh key肯定要配置好。
- 其次，配置_config.yml中有关deploy的部分：


```
deploy:
  type: git 
  repo: git@github.com:yumeng819/yumeng819.github.io.git
  branch: master
```
- 输入hexo d就会将本次有改动的代码全部提交


> 网站访问地址就是 http://你的用户名.github.io 

> 绑定域名 在你的github项目新建一个名为CNAME的文件（无后缀），里面填写你的域名即可

#### 写博客

```
hexo new 'my-first-blog' 
```
hexo会帮我们在_posts下生成相关md文件<br>
打开这个文件就可以开始写博客了

---


##### 常见的hexo命令

```
hexo new "postName" #新建文章 缩写：hexo n
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录 缩写：hexo g
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server） 缩写：hexo s
hexo deploy #部署到GitHub 缩写：hexo d
hexo help  # 查看帮助
hexo version  #查看Hexo的版本
```
