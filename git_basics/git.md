# Basic Git Knowlenge

## Install
```bash
sudo apt-get update && sudo apt-get install git-all
git version
```

## Setting Up
Write who are you:
```bash
git config --global user.name "User Namonich"
git config --global user.email username@yandex.ru
```

Two ways to check configuration:
```bash
cat ~/.gitconfig
git config --list
```

## Basic Workflow
```bash
git init  # create repo
```
```bash
rm -rf .git  # remove repo
```
```bash
git status  # check state of the repo
```
```bash
git add  # add file(s) to index; --all - all files; . - all files from current dir
```
```bash
git commit  # create commit with redactor to make comment
```
```bash
git commit -m 'Initial commit'  # create commit with message
```
```bash
git log  # check history (output is in desc order by default); --reverse - asc order; --oneline - short way
```

## Synchronization
(repositories and branches)  

Check if the keys already exist:
```bash
cd ~
ls -la ~/.ssh
```

Instuction to generate SSH keys:
```bash
ssh-keygen -t ed25519 -C 'email address associated with your GitHub'
```
If the algorithm is not supported:
```bash
ssh-keygen -t rsa -b 4096 -C 'email address associated with your GitHub'
```

Is everything ok?
```bash
ssh -T git@github.com
```

Synchronizing a local Git repository with a remote one:
```bash
git remote add origin <url>
git remote -v
```

First push:
```bash
git push -u origin main  # after you should write just `git push`
```

## States
File/git status:
- untracked/untracked files
- tracked
- staged (staging area, index, cash)/changes to be commited
- modified/changes not staged for commit

Roadmap:
```mermaid
graph LR;
  untracked -- "git add" --> staged;
  staged -- "git restore --staged" --> untracked;
  staged -- "some changes" --> modified;
  staged -- "git restore --staged" --> modified;
  staged -- "git commit" --> tracked/commited;
  modified -- "git add" --> staged;
  modified -- "git restore" --> staged;
  modified -- "git restore" --> tracked/commited;
  tracked/commited -- "some changes" --> modified;
```

**Git file lifecycle**:
![Git file lifecycle](https://pictures.s3.yandex.net/resources/M2_T5_1686651284.png)

## Commit Styles
- corporate `<jira_task_id>: <message>`
- conventional commits `<type>: <message>`
- GitHub-style `Fix <task_num>, <message>`

[More info about Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4/#%D1%81%D0%BF%D0%B5%D1%86%D0%B8%D1%84%D0%B8%D0%BA%D0%B0%D1%86%D0%B8%D1%8F "Conventional Commits")

## Change Last Commit
```bash
git commit --amend --no-edit  # without comment changing
git commit --amend -m  # change comment in the last commit
```

## Rollbacks
To unstage:
```bash
git restore --staged <file>  # one file
git restore --staged .  # all files
```

For commits:
```bash
git log --oneline  # to check hash
git reset --hard <commit_hash>  # to rollback
```

**Rollback-schema** with `git reset --hard`:
![rollback-schema with git reset --hard](https://pictures.s3.yandex.net/resources/M2_T6_1686651127.png "git reset --hard")

*Be careful with git reset --hard command, you can lose some important information!*

Rollback files that were modified by accident:
```bash
git restore <file>
```

## Check Changes
Between files:
```bash
git diff  # modified files by default
git diff --staged  # staged files
```

Between commints:
```bash
git diff <commit1_hash> <commit2_hash>  # order is important
```
*You can use HEAD insted of the last commit hash.*

## .gitignore
Steps:
- create .gitignore file in the root directory
- fill it out

Templates:
```
# - a comment
__pycache__ - just a file
*, *.jpeg, docs/*/tmp - all files, all .jpeg files, all tmp files in docs subdirs
!, !doge.jpeg - except
? - one symbol
[...], [1-9], [a-z] - one symbol from brackets
/, /todo.txt - ignore file(s) only in the root directory
build/ - ignore only target directory
** - depth no matter (0 or more); to compare * - only one
```

Ignored files don't display with git status by default, but you can change it:
```bash
git status --ignored
```

[A collection of useful .gitignore templates.](https://github.com/github/gitignore ".gitignore templates")
