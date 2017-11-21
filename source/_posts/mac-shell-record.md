---
title: Shell 相关问题
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

### Java
1. java怎么执行shell脚本

[Java执行shell遇到的各种问题](http://blog.csdn.net/caohaicheng/article/details/22928297) 尤其是问题3，脚本中有关联脚本时，注意运行环境是当前java类的运行目录，而不是shell脚本的。



### 脚本常用技巧
#### 1. bash set 命令
[Bash 脚本 set 命令教程](http://www.ruanyifeng.com/blog/2017/11/bash-set.html)  
常用方法：  

```shell
# 写法一
set -euxo pipefail

# 写法二
set -eux
set -o pipefail
```
或者执行脚本时传入参数

```shell
$ bash -euxo pipefail script.sh
```

#### 2. 系统关机和重启
[系统关机和重启](http://rackie386.blog.51cto.com/11279229/1930686)

```shell
halt [OPTIONS...]
poweroff [OPTIONS...]
reboot [OPTIONS...]
shutdown [OPTIONS...] [TIME] [WALL...]
init [OPTIONS...] {COMMAND}
```
> 
推荐使用的关机命令：  
halt，poweroff，init 0，shutdown，shutdown +5 "warning system will be shutdown after 5m"  
推荐使用的重启命令：  
reboot，ini 6，shutdown -r  

