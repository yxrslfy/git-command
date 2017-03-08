# Git 创建版本库

* Git安装好了之后，首先进行设置
`git config --global user.name "your name"`
`git config --global user.email "youremail@xxx.com"`

* 把当前目录变为Git可以管理的仓库
<br/>
`git init`

* 把要添加的文件添加到Git上。
`git add [filename]`

* 提交代码到Git仓库
`git commit -m "commit"`
双引号内为提交说明，为更好的阅读代码，最好每次都填写。

* 远程克隆Git仓库项目及整个代码历史
`git clone [url]`


# Git 增加删除文件 

* 添加指定文件到暂存区
`git add [filename]`

* 添加当前目录的所有文件到暂存区
`git add .`

* 删除工作区文件，并将此次删除记录到暂存区
`git rm [file]`

* 改名文件，并将此次改名记录到暂存区
`git mv [file-origina] [file-renamed]`


# Git 代码提交

* 提交暂存区到仓库区
`git commit -m "commit message"`

* 提交暂存区的指定文件到仓库区
`git commit [fimename] -m "commit message"`

* 提交工作区自上次commit之后的变化，直接到仓库区
`git commit -a`

* 提交时显示所有diff信息
`git commit -v`

* 使用一次新的commit，替代上一次提交 (如果代码没有任何新变化，则用来改写上一次commit的提交信息)
`git commit --amend -m [message]`

* 重做上一次commit，并包括指定文件的新变化
`git commit --amend [file1] [file2]`


# Git 分支

* 列出所有本地分支
`git branch`

* 列出所有远程分支
`git branch -r`

* 列出所有本地分支及远程分支
`git branch -a`

* 新建一个分支，并切换到该分支
`git branch -b [branch]`

* 新建一个分支，指向指定commit
`git branch [branch] [commit]`

* 新建一个分支，与指定的远程分支建立追踪关系
`git branch --track [branch] [remote-branch]`

* 切换到指定分支，并更新工作区
`git checkout [branch-name]`

* 切换到上一个分支
`git checkout -`

* 建立追踪关系，在现有分支与指定的远程分支之间
`git branch --set-upstream [branch] [remote-branch]`

* 合并指定分支到当前分支
`git merge [branch]`

* 选择一个`commit`，合并到当前分支
`git cherry-pick [commit]`

* 删除分支
`git branch -d [branch-name]`

* 删除远程分支
`git push origin --delete [branch-name]`
`git branch -dr [remote/branch]`


