# Git笔记

## git基本知识

### 1. git关键字解释

```
HEAD 当前版本的指针，当切换本地版本的时候会快速指向指定版本文件
master git为我们创建主分支，在github上改成main（git branch -M main）
origin 远程仓库的名称
```

### 2. git基本逻辑

包括四个部分：工作区、暂存区、本地仓库和远程仓库（最牛逼的是github）

<img src="/Users/wmx/Library/Application Support/typora-user-images/image-20221204164141344.png" alt="image-20221204164141344" style="zoom:50%;" />

来源（https://blog.csdn.net/qq_42363495/article/details/104878170）

### 3. 常用命令

```
git init 在当前目录新建一个仓库
git status [文件名] 查看指定文件状态
git status 查看所有文件状态
git add [file-name1] [file-name2] ... 从工作区添加指定文件到暂存区
git add . 将工作区的被修改的文件和新增的文件提交到暂存区，不包括被删除的文件
git add -A . A指all，将工作区被修改、被删除、新增的文件都提交到暂存区
git commit -m [版本名] 将暂存区所有文件添加到本地仓库
git commit [file-name-1] [file-name-2] -m [版本名] 将暂存区指定文件添加到本地仓库
git commit -am [版本名] 将工作区的内容直接加入本地仓库（a就是add）
git log 显示所有commit日志
git reflog 显示操作本地版本库的命令，包括commit和reset等，在回退版本以后又后悔找不到commit id了可以使用此命令查看历史
git push 将文件添加到远程仓库
git push -f 强制提交，当我们本地reset到旧的版本时，然后普通push会被拦截，因为此是本地HEAD指向比远程库还要旧
git push origin [branch-name] 推送当前本地分支到指定远程分支
```

插入一个mac电脑的小毛病，外接硬盘会出现很多._的文件，版本控制的时候会识别，所以更新完工作区之后，输入如下命令：

```
find . -name "._*"  | xargs rm -f
```



