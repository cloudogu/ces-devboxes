### Linux Utility Software 

* restic
* thefuck https://github.com/nvbn/thefuck
* btrfs-progs (für cesapp)

* git, gotop, jq, yq, ctop
* HTTP Anfragen speichern/testen/abfeuern (mit GUI), für CLI curl
   * Postman (gibt OSS Alternativen) 
   * Insomnia
* K9s (optional mit Kubernetes-Rolle)
* gopass / +keypass
* Ubuntu Monitoring Leiste oben
* JExplorer (für ldap)

* gutils
~~* zoiper~~

* gif-Erstellung: peek
* PDF Viewer
* (LibreOffice)

### Browser

* Tampermonkey vorinstalliert
* Chromium
* Firefox
* CES-Developer Lesezeichen erstellen/importieren
   * Workmeet 
   * Cloudogu Infrastruktur
      * GCE Dinge
      * StageX
      * Prod
      * Bucket für docs
      * Docs
      * Blueprint PR
   * Cheatsheets
      * Zeiterfassung: https://www.zeiterfassungonline.com/stunden-rechner.html 
      * Docker: https://opensourcelibs.com/lib/docker-notes
      * OpenSSL: https://www.freecodecamp.org/news/openssl-command-cheatsheet-b441be1e8c4a/
      * Bash: https://devhints.io/bash
      * Testing Regular Expressions: https://www.regextester.com/
      * SED-Tester: https://sed.js.org/index.html
      * Explain-Shell: https://explainshell.com/

### VM Dinge

* VMWare Workstation Pro
* (ggf. QEMU)
* Virtualbox
* Packer
* Vagrant (virtualbox-guest additions plugin??)

### ZSH

Plugins:
- Autocompletion:
   - git
   - docker/compose
   - kubectl / kubecontext
   - gitflow
- savepaste (https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/safe-paste)
- fzf

### SDKs

* (python 2)
* Ruby (rvm) / rake
* NVM / yarn
* Go (gvm)
* Java (jabba/sdkman)

### Snippet Manager

- Jeder für sich

### Alias

- ll
- vagrant aliases
alias für sdk versionen java8 java11 node11 node14 go18 go14
alias goodbye="shutdown -h now"
alias gbforce="systemctl poweroff -i"
alias rbforce="systemctl reboot -i"
alias java8="sudo update-alternatives --set java /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java"
alias java11="sudo update-alternatives --set java /usr/lib/jvm/java-11-openjdk-amd64/bin/java"
alias untar="sudo tar -xvzf"
