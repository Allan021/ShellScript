# linux

## comands

```sh

```

## Files configurations

### Bash

```bash
#.bash_history
#.bash_login
#.bash_profile
#.bashrc
alias open=xdg-open

#Git Alias
gcommit() {
    #do things with parameters like $1 such as
    git branch
    git add .
    git status
    sh ./test.sh && git commit -m "$1"
}
gpush(){
    gcommit "$1" && git push
}
gstash(){
    git add .
    git stash $@
}
greactpersonal(){
    git clone https://github.com/Allan021/$1
    mv $1 $2
    cd $2
    npm i
    npm start
}

#Utils alias
ipv4(){
hostname -I | awk '{print $1}'
}

alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'

#npm alias
alias npmst="npm start"
alias npmdv="npm run dev"

```

### ZSH

```zsh
# Theme of the terminal
ZSH_THEME="powerlevel10k/powerlevel10k"

# Plugins
 plugins=(git
 zsh-syntax-highlighting
 web-search dirhistory
 copyfile
 copypath
 copybuffer
 zsh-autosuggestions
 zsh-interactive-cd
 fzf-zsh-plugin
 command-time)
```

# Add Wifi to Debian

## 1.Add “non-free” component to /etc/apt/sources.list, for example:

```
# Debian 9 "Stretch"
deb http://httpredir.debian.org/debian/ stretch main contrib non-free
```

## 2.Update the list of available packages and install the firmware-iwlwifi package:

```sh
apt-get update; apt-get install firmware-iwlwifi
```

## 3.As the iwlwifi module is automatically loaded for supported devices, reinsert this module to access installed firmware:

```sh
modprobe -r iwlwifi; modprobe iwlwifi
```
