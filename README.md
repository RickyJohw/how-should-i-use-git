# 🤔 How should I work with Git?

## 🤩 New features with independent branches

```
$ git branch '<new-feature-name>'
$ git switch <new-feature-nae>
```

## 🙌 Multiple implementations of one feature with commits

```bash
# add and commit method one
$ git add .
$ git commit -m 'new feature: XXX, method one'
# 可以根据需求使用revert
$ git revert HEAD~n
```

## 💪 Combining with rebasing instead of merging

```bash
# switch to main branch
$ git switch main
# rebase add
$ git rebase add
# rebase mul
$ git rebase mul
```

## 🤖 Situations

1. 你 commit 的时候备注没有写好，或者还有部分功能没有实现完善就 commit 了，并且你不想保留这次 commit

```bash
# reset your previous commit to staging area
$ git reset --soft HEAD^
# you can also reset your previous commit to working area, it's up to you.
$ git reset HEAD^

# modify...

# readd
$ git add .

# recommit
$ git commit -m '...'
```

Note: It doesn't work for the first commit of your repository. If you want to reset the first commit, you can remove the `.git` directory 😅.

2. 合并最近的多个 commits

```bash
$ git reset --soft HEAD~n
```

Note: 如果你想要合并的 commits 中，最早的 commit 是第一个，这个方法同样不会奏效，最好的方法依然是删除`.git`文件夹，然后重新初始化并 commit
