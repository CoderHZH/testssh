# Git笔记

## 初始化Git仓库
- `git init`

## 设置当前用户名和邮箱
- `git config --global user.name "hzh"`
- `git config --global user.email "xxx@xxx.com"`

## 存储代码到仓库
- 1. 放到暂存区 
    - `git add ./README.md` 存放指定文件
    - `git add ./` 存放所有修改的文件
- 2. 存放到仓库
    - `git commit -m "说明"`
- 3. 合并1.2步 
    - `git commit --all -m "说明"`

## 查看当前状态
- `git status`

## 忽略文件.gitignore
- .gitignore 此文件可以设置要被忽略的文件或者目录
- 必须要在需要被忽略的文件创建前提交此文件否则不生效
- /.xx 忽略以.xx结尾的文件
- /js 忽略js目录下的所有文件
- /js/*.js 忽略js目录下的js文件

## 查看日志
- `git log` 查看历史提交的日志
- `git log --oneline` 查看简洁版日志

## 回退到指定版本
- `git reset --hard Head~0` 回退到上一条日志的状态
- `git reset --hard Head~1` 回退到上上条日志的状态
- `git reset --hard 版本号` 回退到指定版本号的状态
- `git reflog` 查看每一次切换版本的记录并且可以看到所有提交的版本号

## 分支
- 默认有一个主分支 master
### 创建分支
- `git branch xxx`
    - 创建了xxx分支
    - 创建时会复制当前状态的master
### 切换分支
- `git checkout xxx`
    - 切换到xxx分支
    - `git branch` 查看当前有哪些分支
### 合并分支
- `git merge xxx`
    - 在master分支下操作 合并xxx到master
- 合并冲突 需要手动解决

## GItHub 连接远程仓库
- `git push 地址 master` 把当前分支上传到远程的master分支
- `git pull 地址 master` 会把远程分支的数据得到:(*注意本地-要初始一个仓储!*)
- `git clone 地址` 克隆远程仓库的内容完整复制一份
### pull和clone的区别
- 从远程服务器克隆一个一模一样的版本库到本地,复制的是整个版本库，叫做clone.（clone是将一个库复制到你的本地，是一个本地从无到有的过程）
从远程服务器获取到一个branch分支的更新到本地，并更新本地库，叫做pull.（pull是指同步一个在你本地有版本的库内容更新的部分到你的本地库）
