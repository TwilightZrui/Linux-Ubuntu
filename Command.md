## 解压.gz文件

```bash
gzip -d FileName.gz
```

## 查找文件

```bash
find ~/ -name Country.mmdb
```

## 回显某个应用的PID

```bash
ps aux | grep process_name
```

```bash
ps -ef | grep electron-ssr
pkill electron-ssr
```

## nvidia-smi 实时刷新 实时显示显存使用情况

```bash
watch -n 0.1 -d nvidia-smi     #每隔0.1秒刷新一次
nvidia-smi -l 1 #1ms刷新一次
```

## 动态实时监控GPU 的使用情况

```bash
pip install gpustat
watch --color -n1 gpustat -cpu
# gpustat基于nvidia-smi可以提供更美观简洁的展示
```

## 释放GPU显存

```bash
nvidia-smi -l 1  # 1ms速度实时nvidia-smi
fuser -v /dev/nvidia* # 查看运行在gpu上的所有程序
pmap -d PID # 查看具体这个进程调用GPU的情况
kill -9 PID # 强行关掉所有当前并未执行的僵尸进程
```

## 重启 Network-Manager 服务

```bash
sudo service network-manager restart
```

## 补依赖

```bash
sudo apt install -f
```

## 在当前路径下编译.cpp文件

```bash
g++ -o hello hello.cpp
./hello #在当前路径下运行编译后的可执行文件
```

## Net speed test

```bash
pip install speedtest-cli
which speedtest-cli | bash
```

## Accelerate git

```bash
github.com -->  github.com.cnpmjs.org
```

## ubuntu查看内核版本

```bash
cat /proc/version
```

## 查看linux系统CPU位数

```bash
sudo uname —m
```

```bash
getconf LONG_BIT
```

## 查看opencv版本

```bash
pkg-config --modversion opencv
```

## 本地与服务器间拷贝文件

从服务器传输到本地：

```bash
scp -P 50000 zhangrui@10.12.128.58:服务器上的文件  本地路径
```

从本地传输到服务器，-P 端口，-r传输目录

```bash
scp -P 50000 -r /home/twilight/rosbag_sim zhangrui@10.12.218.58:/data1/zhangrui
```

## 查看boost版本

```bash
dpkg -S /usr/include/boost/version.hpp
```

## 查看Eigen版本

```bash
gedit /usr/include/eigen3/Eigen/src/Core/util/Macros.h
```

## 快捷键

nautilus .： 在命令行端打开文件资源管理器
ctrl+H: 文件夹下，把隐藏文件显示出来

## 修改用户名

```bash
sudo passwd user
```

## 永久修改主机名

```bash
sudo gedit /etc/hostname
```

## 列出Ubuntu上的磁盘

```bash
sudo lsblk
```

## ubuntu卸载dpkg安装的软件

```bash
dpkg -l 查看软件安装名字
sudo dpkg --purge dropbox
```

## 修改用户名

```bash

```
