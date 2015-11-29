jidoka
======

## Purpose ##

Decided not to long ago that I needed to manage how my OSX machine was configured. This attempts to recreate my current working machine from scratch.

### What's it do exactly? ###
The following [Ansible](https://github.com/ansible/ansible) playbook does the following:

1. [Homebrew](http://brew.sh/) - OSX package manager
  1. [Cask](http://caskroom.io/)  - Extends Homebrew to binaries
  1. [Fonts](https://github.com/caskroom/homebrew-fonts) - Extends Homebrew to Fonts
1. Installs some brews:
  * [tmux](http://tmux.sourceforge.net/) - terminal multiplexer
  * [vim](http://www.vim.org/) - text editing
  * [zsh](http://www.zsh.org/) - system shell
  * For a full list [see here](https://raw.githubusercontent.com/jkordish/jidoka/master/roles/jidoka/vars/main.yml)
1. Grabs the latest dotfiles from my github [jkordish](https://github.com/jkordish/dotfiles)
  * Changes zsh to default to vi bindings with graphical notification of mode
  * Antigen with various modules (language completitions)
  * etc
1. [Antigen](https://github.com/zsh-users/antigen) for zsh fun
1. [RVM](https://rvm.io/rvm) - Ruby management
1. [NVM](https://github.com/creationix/nvm) - NodeJS management
1. [GVM](https://github.com/moovweb/gvm) - Go management
1. [Multirust](https://github.com/brson/multirust) - Rust management
1. [jEnv](https://github.com/gcuisinier/jenv) - Java installation management.
1. Installs [Janus](https://github.com/carlhuda/janus) - VIM plugin management

## Prereq ##
Ensure the OSX Xcode command line tools are installed

1. Do it manually

    $ xcodebuild -license && xcode-select --install

1. Or automate it via this Ruby gem [xcode-install](https://github.com/neonichu/xcode-install)

### install pip ###

    $ curl -sSL https://bootstrap.pypa.io/get-pip.py | python - --user

### Install Ansible ###

Ensure you are using Ansible version 2 or greater.

Installing Ansible should be as easy as

    $ pip install --user -U ansible

## Running ##

    $ ansible-playbook -v jidoka.yml

### config ###

The only real configuration options available are the versions of the node/ruby/go to be installed. They can be changed by editing

    roles/jidoka/vars/main.yml.

### todo ###

1. need to make more components selectable such as the antigen modules

#### contact ####

Questions/Comments/Priases can be sent to me at <joe@unicornclouds.com>
