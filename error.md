- 项目提交失败

![](img/20180412161324.jpg)

> [github项目提交失败 master -> master (non-fast-forward)](http://michaelye1988.iteye.com/blog/1653599)


- VIM退出命令

> [VIM中的保存和退出、VIM退出命令、如何退出vim编辑、VIM命令大全](https://blog.csdn.net/feosun/article/details/73196299)


- fetch命令、pull命令和checkout命令之间的区别

1. git fetch：相当于是从远程获取最新版本到本地，不会自动merge

```
Git fetch origin master
git log -p master..origin/master
git merge origin/master
```

以上命令的含义： 
首先从远程的origin的master主分支下载最新的版本到origin/master分支上；然后比较本地的master分支和origin/master分支的差别；最后进行合并。上述过程其实可以用以下更清晰的方式来进行：

```
git fetch origin master:tmp
git diff tmp 
git merge tmp
```

从远程获取最新的版本到本地的tmp分支上之后再进行比较合并 

2. git pull：相当于是从远程获取最新版本并merge到本地

```
git pull origin master
```

上述命令其实相当于git fetch 和 git merge 在实际使用中，git fetch更安全一些。因为在merge前，我们可以查看更新情况，然后再决定是否合并结束。

3. checkout：切换分支（删除、添加或更改项目内的文件）

```
git checkout release
```

上述命令的含义：

将当前分支切换到release

> [git fetch和git pull之间的区别](https://blog.csdn.net/a19881029/article/details/42245955)


