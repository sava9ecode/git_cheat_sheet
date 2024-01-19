# Work With Repositories/Branches

## Clonnig

Cloning:
```bash
git clone <url>
```

Check if everything is ok:
```bash
git remote -v
```

## Forking

Forking a repository is the matter of clicking a button.

To follow along, browse to a public repository that you want to fork.  
At the top right of the page, you will find the Fork button. Click on  
the button and wait for a few seconds. You will see that the newly  
forked repository gets created under your GitHub account.

## Branch Workflow
Check:
```bash
git branch  # * is a sign in what branch you are
```

Create:
```bash
git branch <branch_name>
```

Switch:
```bash
git checkout <branch_name>
```

Create and switch in one time:
```bash
git branch -b <branch_name>
```

Compare:
```bash
git diff <branchname1> <branchname2>  # you can also use HEAD or commit hash
git diff HEAD~ HEAD  # ~N is a navigation suffix; from 0 to len(commits) - 1; 1 by default (without N)
```

Merge:
```bash
git checkout main  # usually main
git merge <branch_name>
```

Delete:
```bash
git branch -D  # --delete --force
git branch -d  # if there are no changes
```

## Conflict
Sometimes when two or more developers edit the same files, there's a conflict.

![conflict](https://pictures.s3.yandex.net/resources/M3_T3-5_1687852525.png "conflict")

How to solve it?
- check out files where conflict is
- change it to save all things
- `git add && git commit`


![solve a conflict](https://pictures.s3.yandex.net/resources/Untitled-110_1687531034.png "solve a conflict")

Or if you want to avoid a conflict:
```bash
git merge --abort
```

## Push Branch
How to push a branch to a remote repo?
- create a new branch
- do some changes (optional)
- `git push -u origin <new_branch_name>`

*To push a branch it's not necessary to be in it.*

## Pull Request
Where can I do PR?
- link from your terminal
- git UI

What is PR for?
- code review
- merge your branch

## Pull Changes
Good practice:
```bash
git checkout main
git pull
git checkout <your_branch>
git merge main
git push -u origin <your_branch>
```

## Change Remote Repo
```bash
git remote rm origin
git remote add origin <url>
```
