# Git 常用命令
```shell
git 
```
# Github 大纲
- Git 简介
- Git 是什么
	- Git的诞生
	- 集中式 VS 分布式版本控制系统
- 安装 Git
- 创建版本库
- 时光机穿梭
	- 版本回退
	- 工作区和暂存区
	- 管理修改
	- 撤销修改
	- 删除文件
- 远程仓库
	- 添加远程库
	- 从远程库克隆
- 分支管理
	- 创建和合并分支
	- 解决冲突
	- 分支管理策略
	- Bug分支
	- Feature分支
	- 多人协作
	- Rebase
- 标签管理
	- 创建标签
	- 操作标签
- 使用 Github
- 自定义 Git
	- 忽略配置文件
	- 配置别名
	- 搭建 Git 服务器
# Question
## Q1: 如何安装 Git ?
Git 是世界上最先进的分布式版本控制系统 VCS (Version Control System) ,Git 一开始是在 Linux 上开发的, 很长的一段时间里面, Git 只能在 Linux 和 Unix 系统上运行, 不过现在我们可以在Windows、MacOS、Linux 这三种操作系统使用 Git, 但是三种系统上安装 Git 方式不一样
- Mac 用户: [[如何在 Mac 上安装 Git]]
- Window 用户: [[如何在Window上安装Git]]
- Linux 用户: [[如何在Linux上安装Git]]
## Q2: 那么接下来, 如何创建一个版本库 ?
首先创建一个文件夹📁
创建一个版本库 `mkdir learn_git`
```zsh
mkdir learn_git // 创建一个新的文件夹/目录叫做 learn_git
cd learn_git // 切换到 learn_git 文件夹
pwd // 显示当前所在的目录
```

```zsh
mv 源地址 目的地址 // 可以移动之前创建的目录,到你想要的目录当中
mv /usr/用户名/learn_git /usr/用户名/Developer
```

使用 `git init` 把这个仓库变成一个 git 可以管理的仓库

把文件添加到版本库当中
```zsh
git touch readme.txt
git add readme.txt
git commit -m "wrote a readme file"
```

## 使用Git 实现时光机穿梭
### Q1:我想要回退到上一个版本, 如何实现?
```zsh
git log
git log --pretty=oneline

git reset --hard HEAD^ // 回退到上一个版本
git reset --hard HEAD^^ //会退到上上个版本
git reset --hard commit_id // 回退到特定版本
git reflog // 查看命令历史,可以看到每个版本的 commit_id 便于回退
```
### Q2: 暂存区和工作区有什么区别?
### Q3: Git 跟踪并管理的东西是什么?
git 跟踪并管理的东西是修改而不是文件
修改-> `git add` ->到暂存区-> `git commit` ->到主分支
```zsh
git status 
git diff HEAD --file // 查看工作区和版本库的最新版本的区别
```

### Q4: 如何撤销我对文件的修改?
场景 1 : 修改了工作区的某个文件的内容, 想直接丢弃工作区的修改 `git checkout -- file`
场景 2:  修改了工作区的文件, 然后使用 `git add` 添加到了暂存区, 想要丢弃修改
第一步: 使用命令 `git reset HEAD <file>`, 然后使用场景 1 中的 `git checkout -- file` 丢弃工作区的修改
场景 3: 提交了不合适的修改到版本库, 想要撤销本次修改, 使用版本会退 ( 5.1 版本回退)
### Q5:如何在 Git 版本库中删除一个文件
`rm file`
`git rm file`
`git checkout -- file` 能够把版本库中的版本替换到工作区的版本, 工作区市修改还是删除都可以还原, 但是如果你已经把版本库中的版本删除了, 那么通过 `git checkout` 就无法还原

## 远程仓库
### Q1: 如何实现本地的 Git 仓库和 Github 仓库之间的同步?
### Q2: 如何从 Github 上面拉取一个项目?
## 分支管理
### Q1: 为什么要创建分支?
## 标签管理
## 使用 Github
## 自定义 Git
### Q1:有些特殊的文件, 我不想提交到远程仓库当中, 但是我必须把它放到 Git 的工作目录当中, 该怎么解决?
### Q2: 有些命令特别长, 用手敲特别麻烦, 还容易敲错, 该怎么解决?
### Q3: 如何搭建一个 Git 服务器?


