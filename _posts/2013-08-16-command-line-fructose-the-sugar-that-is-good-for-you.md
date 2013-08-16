---
published: true
layout: post
title: Happy command line
category: dev
tags: "usability,command line, terminal, server"
---

The healthy sugar that you can use in your command-line work. Taking a look at some convinient tweaks.

## Few notes
The code samples are targetting debian based OSs and it was tested on Ubuntu 13.04.

## Removing long login greeting message.
That thing:

```
Linux steve 2.6.18-4-686 #1 SMP Wed May 9 23:03:12 UTC 2007 i686

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Last login: Fri Aug 24 09:38:52 2007 from localhost.localdomain
ubuntu@anton-laptop$ ▌
```

or something similar that appears every time you login (especially remotely).

Which is the least - distracting. So to remove it:

```
touch ~/.hushlogin
```

## Some packages to start with

```
sudo apt-get install zsh fortune cowsay htop git
```

## Install a `zsh` framework and set it as default shell

```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | zsh
sudo chsh -s `which zsh` ubuntu # where ubuntu is your username
```

to have [features like those here](http://staunchrobots.com/blog/blog/2012/09/06/switch-to-zsh/).

You could also [pick another theme](https://github.com/robbyrussell/oh-my-zsh/wiki/Themes). 
## Some `oh-my-zsh` plugins
Just edit the plugins variable in `.zshrc`. You can set some automatically via:

```
sed -i.bak 's/^plugins=(.*/plugins=(<<PLUGIN NAMES SEPARATED BY A SPACE>>)/' ~/.zshrc
```

On most of the dev machines I'm running this:

```
sed -i.bak 's/^plugins=(.*/plugins=(git django python pip emoji-clock zsh-syntax-highlighting bower)/' ~/.zshrc
```

## Inline syntax highlighting
As described on [zsh-syntax-highlighting plugin page](https://github.com/zsh-users/zsh-syntax-highlighting) it is a [Fish shell](http://fishshell.com/ ) like inline sytax highlighting

Basically it does coloured command line prompt:

![Syntax highlighting of the command prompt](http://dl.dropbox.com/u/4296335/Selection_003.png)

Install:

```
mkdir -p ~/.oh-my-zsh/custom/plugins
git clone git://github.com/zsh-users/zsh-syntax-highlighting.git  ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

## Visual disk usage representation 
A histogram/barchart of disk space usage

![CDU](http://dl.dropbox.com/u/4296335/Selection_005.png)

Install:

```
tar zxv < (wget -q -O - http://arsunik.free.fr/pkg/cdu-0.37.tar.gz)
sudo make install
```

## Remove silly `oh-my-zsh` autocorrecting
[Yep, it's annoying.](https://github.com/robbyrussell/oh-my-zsh/issues/534) Remove it via:

```
echo "unsetopt correct_all" >> ~/.zshrc
echo "unsetopt correct" >> ~/.zshrc
```

## Keep your spirit up
[Fortunes](http://en.wikipedia.org/wiki/Fortune_%28Unix%29) are nice but sometimes depressing or quite often not really good-hearted. I prefer to put up a login with a friendly fixed message to remind me why am I doing all this. Something like 

>> You're coverd in code and it's not easy, but you're building a better world.

Add this to your login with by adding:

```
echo -e "\e[00;33m" 
echo "You're coverd in code and it's not easy, but you're building a better world." | cowsay -f $(echo "turtle\nstegosaurus\nbud-frogs" | shuf -n1)
echo -e "\e[00m" 
```

to `~/.zshrc`. This will result into a greeting with a cowsay animal every time you login:

![Greeting](http://dl.dropbox.com/u/4296335/ubuntu%40anton-laptop%3A%20~_007.png)