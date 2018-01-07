# git-learn
git 常用命令解析


1，常用命令
1.1 git常用命令
1.2 git的三种状态
2，常用命令区分不同
2.1 回滚（撤销）
2.2 比较
2.3 删除
2.3 恢复 
3，远程操作
3.1 提交本地代码到远程
3.2 解决冲突
4，参考网站
4.1 网址
1，常用命令
1.1 git常用命令
 
 
 
git config --global user.name "yangjingjing07"

git config --global user.email "yangjingjing07@meituan.com"

git config --list

这2个配置信息必须设置，在你提交代码的时候会显示是谁提交的代码

 

查看配置信息

git config可以自定义指定别名
git clone 克隆地址	克隆代码	 
git status	
查看工作区，暂存区修改

红色代表未缓存

绿色代表已经缓存

 
git checkout branchname

git checkout -b newbranchname

切换分支

创建一个新分支并切换过去

注：创建分支的时候是根据俄当前分支来创建的，如果要指定从某个分支创建新分支分支，一定要切换到那个指定分支

 
git merge branchname

 

合并branchname分支到当前分支

如果有冲突是合并不成功的，只有手动解决完冲突再次 add commit 之后

再去查看已经合并成功了，

然后可以删除已经合并的分支

 
git branch

git branch --merged

git branch --no-merged

git branch -d branchname

git branch -D branchname

查看本地所有分支

已经合并到当前分支的所有分支

为合并到当前分支的所有分支

删除某个已合并的分支

强制删除某个分支，即使没有合并也可以删除

 
git tag

git tag v1.0.0

git push origin v1.0.0

查看历史标签

打一个1.0.0的标签

推送到远程

 
git stash

git stash list

git stash pop

不想提交的修改放到储藏区

查看储藏记录

还原最新一次的储藏区

 
1.2 git的三种状态
    工作区———>暂存区———>版本库

              add                    commit

    git add .   全部修改添加到缓存区

   git commit -m "add distributed" 缓存区提交到版本库

   简写：以上2个命令合并写法

   git commit -a -m “提交注释”

2，常用命令区分不同
2.1 回滚（撤销）
 
 
 
git reset HEAD .

git reset HEAD filename

 从暂存区撤销回工作区	 
git checkout .

git checkout filename

 从版本区撤销回工作区

(如果暂存区也存在修改文件先从暂存区拉去，没有的情况下才会拉去版本区 待验证)

 
git commit --amend	
 假如已经commit提交一次了，但是漏掉了一些修改

git add .

git commit -m ‘撤销上次提交状态合并到这次提交’ amend

上次提交状态就会撤销被合并到这次提交中

 
2.2 比较
 
 
 
git diff	工作区 跟暂存区比较 	 
git diff --cached	 暂存区跟版本库比较	 
git diff master	 工作区跟版本库比较	 
2.3 删除
 
 
 
git rm filename	工作区删除一个文件，删除暂存区文件	 
git rm -f filename	 删除工作区，缓存区文件	 
git rm --cached filename	 仅删除暂存区，保留工作区文件	 
2.3 恢复 
 
 
 
git checkout commitID filename	工作区误操作一个filename，恢复某个commit下的filename	 
git reset --hard commitID

git reset --hard

git reset --hard HEAD^

git reset --hard HEAD~3

工作区恢复到某个版本，commitID可是复制前几个就行

工作区恢复到最近一次提交commit版本

工作区恢复到上上一次commit版本

工作区恢复到后退3个版本

HEAD指向某个版本指针
git reflog	查看所有HEAD移动状态，找到你想回去的版本ID	 
3，远程操作
3.1 提交本地代码到远程
 

 
 
 
 
 
 
git remote -v	查看远程仓库分支信息，网址，名称	 
git push origin master	提交本地代码到远程master 分支	
这次操作会把在本地commit的所有记录也会同步上去

如果有冲突是推送不上远端的，解决完冲突才能再次推送

 	 	 
3.2 解决冲突
 
 
 
git fetch	
拉取远端代码但不合并

git diff master origin/master 查看区别

git merge origin/master 手动合并代码，做取舍之后在在push 到远端

 
git pull	拉取远端代码自动合并大本地	 
 

4，参考网站
4.1 网址
 http://git.oschina.net/progit/

https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/
