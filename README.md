jidoka
======

# Wut? #

The following [Ansible](https://github.com/ansible/ansible) playbook does the following:

1. Installs [Homebrew](http://brew.sh/)
1. Installs some brews:
  * [tmux](http://tmux.sourceforge.net/) - terminal multiplexer
  * [vim](http://www.vim.org/) - text editing
  * [zsh](http://www.zsh.org/) - system shell
1. Grabs the latest dotfiles from my github [joethemongoose](https://github.com/joethemongoose/dotfiles)
  * Changes zsh to default to vi bindings with graphical notification of mode
  * Antigen with various modules (language completitions)
  * etc
1. Changes default shell to [zsh](http://www.zsh.org/)
1. Installs [Antigen](https://github.com/zsh-users/antigen) for zsh fun
1. Installs [RVM](https://rvm.io/rvm) - Ruby management
1. Installs [NVM](https://github.com/creationix/nvm) - NodeJS management
1. Installs [GVM](https://github.com/moovweb/gvm) - GoLang management
1. Installs [Janus](https://github.com/carlhuda/janus) - VIM plugin management plus defaults

## Prereq ##
Ensure the OSX Xcode command line tools are installed

1. Do it maually

    xcodebuild -license; xcode-select --install

1. Automate it [here](https://gist.github.com/d7an/9756475)

### Install Ansible ###

Installing Ansible should be as easy as

    pip install -U ansible

## Running ##

    ansible-playbook jidoka.yml -K

### config ###

The only real configuration options avaiable are the versions of the node/ruby/go to be installed. They can be changed by editing 

    roles/jidoka/vars/main.yml.

### todo ###

1. need to make more components selectable such as the antigen modules

#### contact ####

Questions/Comments/Priases can be sent to me at <joe@unicornclouds.com>
