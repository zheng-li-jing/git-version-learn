#### git的3个步骤
	1. git add. 将所有文件放入暂存区
	2. git commit -m 'comment' 将所有文件从暂存区放入本地仓库
	3. git push origin master 将本地仓库推送到远程仓库
#### git的4个区
	1. 工作区(Working Area)
	2. 暂存区(Stage)
	3. 本地仓库(Loacl Repository)
	4. 远程仓库(Remote Repository)
#### git的5个状态
	1. 未修改状态(Origin)
	2. 修改状态(Modify)
	3. 已暂存状态(Staged)
	4. 已提交状态(Committed)
	5. 已推送状态(Pushed)
#### 检查修改以及撤回
	1. 是已修改状态，未暂存
		+ 查看文件的差异: git diff
		+ 撤回到未修改状态: git checkout .(或者: git reset --hard)
	2. 是已暂存状态，未提交
		+ 查看文件的差异: git diff --cached
		+ 撤回到已修改状态: git reset --hard(或者:先git reset,然后git checkout .)
	3. 是已提交状态，未推送
		+ 查看文件的差异: git diff HEAD^ HEAD,查看的上一次提交和当前提交的区别(或者: git diff master origin/master，查看的是主分支和远程主分支的区别)
		+ 撤回到已修改或未修改状态: git reset --hard origin/master(或者: git reset --soft HEAD^,撤回commit操作，但代码保留)
	4. 已推送
		+ 撤回到未修改状态: git reset --hard HARD^, then, git push -f,(先恢复本地仓库，然后强势推送到远程仓库)