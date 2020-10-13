SVN

![](https://external-30160.picsz.qpic.cn/27539bd6740018184d7522d9c5ea7526)

![](https://external-30160.picsz.qpic.cn/f0e7506fc84d96d1b0c700f8b417f22a)





# 1.Git 基础

Git是一个版本管理控制系统 (缩写VCS) .它可以在任何时间点,将文档的状态作为更新记录保存起来,也可以
在任何时间点，将更新记录恢复回来。

## 1.1 Git提交

	1.git init 初始化git仓库
	2.git status 查看文件状态
	3.git add 追踪文件
	4.git commit -m "提交的信息" 向仓库中提交代码
	5.git log 查看提交记录
## 1.2 恢复记录

- 用暂存区文件覆盖工作目录文件 ： git checkout 文件
- 将文件从暂存区中删除: git rm --cached文件



- git log

- git reset --hard commitID 将git仓库中指定记录恢复，并覆盖暂存区和工作目录

注意:回到过去之后，要想再回到之前最新的版本的时候，则需要使用指令去查看历史操作,得到最新的commit id。

- **指令: 	git reflog**

在写回退指令的时候commit id可以不用写全, git 自动识别，但是也不能写太少，至少需要写前4位字符

- 指令: 	**git checkout** commit id -- .

回退到上版本并保留当前版本
  
   

![](https://external-30160.picsz.qpic.cn/d3be87bd2c92c6c6ac93706b9c993002)

## 1.3忽略文件

场景:在项目目录下有很多万年不变的文件目录，例如CSS、is、 images 等，或者还有一些目录即便有改动，我们也不想让其提交到远程仓库的文档，此时我们可以使用“忽略文件”机制来实现需求。

忽略文件需要新建一个名为gitinore.的文件，该文件用于声明忽略文件或不忽略文件的规则，规则对当前目录及其子目录生效。

**注意:该文件因为没有文件名，没办法直接在windows 目录下直接创建，可以通过命令行GitBash来touch创建。**



![](https://external-30160.picsz.qpic.cn/dc1c4ca036cff1fcb690443c2c153b0f)



①新增.gitignore文件

![](https://external-30160.picsz.qpic.cn/b3033a5ca3d5fed6140976ba59644436)

②编写文件中的规则

![](https://external-30160.picsz.qpic.cn/8921f4f01bd7009f2c4c4621361c4656)









# 2.Github

![](https://external-30160.picsz.qpic.cn/9776e7b5c61349628d1eda8db151fdac)

## 2.1 Github 提交仓库

1. git push 远程仓库地址 分支名称(master)
3. git push -U远程仓库地址 别名分支名称
-u记住推送地址及分支，下次推送只需要输入git push即可
4. git remote add 远程仓库地址别名远程仓库地址

## 2.2 Git 克隆

	Git 克隆 
	git clone 仓库地址

```
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/1738100406/html-css.git
git push -u origin master
                
```





	拉取远程仓库最新版
	git pull  远程仓库地址 分支名称(master)

![](https://external-30160.picsz.qpic.cn/76df3074e40e778de13158959ef46620)

提醒:
	在每天工作的第一件事就是先git pull拉取线上最新的版本

​	每天下班前要做的是gitpush,将本地代码提交到线上仓库

解决冲突

① git pull

![](https://external-30160.picsz.qpic.cn/87c9eceabea3f9fb4787bd60a1c38716)

②打开冲突文件，解决冲突解决方法:需要和同事(谁先提交的)进行商量，看代码如何保留，将改好的文件再次提交即可。|

![](https://external-30160.picsz.qpic.cn/fea11f5c3ae87374d5dc1b7bc3d0fd9c)

![](https://external-30160.picsz.qpic.cn/94829cd89368a4dc173aa6c0f90f46af)

③重新提交







## 2.3  ssh免登陆

![](https://external-30160.picsz.qpic.cn/9ea7f349a6c7e4da1882723a7c5a759f)
生成秘钥: ssh-keygen
秘钥存储目录: C:\Users\用户\.ssh
公钥名称: id_ rsa.pub
私钥名称: id. rsa

# 3.Gitee
1、在本地待上传的代码文件夹，右键 选择：Git Bash Here
2、出来的窗口上执行：git init
3、然后执行：git add .    （. 表示当前目录所有内容），注意 add 后要有空格，这个是个容易 踩的坑
4、git commit -m "注释的内容"   #提交到本地仓库
5、提交代码到gitee： git remote add origin 远程项目的Https地址
6、git push -u origin master -f   #-f强制上传
7、弹出帐号密码框时：输入账号密码。



查看有多少个分支    git branch

创建分支					git branch 分支名

切换到副分支			git checkout 分支名 	

删除分支 				git branch -d 分支名



git checkout -b 分支名  创建并切换分支

git merge 次分支 --no-ff 	次分支合并副分支

git push origin dev 		推送到副分支

git remote rm origin   删除分支

```
mkdir html_css
cd html_css
git init
touch README.md
git add README.md
git commit -m "first commit"
git remote add origin https://gitee.com/no_broken_heart/html_css.git
git push -u origin master

git push --set-upstream origin main
```

