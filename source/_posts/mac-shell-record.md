---
title: Shell Setting Record
date: 2017-09-26 12:03:53
categories:
- Shell
tags:
- Shell
- Mac
---

最近再整理自己mac上的配置时候，发现有点（很）乱，包括版本管理之类的。所以打算重新整理一下，各个常用工具的配置啊，balabala之类的。
### shell
首先从shell着手吧，由于使用了oh-my-zsh，所以基于zsh做配置。  
打开zsh终端：
  
```	shell
➜ echo $SHELL
/bin/zsh
```
bash，sh，zsh，那么你的用的可能就是Bourne Shell的一个变种。  
Bourne Shell(简称sh)  Unix默认的Shell，是其他Shell的开发基础。  
在Bourne Shell下有三种配置文件：
> / ect/profile  
> /ect/bashrc  
> ~/.bash_profile  
 
Linux里边是.bashrc 而MAC 是.bash_profile 。  
`/ect/profile` (一般不建议修改这个文件)，全局（公有）配置，不管是哪个用户，登陆是都会读取该文件。  
`/etc/bashrc` 一般在这个文件中添加系统级环境变量，全局（公有）配置，bash shell执行时，不管是何种方式，都会读取此文件。  
~/.bash_profile 一般在这个文件中添加用户级环境变量。每个用户都可使用该文件输入专用于自己使用的shell信息,当用户登录时,该文件仅仅执行一次。    
~/.zshrc 在.zshrc文件末尾增加.bash_profile的引用：`source ~/.bash_profile`

### python
用brew安装的python2.7.14 和3.6.2。  
但为了管理第三方包方便点，决定试试anaconda。



