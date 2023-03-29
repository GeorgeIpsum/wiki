---
description: push --force; never again
---

# git

## Installing git

### On macOS

Allegedly since OS X 10.9 git will install itself if its not installed already by just running the command in the shell:

```bash
git --version
```

I can't verify that this is actually the case since... I don't recall ever having to install git on a mac. So I'm guessing this works.

### On Windows

Via `chocolatey`:

```bash
choco install git
```

Or you can install it from the [Git for Windows project](https://gitforwindows.org/).

### On Linux

For Debian-based distros (Ubuntu, etc):

```bash
sudo apt install git-all
```

For Fedora/ RPM-based distros (RHEL, CentOS, etc):

```bash
sudo dnf install git-all
```

