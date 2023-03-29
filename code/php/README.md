---
description: mom... do we HAVE to use php...
---

# php

## Installing php

### On macOS

brew everything:

```bash
# list installed php packages and uninstall any (just use the first 2 to only list)
brew list | grep php | while read x; do brew uninstall --force $x; done

# also potentially might need to run this
rm -rf /usr/local/Cellar/php

# clean up launch agents
rm ~/Library/LaunchAgents/hombrew.mxcl.php*
sudo rm /Library/LaunchDaemons/homebrew.mxcl.php*

brew untap homebrew/php
brew cleanup
brew update
brew doctor # just making sure

ps ax | grep php # reboot if php daemons still running

brew install php
```

this installs

* `/usr/local/opt/php/lib/httpd/modules/libphp7.so` - the apache module
* `/usr/local/bin/php` - command line
* `/usr/local/bin/php-fpm` - fastcgi binary

If homebrew isn't available for whatever reason (for php 7.3):

```bash
curl -s http://php-osx.liip.ch/install.sh | bash -s 7.3
```

This only installs php and not apache (but does use macos' native apache install)

### On Windows

Before you do this, consider the following:

* Don't.
* get WSL, look forward to "installing on linux"
* seriously, why do you need a native php install on your windows machine?

Still need to install on windows? [Download the source from here](https://windows.php.net/download/).

[Or, even better yet, use XAMPP](https://www.apachefriends.org/index.html).

### On Linux

This should only work for Debian-based distros since I have never seen a red hat in my entire life.

```bash
sudo apt-get update && apt-get ugprade # just in case

# skip this part if you need only 7.0
apt-get install software-properties-common
add-apt-repository ppa:ondrej/php
apt-get update

apt-get install php7<.x>
```

It gets complicated for rpm distros. So google it.
