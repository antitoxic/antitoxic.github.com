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
## Inline syntax highlighting
As described on [that plugin page](https://github.com/zsh-users/zsh-syntax-highlighting): a [Fish shell](http://fishshell.com/ ) like inline sytax highlighting
