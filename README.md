# Git Cheat Sheet
This repository is for refreshing your memory about Git.

Git is a _Global Information Tracker_ or _Goddamn Idiotic Truckload of sh*t_, depends on your mood.

---

## Basic CLI
### Commands:
```bash
pwd  # print working directory
```
```bash
cd  # change directory
```
```bash
ls  # list directory contents
```
```bash
ls -a  # all
```
```bash
ls -l  # long
```
```bash
ls -la  # all + long
```
```bash
touch  # create a file
```
```bash
mkdir  # create a dir
```
```bash
mkdir -p  # create dirs
```
```bash
cp  # copy
```
```bash
mv  # move
```
```bash
cat  # concatenate and print
```
```bash
rm  # remove a file
```
```bash
rm -rf  # remove a not empty dir; r - recursive; f - force
```
```bash
rmdir  # remove an empty dir
```

### Symbols:
- **.** - *current directory*
- **..** - *parent directory*
- **~** - *home directory (tilda)*
- **/** - *root directory*

### Make Your Work Faster:
- **&&** - *run more than one cmd (double ampersand)*
- **↑ ↓** - *teminal memory AKA buffer*
- **Tab** - *autocomplete*

---

## First Steps With Git
### Installing
```bash
sudo apt-get update && sudo apt-get install git-all
git version
```

### Setting Up
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

### Basic Workflow
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
git commit  # create commit with redactor
```
```bash
git commit -m 'Initial commit'  # create commit with message
```
```bash
git log  # check history (output is in desc order by default); --reverse - asc order; --oneline - short way
```

### Synchronization
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
