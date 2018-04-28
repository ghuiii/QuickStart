Git本身是一个非常强大的版本管理工具,功能很多,全部掌握也比较困难,好在大部分的命令平时基本不会用到,经常使用的命令也不是很多,在这里我总结一下平时比较常用的几个命令,方便日后随时查看也分享给大家:

## 1. 分支操作

- 创建本地分支 `git checkout -b your_branch_name`
- 删除本地分支 `git branch -d your_branch_name`
- 创建远程分支
  1. 先创建本地分支 `git checkout -b your_branch_name`
  2. 推送本地分支到远端 `git push -u <remote-name> your_branch_name`
- 删除远程分支 `git push origin :the_remote_branch`

## 2. Tag操作

- 创建本地Tag `git tag tag_name [commit_id]` ([]代表此参数可省略，默认为HEAD)
- 创建远程Tag
  1. 创建本地Tag `git tag tag_name [commit_id]`
  2. 推送到远端 `git push origin tag_name`
- 基于某个Tag，拉出新分支 `git checkout -b your_branch_name tag_name`
- 删除本地Tag `git tag -d your_tag_name`
- 删除远程Tag `git push origin :remote_tag_name`

## 3. git 配置

1. `git config -e` 打开当前.git目录下的.gitconfig配置文件
2. `git config -e --global` 打开~/.gitconfig配置文件
3. `git config -e --system` 打开/etc/.gitconfig配置文件

## 4. 其它常用操作

1. 恢复某个文件至某个**commit**下的状态。

```
1. git reset <commit-id^> -- <文件path>
2. git checkout <文件path> //之后再做一次提交即可
```

1. 上面一个操作的控制粒度是文件级别的，如果你想撤销历史上某次commit作的所有修改还有一个更方便的操作 :

```
git revert <commit_id>
```

> 这个操作会针对`<commit_id>`这次提交做一次反提交(生成一个新的commit), 因此并不会改变提交历史。

