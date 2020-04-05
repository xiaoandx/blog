---
title: git pull 远程分支并与本地分支合并（包含错误解决）
date: 2020-03-24 15:35:65
tags: [git]
category: 报错总结
---

> 今天push代码时出现了commit冲突，无法提交本地代码？查看提交状态发现，本地提交代码与远程仓库代码不一致。下面将总结我的解决办法：

###  第一步：先将自己的代码保存在缓存库中

```
git add * 
```

```
git commit -m "本地最新代码"
```

### 第二步：pull取远程仓库最新代码（需要新分支来储存）

> 说明：pull拉取远程仓库代码将储存本地新建分支中（如dev分支）

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324154308.png)

```
git fetch test master:dev
```
> 命令说明

- origin 远程仓库别名（默认）我使用的git 自定义了远程仓库名（test）
 ```
git remote add test git@e.coding.net:xiaoandx-my/blog.git
 ```

-   master：远程仓库名称
-   dev：需要在本地新建的仓库名称



### 第三步：查看远程最新分支与本地最新分支的区别（查看修改部分）

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324155033.png)![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324155234.png)

```
git diff dev
```

> 命令说明

- `dev` 刚刚新建的分支

### 第四步：将远程最新分支与本地最新分支合并（用于修改在push）

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324155301.png)

```
git merge dev
```

> 命令说明：

- 将dev与本地当前分支合并
- 合并后会显示代码的修改情况，然后自己手动更新修改代码



### 注意：修改成功后保存代码源文件（如果git会出现下面这样的报错，白框）

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324155608.png)

只需要将目前最新的代码报错本地缓存空间中

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324155817.png)



### 第五步：提交最新代码到远程仓库

```
git push test master:master
```

> 代码说明

- test 远程仓库别名
- 第一个 master 本地代码分支
- 第二个master 远程仓库的分支

### 最后：如果有需要删除刚刚本地新建分支

![](https://gitee.com//xiaoandx_my/images/raw/master/img/20200324160712.png)

```
git branch -d dev
```

