## 新建代码库
```bash
$ git init  						# 在当前目录新建一个Git代码库
$ git clone [url]					# 下载一个项目和它的整个代码历史
```
## 配置
```bash
$ git config --global user.name "Your Name"				# 设置提交代码时的用户信息
$ git config --global user.email "email@example.com"	# 设置提交代码时的用户信息
```
## 增加/删除文件
```bash
$ git add [file1] [file2] ...		# 添加指定文件到暂存区
$ git add .							# 添加当前目录的所有文件到暂存区
$ git rm [file1] [file2] ...		# 删除工作区文件，并且将这次删除放入暂存区
$ git mv [file-original] [file-renamed]				# 改名文件，并且将这个改名放入暂存区、
```
## 代码提交
```bash
$ git commit -m [message]			# 提交暂存区到仓库区
```
## 分支
```bash
$ git branch						# 列出所有本地分支
$ git branch -a						# 列出所有本地分支和远程分支
$ git branch [branch-name]			# 新建一个分支，但依然停留在当前分支
$ git checkout -b [branch]			# 新建一个分支，并切换到该分支
$ git branch [branch] [commit]		# 新建一个分支，指向指定commit
$ git branch --track [branch] [remote-branch]		# 新建一个分支，与指定的远程分支建立追踪关系
$ git checkout [branch-name]		# 切换到指定分支，并更新工作区
$ git branch --set-upstream [branch] [remote-branch]	# 建立追踪关系，在现有分支与指定的远程分支之间

$ git merge [branch]				# 合并指定分支到当前分支
$ git merge --no-ff -m [message] [branch]	# 合并指定分支到当前分支(禁用Fast forward)
$ git cherry-pick [commit]			# 选择一个commit，合并进当前分支

$ git branch -d [branch-name]		# 删除分支
$ git branch -D [branch-name]		# 丢弃一个没有被合并过的分支
$ git branch -dr [remote/branch]	# 删除远程分支
```
## 标签

```bash
$ git tag							# 列出所有tag
$ git tag [tag]						# 新建一个tag在当前commit
$ git tag [tag] [commit]			# 新建一个tag在指定commit
$ git tag -a [tag] -m "blablabla..."	# 指定标签信息
$ git tag -d [tag]					# 删除本地tag
$ git push origin :refs/tags/[tagName]	# 删除远程tag
$ git show [tag]					# 查看tag信息
$ git push [remote] [tag]			# 提交指定tag
$ git push [remote] --tags			# 提交所有tag
$ git checkout -b [branch] [tag]	# 新建一个分支，指向某个tag
```
## 查看信息

```bash
$ git status						# 显示有变更的文件
$ git log							# 显示当前分支的版本历史
$ git log --graph --pretty=oneline --abbrev-commit
$ git diff							# 显示暂存区和工作区的差异
$ git show [commit]					# 显示某次提交的元数据和内容变化
$ git reflog						# 显示当前分支的最近几次提交
```
## 远程同步
```bash
$ git fetch [remote]				# 下载远程仓库的所有变动
$ git remote -v						# 显示所有远程仓库
$ git remote add [remote] [url]		# 增加一个新的远程仓库，并命名
$ git pull [remote] [branch]		# 取回远程仓库的变化，并与本地分支合并
$ git push [remote] [branch]		# 上传本地指定分支到远程仓库

$ ssh-keygen -t rsa -C "youremail@example.com"
$ git remote add origin [url]
$ git branch -M master
$ git push -u origin master
```
## 撤销
```bash
$ git checkout [file]				# 恢复暂存区的指定文件到工作区
$ git checkout [commit] [file] 		# 恢复某个commit的指定文件到暂存区和工作区
$ git checkout .					# 恢复暂存区的所有文件到工作区
$ git reset [file]					# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
$ git reset --hard					# 重置暂存区与工作区，与上一次commit保持一致
$ git reset [commit]				# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
$ git reset --hard [commit]			# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致

$ git stash							# 把当前工作现场“储藏”起来
$ git stash pop						# 恢复的同时删除stash
```
## 其他
```bash
$ git archive						# 生成一个可供发布的压缩包
$ git rebase						# 把本地未push的分叉提交历史整理成直线
```

