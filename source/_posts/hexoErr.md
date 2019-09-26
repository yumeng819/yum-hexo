---
title: hexo踩过的坑
date: 2019-09-26 
categories: 技术
tags: [hexo]
comments: true
---

### 1.hexo在本地修改的nexT主题后，无法push到Github

![image](/img/next.png)

提出问题：无法提交某个子文件夹下的文件
解决方法：
删掉子文件夹下的.git目录（themes/next下的.git目录）
```
git rm --cached next
git add next // next为子文件的路径
```
然后正常提交即可成功，亲测有效
