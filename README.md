# Install software
## Git
```bash
sudo apt install git
```

### Setup ssh keys
```bash
ssh-keygen -t rsa -C "jvsegarra@gmail.com"
```

## Fish shell
Follow instructions in <https://github.com/fish-shell/fish-shell>

```bash
sudo apt-add-repository ppa:fish-shell/release-3
sudo apt-get update
sudo apt-get install fish
```

### Make fish the default shell
```bash
chsh -s /usr/bin/fish
chsh -s /usr/local/bin/fish (if the previous one does not find fish)
```

### Config fish background
```bash
fish_config
might need to install -> sudo apt install python3-distutils -y 
```

### Install fish theme
Download oh-my-fish
```bash
curl -L https://get.oh-my.fish | fish
```

Install oh-my-fish themes
```bash
omf install clearance
```

## Docker
Install docker from <https://docs.docker.com/engine/install/ubuntu/>

### Install docker-compose
```bash
sudo apt install docker-compose
```

## Java / JDK


## Intellij / Pycharm
Install from software center or <https://snapcraft.io/store>

## Postman
```bash
sudo snap install postman
```

## Querypie
Download and install from <https://www.querypie.com/>


# Settings
## Bash

PS1='${debian_chroot:+($debian_chroot)}\[\033[0;32m\]\u\[\033[0;36m\] @ \[\033[0;36m\]\h \w\[\033[0;32m\]$(__git_ps1)\n\[\033[0;32m\]└─\[\033[0;32m\] \$\[\033[0;32m\] ▶\[\033[0m\] '

## Git

alias gtree='git log --graph --abbrev-commit --decorate --date=relative --format=format:'\''%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)'\'' --all'
