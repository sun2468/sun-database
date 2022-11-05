---
type: 
uid: recTBexkNBWN0
vikaLink: https://vika.cn/workbench/dstpaAfExTHBNUNusm/viwvRoe0VMYoJ/recTBexkNBWN0
tags: 
 - git
 - Homebrew
aliases: 
 - Homebrew安装
---

# Homebrew安装（MacOS）

Homebrew官网：https://brew.sh/

终端输入以下命令：
```
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"

```

卸载Git老版本命令：
```
$ sudo mv /usr/bin/git /usr/bin/git-2.26.0
```

更新Git命令：
```
brew install git
```

## 三个区域

Git本地有三个工作区域：
- 工作目录（Working Directory）、
- 暂存区(Stage/Index)、
- 资源库(Repository或Git Directory)。
- 如果在加上远程的git仓库(Remote Directory)就可以分为四个工作区域。

- Workspace：工作区，就是你平时存放项目代码的地方
-   Index / Stage：暂存区，用于临时存放你的改动，事实上它只是一个文件，保存即将提交到文件列表信息
-   Repository：仓库区（或本地仓库），就是安全存放数据的位置，这里面有你提交到所有版本的数据。其中HEAD指向最新放入仓库的版本
-   Remote：远程仓库，托管代码的服务器，可以简单的认为是你项目组中的一台电脑用于远程数据交换

-   Directory：使用Git管理的一个目录，也就是一个仓库，包含我们的工作空间和Git的管理空间。
-   WorkSpace：需要通过Git进行版本控制的目录和文件，这些目录和文件组成了工作空间。
-   .git：存放Git管理信息的目录，初始化仓库的时候自动创建。
-   Index/Stage：暂存区，或者叫待提交更新区，在提交进入repo之前，我们可以把所有的更新放在暂存区。
-   Local Repo：本地仓库，一个存放在本地的版本库；HEAD会只是当前的开发分支（branch）。
-   Stash：隐藏，是一个工作状态保存栈，用于保存/恢复WorkSpace中的临时状态。

## 工作流程

git的工作流程一般是这样的：

１、在工作目录中添加、修改文件；

２、将需要进行版本管理的文件放入暂存区域；

３、将暂存区域的文件提交到git仓库。

因此，git管理的文件有三种状态：已修改（modified）,已暂存（staged）,已提交(committed)

## 牢记六个命令
git add.
git commit
git push
git pull
git reset  
git checkout

**Git文件操作**

## 文件的四种状态

版本控制就是对文件的版本控制，要对文件进行修改、提交等操作，首先要知道文件当前在什么状态，不然可能会提交了现在还不想提交的文件，或者要提交的文件没提交上。

-   Untracked: 未跟踪, 此文件在文件夹中, 但并没有加入到git库, 不参与版本控制. 通过git add 状态变为Staged.
    
-   Unmodify: 文件已经入库, 未修改, 即版本库中的文件快照内容与文件夹中完全一致. 这种类型的文件有两种去处, 如果它被修改, 而变为Modified. 如果使用git rm移出版本库, 则成为Untracked文件
    
-   Modified: 文件已修改, 仅仅是修改, 并没有进行其他的操作. 这个文件也有两个去处, 通过git add可进入暂存staged状态, 使用git checkout 则丢弃修改过, 返回到unmodify状态, 这个git checkout即从库中取出文件, 覆盖当前修改 !
    
-   Staged: 暂存状态. 执行git commit则将修改同步到库中, 这时库中的文件和本地文件又变为一致, 文件为Unmodify状态. 执行git reset HEAD filename取消暂存, 文件状态为Modified

## 查看文件状态

上面说文件有4种状态，通过如下命令可以查看到文件的状态：
```
#查看指定文件状态
git status [filename]
# 查看所有文件状态
git status

# git add .                  添加所有文件到暂存区
# git commit -m "消息内容"    提交暂存区中的内容到本地仓库 -m 提交信息
```


