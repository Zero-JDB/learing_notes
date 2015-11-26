安装Git
=======
在windows上安装Git
----------------
下载mysysgit(windows下的git)，然后默认选项安装下载。

安装后打开能弹出窗口，说明安装成功。

安装完成后，配置你的github用户信息：
>$ git config --global user.name "Your Name"

>$ git config --global user.email "email@example.com"

创建版本库
============
创建仓库
--------
第一步创建一个空的目录
>$ mkdir [repository_name] //创建目录

>$ cd [repository_name] //切换路径

>$pwd //查看当前路径

第二步将当前目录变成git仓库
>$ git init

>Initialized empty Git repository in /Users/michael/learngit/.git/

添加文件
--------
第一步，将文件添加到仓库
>$ git add [file_name] //执行后没有反应则表示成功

>$ git add -A  //添加全部文件

第二步，提交到仓库
>$ git commit -m "描述信息"

>[master (root-commit) cb926e7] wrote a readme file 1 file changed, 2 insertions(+) create mode 100644 readme.txt

查看状态
=========
1.查看状态
>$ git status

2.查看文件具体修改内容
>$ git diff [file_name]

3.查看文本内容
>$ cat [file_name]

版本回退
==========
1.查看历史记录
>$ git log

2.查看历史记录（一行显示 简略）
>$ git log --pretty=oneline

3.回退上一个版本
>$ git reset --hard HEAD^

4.回退至指定版本
>$ git reset --hard [commit_id]

5. 查看命令记录
>$ git reflog


管理修改
===========
1.查看工作区和版本库里面最新版本的区别 
>$ git diff HEAD -- [file_name]

2.丢弃工作区的修改(add 前),恢复误删文件(最后一次提交的内容)
>$ git checkout -- [file_name]

3.撤销暂存区的修改(add 后)
>$ git reset HEAD [file_name]

4.从版本库中删除文件/文件夹
>$ git rm [file_name] //删除后须git commit 

>$ git rm -r [folder] //删除后须git commit 


远程仓库
==========
添加SSH key
------------
1.创建SSH KEY,输入命令后会在用户主目录下创建.ssh目录,
id_rsa是私钥，id_rsa.pub是公钥。
>$ ssh-keygen -t rsa -C "youremail@example.com"

2.登录GitHub，add SSH Key，粘贴id_rsa.pub的内容


添加远程仓库
------------
1.登录GitHub，创建一个Git仓库

2.将本地仓库与远程仓库关联 
>$ git remote add origin git@github.com:[username]/[repository_name].git

3.查看关联的远程仓库 
>$ git remote -v 

4.查看远程仓库信息 
>$ git remote origin

5.删除关联的远程仓库 
>$ git remote rm origin

克隆远程仓库
-------------
将已有远程仓库克隆到本地
>$ git clone git@github.com:[username]/[repository_name].git


推送分支内容
------------
将本地仓库的master分支推送到远程
>$ git push -u origin master //第一次推送

>$ git push origin master

分支管理
=========
创建与合并分支
--------------
1.创建dev分支，然后切换
>$ git branch dev

>$ git checkout dev

2.创建dev分支，然后切换（另一种方式）
>$ git checkout -b dev

3.查看分支 (*号为当前分支) 
>$ git branch 

4.切换分支至master 
>$ git checkout master

5.将dev的工作成果合并到当前分支（当前分支master）
>$ git merge dev

6.删除分支dev 
>$ git branch -d dev

7.强制删除分支dev 
>$ git branch -D dev

8.查看分支合并信息 
>$ git log --graph --pretty=oneline --abbrev-commit

分支管理策略
------------
1.禁用 Fast forward
>$ git merge --no-ff -m "描述" dev

2.储存当前工作现场 
>$ git stash

3.查看储存列表
>$ git stash list

4.恢复储存信息（指定第一条）
>$ git stash apply stash@{0}

5.删除储存信息（指定第一条）
>$ git stash drop stash@{0}

6.恢复后删除储存信息（指定第一条） 
>$ git stash pop stash@{0}

7.在本地创建和远程分支对应的分支 
>$ git checkout -b branch-name origin/branch-name

8.建立本地dev与远程origin/dev分支联系
>$ git branch --set-upstream dev origin/dev 

9.获取远程分支最近提交 
>$ git pull


标签管理
==========
创建标签
---------
1.创建新标签 
>$ git tag [tagname]

2.创建指定提交的标签
>$ git tag [tagname]  [commit_id]

3.创建带描述的标签
>$ git tag -a [tagname] -m "描述" [commit_id]

4.查看所有标签 
>$ git tag

5.查看指定标签信息 
>$ git show [tagname]

操作标签
========
1.删除标签 
>$ git tag -d [tagname]

2.推送某个标签到远程 
>$ git push origin [tagname]

3.推送全部标签到远程 
>$ $ git push origin --tags

4.从远程删除某个标签
>$ git push origin :refs/tags/[tagname]

5.切换至标签
>$ git checkout -f [tagname]
