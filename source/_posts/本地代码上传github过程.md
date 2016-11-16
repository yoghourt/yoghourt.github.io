---
title: 本地代码上传github过程
date: 2016-03-28 14:10:21
tags: git
---
> github是一个很不错的代码托管网站，利用它可以托管自己的项目，还可以搭建个人博客，实乃各类小猿必备利器。
那么如何将本地代码上传到github上呢？

<!---more--->

1. 创建本地创库
```
	$ git init
```
2. 添加文件
```
	$ git add *
```
3. 提交文件
```
	$ git commit -m 'message xxx'
```
4. 添加github远程代码库
```
	$ git remote add origin https://xxx.git
```
5. 推送代码
```
	$ git push origin gh-pages
```
- - -
###### git命令补充
* 查看分支
```
	$ git branch
```
* 切换分支
```
	$ git checkout target-branch
```
* 删除远程仓库
```
	$ git remote rm XXX.git
```
* *查看当前状态*
```
	$ git status
```