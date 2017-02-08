---
title: 修复ubunut桌面
tags: 桌面, ubuntu
grammar_cjkRuby: true
---
，按下Ctrl+Alt+F2。这会让你进入一个命令行界面而不是默认的用户桌面界面。切换到命令行界面后，输入用户名和密码登录之后，使用下面的命令重装Unity桌面环境：

``` bash
sudo apt-get update
sudo apt-get install --reinstall ubuntu-desktop
sudo apt-get install unity
sudo shutdown -r now
```



