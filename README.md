# CES-Devboxes

This repository contains ansible roles to setup a new development machine for the Cloudogu EcoSystem developers.

The playbook will install and configure the following tools:

* zsh (configured with [oh-my-zsh](https://github.com/robbyrussell/oh-my-zsh))
* tmux (inspired from [.tmux](https://github.com/gpakosz/.tmux))
* vim (configured with [vimrc](https://github.com/amix/vimrc))
* docker
* vagrant
* virtual box
* packer
* terraform
* gcloud, kubectl and kubectx
* gpg
* git
* mercurial
* java and maven
* node.js
* golang
* vscode
* Intellij
* and many more

## Tested Operating Systems

* Ubuntu (tested on 22.04)

## Prerequisites

* Ansible >= 2.6

### Ubuntu

Install ansible

```bash
sudo add-apt-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```

## Getting started

Just run the `devbox` script, on the first run it will ask some question to personalize the installed configurations.
After that it will ask for your sudo password and then apply the ansible playbook. 

## Tags

Its also possible to only apply certain tags, e.g.

`devbox --tags zsh`

See [playbook](playbook.yml) for existing tags.
