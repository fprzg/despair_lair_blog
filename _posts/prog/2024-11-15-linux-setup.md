---
layout: page
title: Linux Setup
---

This page is intended as a (non comprehensive) list of things I have to install on every fresh linux installation.

# SSH

Add ``eval `ssh-agent -s` `` to `.profile` to start a ssh-agent session.

# Programming Languages

## Golang

`TODO(Farid): What should I do if I want several versions of golang? (Maybe something with .env and direnv).`
* **$GOPATH**: `$HOME/.local/share/go`
* **$GOROOT**: `/usr/share/go`


## Ruby
Installing `ruby-installer`
```bash
curl asdfasdf
```

### Environment Variables

* **$GEM_HOME**: Set it to the directory where you want to store the ruby gems.
* **$RUBIES_DIR**: This one has nothing to do with ruby-installer, but I use it to store the `rubies` directory (where ruby-installer saves the different version of ruby in your computer, by default is `$HOME/.rubies`). I set it to `$HOME/.local/share/rubies`

### Ruby Installation
```bash
ruby-installer
```

## Node


### NVM
Node version manager.
```bash
export NVM_DIR="$HOME/.local/share/nvm" && (
  git clone https://github.com/nvm-sh/nvm.git "$NVM_DIR"
  cd "$NVM_DIR"
  git checkout `git describe --abbrev=0 --tags --match "v[0-9]*" $(git rev-list --tags --max-count=1)`
) && \. "$NVM_DIR/nvm.sh"
```

then
```bash
nvm install node
```