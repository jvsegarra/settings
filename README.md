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

## Bash shell
Follow instructions in <https://github.com/ohmybash/oh-my-bash>

### Bash-it
Follow instructions in <https://github.com/Bash-it/bash-it>

```bash
git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
~/.bash_it/install.sh
```
### Switch themes in Bash-it
go to ```~/.bashrc``` and change line export ```BASH_IT_THEME='<theme>'``` (eg. ```BASH_IT_THEME='sexy'```)

(careful, theme names go in lowercase)

then ```source ~/.bashrc```

## Bash utilities
<https://dev.to/heraldofsolace/replace-your-existing-unix-utilities-with-these-modern-alternatives-2bfo>

## Docker
### Install and setup
Install docker from <https://docs.docker.com/engine/install/ubuntu/>

Add user to docker group:
```bash
sudo groupadd docker
sudo usermod -aG docker ${USER}
```
Then log out and log back in

### Install docker-compose
```bash
sudo apt install docker-compose
```

## Java / JDK
Install JRE
```bash
sudo apt install default-jre
java -version
```

Install JDK
```bash
sudo apt install default-jdk
javac -version
```

Determine where Java is installed
```bash
sudo update-alternatives --config java
```

### For bash shell
Copy the path from your preferred installation and add the following line at the end of /etc/environment, making sure to replace the highlighted path with your own copied path, but do not include the /bin portion of the path:
```bash
JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64" (without /bin/java)
```

Now reload this file to apply the changes to your current session:
```bash
source /etc/environment
echo $JAVA_HOME
```

### For fish shell
Edit fish config
```bash
vim ~/.config/fish/fish.config
```

And add the following line with the path to the current Java installation, without the /bin portion of the path:
```bash
set -x JAVA_HOME "/usr/lib/jvm/java-11-openjdk-amd64"
```

Now reload this file to apply the changes to your current session:
```bash
source ~/.config/fish/fish.config
echo $JAVA_HOME
```

### Node / Typescript
```bash
sudo snap install node --classic

# Typescript compiler
sudo npm install -g typescript
```

### Python
```bash
sudo snap install python<version>

# Setup default version with alias
alias python='/usr/bin/python3.9'
```
https://linuxconfig.org/how-to-change-from-default-to-alternative-python-version-on-debian-linux

## Flathub.org
Install:
- Intellij / Pycharm
- Postman
- Slack
- Telegram
- Todoist
- ...

### Slack channels
kotlinlang, BcnEng, pyBCN, typescript

## Hyper
### Download .deb
Download .deb from <https://hyper.is/> and install it

### Setup
Open Preferences and edit the next keys in .hyper.js:
```javascript
cursorColor: '#FDFA7C'
```
Install hyper-material-theme theme. Run this command in Hyper:
```bash
hyper i hyper-material-theme
```

# Settings
## Bash

PS1='${debian_chroot:+($debian_chroot)}\[\033[0;32m\]\u\[\033[0;36m\] @ \[\033[0;36m\]\h \w\[\033[0;32m\]$(__git_ps1)\n\[\033[0;32m\]└─\[\033[0;32m\] \$\[\033[0;32m\] ▶\[\033[0m\] '

## Git

alias gtree='git log --graph --abbrev-commit --decorate --date=relative --format=format:'\''%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)'\'' --all'
