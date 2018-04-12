学习Git命令行操作

- 检查当前目录文件状态

```
git status
```

- 添加未跟踪的文件或文件夹

```
//单个文件添加
git add README.MD

//批量文件添加
git commit -a -m 'add more files'
```

- 提交暂存起来的文件

```
git commit
```

- 删除某个文件

```
git rm note.txt
```

[2.2 Git 基础 - 记录每次更新到仓库](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E8%AE%B0%E5%BD%95%E6%AF%8F%E6%AC%A1%E6%9B%B4%E6%96%B0%E5%88%B0%E4%BB%93%E5%BA%93)


- 检查提交的日志

```
git log

//比较最近2次提交日志的区别
git log -p -2

//查看提交日志的统计信息
git log --stat
```

[2.3 Git 基础 - 查看提交历史](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E6%9F%A5%E7%9C%8B%E6%8F%90%E4%BA%A4%E5%8E%86%E5%8F%B2)


- 撤销提交操作

```
git commit --amend

//添加新的文件后覆盖最新提交的版本
git commit -m 'initial commit'
git add forgotten_file
git commit --amend
```

- 取消暂存的文件

```
git reset HEAD <file>...
```

- 保持本地文件和仓库一致

```
//双减号后空格，后面文件名
git checkout -- README.MD
//保持分支一致
git checkout master
```

[2.4 Git 基础 - 撤消操作](https://git-scm.com/book/zh/v2/Git-%E5%9F%BA%E7%A1%80-%E6%92%A4%E6%B6%88%E6%93%8D%E4%BD%9C)


- 查看远程仓库

```
git remote -v
```

- 添加远程仓库

```
//pb表示别名，可以代替完整的url地址
git remote add pb https://github.com/teachcourse/git_command
```

- 拉取远程仓库

```
//用别名pb代替完整的url地址：https://github.com/teachcourse/git_command
git fetch pb

git fetch https://github.com/teachcourse/git_command
```

- 推送到远程仓库

```
//推送成功演示
git push https://github.com/teachcourse/git_command master
//pb表示仓库别名（推送失败）
git push pb master
```

- 查看远程仓库

```
//origin表示仓库url别名，比如：gitNick
git remote show origin
```