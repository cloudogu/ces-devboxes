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

Installs zsh with some preconfigurations and plugins. See [.zshrc](config/zshrc) for more information.

**Browser**

The devbox installs Chrome and Firefox as browsers. It also adds some basic extensions and bookmarks into Chrome.

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

**Snippet Manager with a preset of handy snippets**

The snippet manager ´pet´ is installed. You can edit your snippets with `pet edit` and search and apply snippets in the
CLI with the hotkey `CTRL+S`.

## Tested Operating Systems

* Ubuntu 22.04

## Prerequisites

* A fully configured YubiKey with valid GPG Key

## Getting started

It is possible to select only a subset of roles. For this you need to open the `playbook.yml` and comment out all unwanted roles. 

1. Copy the `vars_template.yml` file to `vars.yml` and change the required fields accordingly:
  - `mail`: Your e-mail address (xxx.xxx@cloudogu.com) used for git commits
  - `displayName`: Name used to display for git commits
  - `gpgKey`: Your gpg key id. Can be normally extracted with
      - `gpg --card-status | grep "sec#" | sed "s|.*\(0x[0-9A-Z]*\)\s.*|\1|g"`
  - `user`: The name of your Ubuntu user account
  - `mokutils.password`: The password used to import the newly generated MOK (Machine-Owner-Key).
2. Run the devbox: `./devbox`. After that it will ask for your sudo password and then apply the ansible playbook.
3. After executing the
   devbox you should reboot your machine. The machine management tool should start (blue screen). You should proceed by
  - `Press Any Key`
  - `Enroll MOK`
  - `Continue`
  - `yes`
  - Type the configured `mokutils.password`
  - `OK`
  - `Continue boot`
4. You should open a Terminal and set the font to `MesloLGS NF in Größe 11`.

**Note:**

It can happen that VirtualBox and VMWare could not load the required modules because of secure boot. Sometimes it can
happen that the generated MOK key ist not correctly imported after the devbox. However, this can be done manually fairly
easily:

```
sudo mokutil --import /mok/CES_MOCK.dep
```

Then you need to provide a password. After that reboot the machine and enroll the MOK key with the password you chose
before. After enrolling the mok VMWare and Virtualbox should work without any problems.
