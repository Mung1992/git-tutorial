## Git
* 配置
```
$ git config --global user.name "Firstname Lastname"
$ git config --global user.email "your_email@example.com"
```
* 编辑配置文件
```
$ vi ~/.gitconfig
```
* 创建SSH Key
```
$ ssh-keygen -t rsa -C "your_email@example.com"
```
* 初始化仓库
```
$ mkdir git-tutorial
$ cd git-tutorial
$ git init
```
* 查看仓库状态
```
$ git status
```
* 向暂存区添加文件
```
$ git add README.md
```
暂存区是提交之前的一个临时区域。
* 保存仓库的历史记录
```
$ git commit -m "First commit"
```
如不加-m，则会启动编辑器。
修改提交信息
```
$ git commit --amend
```
* 查看提交日志
```
$ git log --graph
```
查看仓库执行过的操作的日志。
```
$ git reflog
```
* 查看更改前后的差别
```
$ git diff
```
查看的是工作树和暂存区的差别。
```
$ git diff HEAD
```
查看的是工作树和最新提交的差别。
在执行git commit命令之前先执行git diff HEAD命令，查看本次提交与上次提交之间有什么差别，等确认完毕后再进行提交。这里的HEAD 是指向当前分支中最新一次提交的指针。
* 显示分支
```
$ git branch -a
```
* 创建、切换分支  
创建
```
$ git checkout -b
```
切换
```bash
$ git checkout
```
* 合并分支
```
$ git checkout master
$ git merge --no-ff feature-A
```
先切换到master分支，然后再合并。
* 回溯历史版本
```
$ git reset --hard fd0cbf0d4a25f747230694d95cac1be72d33441d
```
* 更改历史
```
$ git rebase -i HEAD~2
```
编辑器打开, 压缩的部分pick改为fixup。
* 添加远程仓库
```
$ git remote add origin git@github.com:github-book/git-tutorial.git
```
可以用hub命令替换
* 推送至远程仓库
```
$ git push -u origin master
```
在master分支下进行操作。  
-u参数可以在推送的同时，将origin 仓库的master 分支设置为本地仓库当前分支的upstream（上游）。
* 获取远程仓库
```
$ git clone git@github.com:github-book/git-tutorial.git
```
默认操作master分支  
可以用hub命令替换
* 获取最新远程仓库分支
```
$ git pull origin feature-D
```
* 查看版本标签
```
$ git tag
```


## Hub
* 获取远程仓库
```
$ hub clone Hello-World
```
* 添加远程仓库
```
$ hub remote add octocat
```
或者
```
$ hub fetch
```
* 创建远程仓库
```
$ hub create
```
* 打开对应仓库页面
```
$ hub browse
```

## Git flow
* 初始设置
```
$ git flow init -d
```
基于master创建develop分支
* 创建feature分支
```
$ git flow feature start add-user
```
创建feature分支add-user
* 创建release分支
```
$ git checkout develop
$ git pull
$ git flow release start '1.0.0' 
```
* 结束release分支
```
$ git flow release finish '1.0.0'
```
会将release合并至delvolop分支
* 创建hotfix分支
```
$ git flow hotfix start '1.0.1' '1.0.0'
```


