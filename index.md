## 第一步：新建分支
首先，每次开发新功能，都应该新建一个单独的分支（这方面可以参考《Git分支管理策略》）。 可以按照开发功能模块命名，也可以是按照日期(上线日期，提测日期，开发日期))来命名，如sprint180829这样子。

```
# 获取主干最新代码,将代码fork到自己的仓库。
# 使用CMD:
$ git clone xxx地址 // 获取下来的代码就在master分支
# 添加远程仓库
$ git remote add team(这里填名称) xxx(远程仓库地址)
# 新建分支
$ git checkout -b sprint180829
# 如果要获取远程仓库上面的代码
$ git pull team(远程仓库名) sprint180829(远程仓库分支)

# 切换分支
$ git checkout master
```

## 第二步：提交分支commit

> 该过程 “非常非常” 建议通过 IDE 来完成，以便每一次提交都是经过检查的,确保没有提交不该提交的代码。
分支修改后，就可以提交commit了。
```
$ git add --all
$ git status
$ git commit --verbose
```

## 第三步：撰写提交信息
> TODO 后续会采用 webhook 自动更新从提交信息中拉去信息更细 jira 状态等

提交commit时，必须给出完整扼要的提交信息，下面是一个范本。

Bug fix

* 解决 xxx 问题 jira: xxxx
* 解决 xxx 问题 jira: xxxx
第一行是不超过50个字的提要，然后空一行，罗列出改动原因、主要变动、以及需要注意的问题。最后，提供对应的网址（比如Bug ticket）。

## 第六步：推送到远程仓库
```
git push origin sprint180829
```
合并commit后，就可以推送当前分支到你 fork 的远程仓库了。

推送不上去，则命令要加上force参数，因为rebase以后，分支历史改变了，跟远程分支不一定兼容，有可能要强行推送。

如果推送布上去，则命令
