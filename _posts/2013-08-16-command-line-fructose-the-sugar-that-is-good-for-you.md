---
published: false
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
## Setting `zsh` as default shell
```
sudo chsh -s `which zsh` ubuntu # where ubuntu is your username
```
## Visual disk usage representation 
A histogram/barchart of disk space usage
![CDU](/http://dl.dropbox.com/u/4296335/Selection_005.png)

Install:
```
tar zxv < (wget -q -O - http://arsunik.free.fr/pkg/cdu-0.37.tar.gz)
sudo make install
```
## Inline syntax highlighting
As described on [zsh-syntax-highlighting plugin page](https://github.com/zsh-users/zsh-syntax-highlighting) it is a [Fish shell](http://fishshell.com/ ) like inline sytax highlighting

Basically it does coloured command line prompt:
![Syntax highlighting of the command prompt](/http://dl.dropbox.com/u/4296335/Selection_003.png)