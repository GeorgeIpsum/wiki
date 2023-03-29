---
description: homebrew is the greatest software Of All Time
---

# macos

## Write some defaults

```bash
# Disable press-and-hold for keys
defaults write -g ApplePressAndHoldEnabled -bool false

# Use Airdrop over all interfaces
defaults write com.apple.NetworkBrowser BrowseAllInterfaces 1

# Show ~/Library folder
defaults write com.apple.Finder FXPreferredViewStyle Nlsv

# Set fast key repeat
defaults write NSGlobalDomain KeyRepeat -int 1
```

## Acquire RVM

```bash
\curl -sSL https://get.rvm.io | bash -s stable --ruby
```

## Acquire Homebrew

```bash
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Acquire Cask

```bash
tap homebrew/cask
brew install caskroom/cask/brew-cask
```

### Execute Brewfile

```bash
brew bundle
```

{% code title="Brewfile" %}
```
tap homebrew/core
tap homebrew/dupes
tap homebrew-ffmpeg/ffmpeg
tap sass/sass

brew ant
brew openssl
brew php
brew composer
brew python
brew pip
brew opting
brew mysql
brew postgresql
brew ffmpeg
brew nmap
brew awscli
brew speedtest-cli
brew watch
brew neofetch
brew nvm
brew yarn
brew go
brew webp
brew imagemagick
brew youtube-dl
brew lua
brew wine
brew rust
brew parallel
brew p7zip
brew watchman
brew httpie
brew lolcat
brew typescript
brew sox
brew gmp
brew cmake
brew cowsay
brew duck
brew geoip
brew rtv
brew streamlink
brew telnet
brew tree
brew trash
brew watch
brew sass/sass/sass
```
{% endcode %}

### Execute Caskfile

```bash
brew bundle Caskfile
```

{% code title="Caskfile" %}
```
tap homebrew/cask-fonts

cask font-fira-code
cask java
cask google-chrome-canary
cask iterm2
cask visual-studio-code-insiders
cask mpv
cask xquartz
cask spotify
cask ngrok
cask transmission
cask cyberduck
cask discord
cask balenaetcher
cask firefox-developer-edition
cask intellij-idea
cask insomnia
cask figma
cask minecraft
cask supercollider
cask the-unarchiver
cask gifcapture
cask webpquicklook
cask streamlink-twitch-gui
cask qlmarkdown
cask quicklook-json
cask xquartz
```
{% endcode %}
