安装Git
=======
在windows上安装Git
----------------
从[exampel line](http://mysysgit.github.io/)下载，然后默认选项安装下载。
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

第二步，提交到仓库
>$ git commit -m "描述信息"
>[master (root-commit) cb926e7] wrote a readme file 1 file changed, 2 insertions(+) create mode 100644 readme.txt
