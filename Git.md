### Accelerate git

```bash
github.com -->  github.com.cnpmjs.org
```

### Git proxy

```bash
git config -global  https.proxy https://127.0.0.1:7891
```
### git 放弃更改
```bash
git checkout . #本地所有修改的。没有的提交的，都返回到原来的状态
git stash #把所有没有提交的修改暂存到stash里面。可用git stash pop回复。

git reset --hard HASH #返回到某个节点，不保留修改，已有的改动会丢失。
git reset --soft HASH #返回到某个节点, 保留修改，已有的改动会保留，在未提交中，git status或git diff可看。

git clean -df #返回到某个节点，（未跟踪文件的删除）
```

### git拉取远程分支
```bash
git branch -r
git pull origin xxx
```


### git cmakelist
```
	GIT_REPOSITORY https://github.com/giaf/blasfeo
	GIT_TAG ae6e2d1dea015862a09990b95905038a756ffc7d

  URL ${CMAKE_CURRENT_SOURCE_DIR}/blasfeo.zip
```

### git stash

```
git stash list
git stash apply stash@{1}
```
