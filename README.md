# Git Cheat Sheet
This repository is for refreshing your memory about Git.

Git is a _Global Information Tracker_ or _Goddamn Idiotic Truckload of sh*t_, depends on your mood.

## Basic CLI
Commands:
* __pwd__ - _print working directory_
* __cd__ - _change directory_
* __ls__ - _list directory contents_
  * __ls -a__ - _all_
  * __ls -l__ - _long_
* __touch__ - _create file_
* __mkdir__ - _create directory_
  * __mkdir -p__ - _create multiple directories_
* __cp__ - _copy_
* __mv__ - _move or rename_
* __cat__ - _concatenate and print_
* __rm__ - _remove a file_
  * __rm -rf__ - _remove a not empty directory (r - recursive, f - force)_
* __rmdir__ - _remove an empty directory_

Symbols:
* __/__ - _root directory_
* __~__ - _home directory (tilda)_
* __..__ - _parent directory_
* __.__ - _current directory_

Make your work faster:
* __&&__ - _run more than one cmd (double ampersand)_
* __↑ ↓__ - _teminal memory AKA buffer_
* __Tab__ - _autocomplete_

## Installing Git
* __sudo apt-get update && sudo apt-get install git-all__
* __git version__

## Setting Up Git
Write who are you:
* __git config --global user.name__ _"User Namonich"_
* __git config --global user.email__ _username@yandex.ru_

Two ways to check configuration:
* __cat ~/.gitconfig__
* __git config --list__

## First Steps With Git
Initialize/remove git repository:
* __git init__ - _create repo_
* __rm -rf .git__ - _remove repo_

Check repo state/add files to index:
* __git status__ - _check state of the repo_
* __git add__ - _add files to index_
  * __git add__ file_name - _add file to index_
  * __git add --all__ - _add all files to index_
  * __git add .__ - _add all files from the current dir to index_

Commit files:
* __git commit__ - _open redactor and create commit_
  * __git commit -m__ 'Info message' - _create commit with message_

Check repo history:
* __git log__ - _check history (output is in desc order by default)_
  * __git log --reverse__ - _make output in asc order_
  * __git log --oneline__ - _check short history_
