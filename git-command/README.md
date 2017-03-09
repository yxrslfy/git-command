# Git 创建版本库

* Git安装好了之后，首先进行设置
```
    git config --global user.name "your name"
    
    git config --global user.email "youremail@xxx.com"
```
* 把当前目录变为Git可以管理的仓库
```
    git init
```

* 把要添加的文件添加到Git上。
```
    git add [filename]
```
* 提交代码到Git仓库
```
    git commit -m "commit"
    // 双引号内为提交说明，为更好的阅读代码，最好每次都填写。
```

* 远程克隆Git仓库项目及整个代码历史
```
    git clone [url]
```

# Git 增加删除文件 

* 添加指定文件到暂存区
```
    git add [filename]
```
* 添加当前目录的所有文件到暂存区
```   
    git add .
```
* 删除工作区文件，并将此次删除记录到暂存区
```   
    git rm [file]
```
* 改名文件，并将此次改名记录到暂存区
```   
    git mv [file-origina] [file-renamed]
```


# Git 代码提交

* 提交暂存区到仓库区
```
    git commit -m "commit message"
```
* 提交暂存区的指定文件到仓库区
```
    git commit [fimename] -m "commit message"
```
* 提交工作区自上次commit之后的变化，直接到仓库区
```
    git commit -a
```
* 提交时显示所有diff信息
```
    git commit -v
```
* 使用一次新的commit，替代上一次提交 (如果代码没有任何新变化，则用来改写上一次commit的提交信息)
```
    git commit --amend -m [message]
```
* 重做上一次commit，并包括指定文件的新变化
```    
    git commit --amend [file1] [file2]
```


# Git 分支

* 列出所有本地分支
```
    git branch
```
* 列出所有远程分支
```
    git branch -r
```
* 列出所有本地分支及远程分支
```
    git branch -a
```
* 新建一个分支，并切换到该分支
```
    git branch -b [branch]
```
* 新建一个分支，指向指定commit
```
    git branch [branch] [commit]
```
* 新建一个分支，与指定的远程分支建立追踪关系
```
    git branch --track [branch] [remote-branch]
```
* 切换到指定分支，并更新工作区
```
    git checkout [branch-name]
```
* 切换到上一个分支
```
    git checkout -
```
* 建立追踪关系，在现有分支与指定的远程分支之间
```
    git branch --set-upstream [branch] [remote-branch]
```
* 合并指定分支到当前分支
```
    git merge [branch]
```
* 选择一个`commit`，合并到当前分支
```
    git cherry-pick [commit]
```
* 删除分支
```
    git branch -d [branch-name]
```
* 删除远程分支
```
    git push origin --delete [branch-name]
    
    git branch -dr [remote/branch]
```


# 查看Git信息

* 显示有变更的文件
```
    git status
```
* 显示当前分支的版本历史
```
    git log
```
* 显示`commit`历史，以及每次`commit`发生变更的文件
```
    git log --stat
```

* 根据关键词，搜索提交历史
```
    git log -S [keyword]
```

* 显示某个`commit`之后的变化每个`commit`占据一行
```
    git log [tab] HEAD --pretty=format:%5
```

* 显示某个文件的版本历史，包括文件改名
```
    git log --follow [file]
    
    git whatchanged [file]
```

* 显示所有提交过的用户，按提交次数排序
```
    git shorlog -sn
```

* 显示指定文件是什么人在什么时间修改过
```
    git blame [file]
```

* 显示暂存区和工作区的差异
```
    git diff
```

* 显示暂存区和上一个commit的差异

```
    git diff --cached [file]
```

* 显示工作区与当前分支最新commit之间的差异
```
    git diff HEAD
```

* 显示两次提交之间的差异
```
    git diff [first-branch]...[second-branch]
```

* 显示某次提交的元数据和内容变化
```
    git show [commit]
```

* 显示某次提交发生变化的文件
```
    git show --name-only [commit]
```

* 显示某次提交时，某个文件的内容
```
    git show [commit]:[filename]
```

* 显示当前分支的最近几次提交
```
    git reflog
```


# Git 标签

* 列出所有tag
```
    git tag
```

* 新建一个tag在当前commit
```
    git tag [tag]
```

* 新建一个tag在指定commit
```
    git tag [tag] [commit]
```

* 删除本地tag
```
    git tag -d [tag]
```

* 删除远程tag
```
    git push origin :refs/tags/[tagName]
```

* 查看tag信息
```
    git show [tag]
```

* 提交指定tag
```
    git push [remote] [tag]
```

* 提交所有tag
```
    git push [remote] --tags
```

* 新建一个分支，指向某个tag
```
    git checkout -b [branch] [tag]
```


# Git 远程同步

* 下载远程仓库所有的变动
```
    git fetch [remote]
```

* 显示所有远程仓库
```
    git remote -v
```

* 显示某个远程仓库的信息
```
    git remote show [remote]
```

* 增加一个新的远程仓库，并命名
```
    git remote add [shortname] [url]
```

* 取回远程仓库的变化，并与本地分支合并
```
    git pull [remote] [branch]
```

* 上传本地指定分支到远程仓库
```
    git push [remote] [branch]
```

* 强行推送当前分支到远程仓库，即使有冲突
```
    git push [remote] --force
```

* 推送所有分支到远程仓库
```
    git push [remote] --all
```


# Git 撤销

* 恢复暂存区的指定文件到工作区
```
    git checkout [filename]
```

* 恢复某个`commit`的指定文件到暂存区和工作区
```
   git checkout [commit] [filename] 
```

* 恢复暂存区所有的文件到工作区
```
    git checkout .
```

* 重置暂存区的指定文件，与上一次`commit`保持一致，但工作区不变
```
    git reset [filename]
```

* 新建一个commit，用来撤销指定commit 后者的所有变化都将被前者抵消，并且应用到当前分支
```
    git revert [commit]
```

* 暂时将未提交的变化移除，稍后再移入
```
    git stash
    
    git stash pop
```

* 生成一个可供发布的压缩包
```
    git archive
```