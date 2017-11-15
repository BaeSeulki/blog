---
title: vps和shadowsocks配置
date: 2017-09-26 17:50:28
categories:
- Setting
tags:
- Shadowsocks
---
1. 登录vps[管理界面](https://kiwivm.64clouds.com/main.php)
2. stop服务，重装系统，我选择了centos 7 64位
3. 系统重装好后，会给你一个root密码，如果忘记了可以重置。
4. ssh登录vps `ssh username@ipaddress -p port` ,输入初始的root密码。
5. 更改密码`passwd`
6. 接下来就是干正事了

```shell
cd
yum -y update
yum -y install gcc
yum -y install openssl-devel
yum -y install wget
yum install python-setuptools && easy_install pip
pip install shadowsocks

vi /etc/shadowsocks.json
# 创建配置文件，自行修改ip和端口，还有登录ss的密码。
{
"server":"xxx.xx.x.xx",
"server_port":7777,
"password":"xxxxxxx",
"timeout":300,
"method":"aes-256-cfb",
"fast_open":false,
"workers": 1
}

#设置开机启动
vi /etc/rc.local
ssserver -c /etc/shadowsocks.json -d start

#启动服务
ssserver -c /etc/shadowsocks.json -d start
#停止服务
ssserver -c /etc/shadowsocks.json -d stop
#重启服务
ssserver -c /etc/shadowsocks.json -d restart
``` 
客户端配置见[官网吧](https://shadowsocks.org/en/config/quick-guide.html)