### 设置网卡优先级

有线网无线网同时连接，设置优先级：

```bash
route -n
#通过网卡名称指定metric值
sudo ifmetric wlp1s0 90
```

[ubuntu18.04同时使用多个有线网络和无线网络时如何设置优先级](https://blog.csdn.net/wen_1_wen/article/details/121757313)

[Linux笔记：Ubuntu18.04有线网络和无线网络的优先级设置](https://blog.csdn.net/weixin_44444810/article/details/124768090)

### 修改VNC分辨率

```bash
# 命令行设置单个窗口
vncserver -geometry 1920x1080
vncserver -geometry 3840x2160
vncserver -virtual -geometry 3840x2160:87

# 永久修改
code /usr/bin/vncserver geometry = "1920x1080"

```

### 关闭指定VNC server 进程

```bash
# 查vnc服务的进程
ps -ef | grep -i vnc | grep -v grep
# 杀进程：
kill -9 进程号
```

### 本地与服务器间拷贝文件

从服务器传输到本地：

```bash
scp -P 50000 zhangrui@10.12.128.58:服务器上的文件  本地路径 
```

从本地传输到服务器，-P 端口，-r传输目录

```bash
scp -P 50000 -r /home/twilight/rosbag_sim zhangrui@10.12.218.58:/data1/zhangrui 
```

将SSH公钥上传到Linux服务器
可以使用ssh-copy-id命令来完成．
```bash
ssh-copy-id username@remote-server
```

