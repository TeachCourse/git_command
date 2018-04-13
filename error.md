- 项目提交失败

![](img/20180412161324.jpg)

> [github项目提交失败 master -> master (non-fast-forward)](http://michaelye1988.iteye.com/blog/1653599)


- VIM退出命令

> [VIM中的保存和退出、VIM退出命令、如何退出vim编辑、VIM命令大全](https://blog.csdn.net/feosun/article/details/73196299)


- git fetch：相当于是从远程获取最新版本到本地，不会自动merge

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

- git pull：相当于是从远程获取最新版本并merge到本地

```
git pull origin master
```

上述命令其实相当于git fetch 和 git merge 在实际使用中，git fetch更安全一些。因为在merge前，我们可以查看更新情况，然后再决定是否合并结束。

- checkout：切换分支（删除、添加或更改项目内的文件）

```
git checkout release
```

上述命令的含义：

将当前分支切换到release


- rebase命令和merge命令的区别

```
//rebase操作：
git rebase origin

//merge操作：将origin合并到本地当前分支
git merge origin
```

> [git merge 和 git rebase 小结](https://blog.csdn.net/wh_19910525/article/details/7554489)


- Git如何取消本地commit操作

|command|description|
|-------|-----------|
|`git reset --mixed`|此为默认方式，不带任何参数的git reset，即时这种方式，它回退到某个版本，只保留源码，回退commit和index信息
|`git reset --soft`|回退到某个版本，只回退了commit的信息，不会恢复到index file一级。如果还要提交，直接commit即可
|`git reset –hard`|彻底回退到某个版本，本地的源码也会变为上一个版本的内容
|`HEAD`|最近一个提交
|`HEAD^`| 上一次

*Note that*:<commit_id>  每次commit的SHA1值. 可以用git log 看到,也可以在页面上commit标签页里找到

```
git reset --hard <commit_id>

git push origin HEAD --force
```


