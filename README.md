# Git Cheat Sheet
This repository for refreshing your memory about Git.

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
* __/__ - _root directory__
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
