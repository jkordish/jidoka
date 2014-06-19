jidoka
======

## Prereq
Ensure the OSX Xcode command line tools are installed

1. Do it maually

    xcodebuild -license; xcode-select --install

1. Automate it [here](https://gist.github.com/d7an/9756475)

### Install Ansible

Installing Ansible should be as easy as

    pip install -U ansible

## Running

    ansible-playbook jidoka.yml -K -i hosts

### config

The only real configuration options avaiable are the versions of the node/ruby/go to be installed. They can be changed by editing roles/jidoka/vars/main.yml.

### notes

Had a terrible time getting [gvm](https://github.com/moovweb/gvm) to work like [nvm](https://github.com/creationix/nvm) and [rvm](https://rvm.io/rvm).

It appears it is the way in which the "install" script operates. I found it was way simplier to just ignore the error during the install then to essentially fix it. I left some comments and some code commented out if anyone is interested.
