# Advanced Work With Branches

## Fast Forward State

Conflict is impossible.

During fast forward merge, there will not be a *merge commit* by default:
![FF](https://pictures.s3.yandex.net/resources/M4_T2_01_1689342594.png "FF")
![FF merge](https://pictures.s3.yandex.net/resources/M4_T2_02_1689342662.png "FF merge")

Disable it:

```bash
git merge --no-ff --no-edit <branch_name>
```

Or with git config:

```bash
git config --global merge.ff false
```

If you disable it, there will be a *merge commit*:
![merge without FF](https://pictures.s3.yandex.net/resources/M4_T2_03_1689342784.png "merge without FF")

Graph log to check it:

```bash
git log --oneline --graph
```

## Non Fast Forward State

When you merge branches in non FF mode, there might be a conflict.  
Git try to solve it by itself, but sometimes you must do it by hand/`git mergetool` or IDE.

![non FF state](https://pictures.s3.yandex.net/resources/M4_T2_01202_1689343530.png "non FF")
![maybe a conflict](https://pictures.s3.yandex.net/resources/M4_T2_02203_1689343586.png "there might be a conflict")
![merge commit](https://pictures.s3.yandex.net/resources/M4_T2_03202_1689343628.png "merge commit")

If there was a conflict and you solved it, usually there's no need to change a message for a commit:

```bash
git add . && git commit --no-edit
```

## Git Push And Fast Forward

Git push is expected a fast forward state between branches.

![git push and FF](https://pictures.s3.yandex.net/resources/M4_T2_01201_1689593319.png "git push and FF")

## Git Push And Non Fast Forward

If there is a conflict, git will reject push.

![git push and non FF](https://pictures.s3.yandex.net/resources/M4_T2_03201_1689593362.png "git push and non FF")

You can solve it with rebase or like that:

```bash
git push --force  # bad practice; do it if repo is broken
```

But be careful, with a force flag you rewrite your colleague's commits.

*When you work with other developers, pushing all in a main branch is not a good choice.*

## Models To Work With Branches

- feature branch workflow
- gitflow
- trank-based

These cases have a lot of common things.

Feature branch workflow in short:

Main concepcts:

- new feature or bugfix - new branch
- when feature branch code is ready, it merges with main branch
- main branch always has the last version

Strengths:

- easy model
- it's easy to work with git in a team without tech complicated

## PR Lifecycle

If you work with open-source project and are not a contributor, do fork before clone.

```bash
git clone <url>
git checkout -b <feature_branch>  # + some changes
git push -u origin HEAD  # -u: --set-upstream; HEAD: current branch (feature_branch)
```

Follow to the link to create PR.  
Wait for code review.  
Update code with the comments.  

```bash
git add <file(s)>
git commit -m 'message'
gut push <feature_branch>
```

If everything is ok, reviewer will approve PR.  
Now you or someone from contributors can merge branches.  
Delete remote feature branch.  

Come back to your terminal:
```bash
git checkout main && git pull
git branch -D <feature_branch>
```

## Aliases

```bash
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.gl git log --oneline --abbrev-commit --graph --date=short --pretty=format:'%h - %an, %cd : %s'
```
