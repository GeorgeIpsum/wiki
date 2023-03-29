---
description: just the basic stuff
---

# cheat sheet

## Config

### Configure user info for all local repos

```bash
git config --global user.name "[name]"
git config --global user.email "[email]"
```

### Colorize CLI output

```bash
git config --global color.ui auto
```

## Looking Inside A Repo

### List new/ modified files

```bash
git status
```

Use `-s` for a color coded and less verbose/ more succint list of modifiied or new files.

To actually see the differences of unstaged files:

```bash
git diff
```

and add the `--staged` flag if you want to get output for staged files

## Branches

### Renaming a branch

Assuming you have the branch you want to rename checked out:

```bash
git branch -m <new_name>
```

Publish if you've pushed the old branch name to remote:

```bash
git push origin --delete <old_name>
git push origin -u <new_name>
```

## Merge pull request (CLI)

```bash
git checkout master
git merge --no-ff <branch_name>
git push origin master
```

## Other Resources

![Found at http://zeroturnaround.com/rebellabs/git-commands-and-best-practices-cheat-sheet/](<../../.gitbook/assets/image (1).png>)

__[_PDF found here_](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)__

{% file src="../../.gitbook/assets/github-git-cheat-sheet.pdf" %}
Or you can just download it
{% endfile %}
