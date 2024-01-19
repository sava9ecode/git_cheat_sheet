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
