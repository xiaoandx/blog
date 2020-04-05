---
title: git退回指定版本（本地）
date: 20200403 10:32:03
tags: [git, reset]
categories: 实用工具
---

### 说明：

> 要退回指定版本需要知道对应版本的修订编码

### 

### 获取修订编码

1. 通过git log 获取commint 修订编码日志![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200403103601.png)

获得日志后可得到对应的修订版本号如：`665089975ba15e98fa2a674facc64c71ed55f685`

2. 通过远程仓库的提交历史获取修订版本号![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200403103804.png)

### 本地退回版本

> 注意：回退版本时需要注意分支，以免将其他分支回退了。

输入 git reset --hard <修订版本号>

```
git reset --hard <修订版本号>
```

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200403104103.png)

 

### 回退远程仓库

> 因为本地仓库已经版本回滚了，如果需要远程仓库的版本与本地一致比，需要强行push

```
git push -f -u origin master
```

注意：如果回退的指定分支需将`master` 修改对应分支如： `dev`



### 查看远程仓库是否一致

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200403104859.png)