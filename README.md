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

## step3
终端执行 `sudo rosdep init`

如果打印如下内容：

```
Recommended: please run
        
        rosdep update
```

则成功。如果你先前进行了某些初始化操作，系统将提示你删除对应文件。

***
# 2.运行rosdep update
使用国内源，依次执行以下脚本

```
rm update_rosdep_tsinghua.sh
wget https://gitee.com/ncnynl/rosdep/raw/master/update_rosdep_tsinghua.sh
sudo chmod +x ./update_rosdep_tsinghua.sh; sudo ./update_rosdep_tsinghua.sh
```

今后，可以正常执行 `rosdep update`





