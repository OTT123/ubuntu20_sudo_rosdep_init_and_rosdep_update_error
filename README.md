# ubuntu20_sudo_rosdep_init_and_rosdep_update_error
***
## 问题描述
ros安装过程中，执行
```
sudo rosdep init
rosdep update
```
大陆用户在运行第一条命令常常会报错：`website may be down`，作者即使科学上网也不能解决这个问题。下文解决这个问题。

# 1.运行sudo rosdep init
## step1 
进入网站`https://www.ipaddress.com/`， 查询 `raw.githubusercontent.com` 所在IP地址(**IPv4**)

## step2
终端中执行 `sudo gedit /etc/hosts`

添加如下内容

`xxx.xxx.xxx.xxx raw.githubusercontent.com`

如下图
![image](https://github.com/OTT123/ubuntu20_sudo_rosdep_init_and_rosdep_update_error/blob/main/pic/host_exp.png)
