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