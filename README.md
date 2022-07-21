# CES-Devboxes

This repository contains ansible roles to setup a new development machine for the Cloudogu EcoSystem developers.

The playbook will install and configure the following tools:

**IDEs**

- IntelliJ Ultimate
- VSCode with some convenient plugins

**Working with VMs**

- Virtualbox (supports Secure-Boot)
- VMWare Workstation Pro 16 (supports Secure-Boot)
- Hashicorp
  - packer
  - terraform
  - vagrant

**Terminal**

Installs zsh with some preconfigured things and plugins. See [.zshrc](config/zshrc) for more information.

**Browser**

The devbox install Chrome and Firefox as Browsers. It also adds some basic extensions and bookmarks into Chrome.

**SDK Manager**

- Jabba with preinstalled Java8 and Java11
   - Also adds two aliases `java8` and `java11` for a convenient switch between versions.
- gvm with newest Go version being installed
- nvm with newest Node version being installed

**k8s**

- kubectl
- gcloud
- k9s

**Recording tools**

- gif image optimization: `gifsicle` 
- gif screen recording: `peek`
- video screen recording: `kazam`

## Tested Operating Systems

* Ubuntu (tested on 22.04)

## Prerequisites

* Ansible >= 2.6

## Getting started

1. Copy the `vars_template.yml` file from the root directory as `vars.yml` and change the required fields accordingly:
   - `mail`: Your E-Mail (xxx.xxx@cloudogu.com) used for git commits
   - `displayName`: Name used to display for git commits
   - `gpgKey`: Your gpg key id. Cen be normally extracted
   - with (`gpg --card-status | grep "sec#" | sed "s|.*\(0x[0-9A-Z]*\)\s.*|\1|g"`)
   - `user`: The current name of the user
   - `mokutils.password`: The password used to import the newly generated MOK (Machine-Owner-Key). 
2. Run the devbox: `.\devbox`. After that it will ask for your sudo password and then apply the ansible playbook.
3. After executing the
   devbox you should reboot your machine. The machine management tool should start (blue screen). You should proceed by
   - `Press Any Key`
   - `Enroll MOK`
   - `Continue`
   - `yes`
   - Type the configured `mokutils.password`
   - `OK`
   - `Continue boot`
