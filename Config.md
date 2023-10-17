## 修改默认分辨率
```bash
sudo gedit /etc/default/grub
GRUB_GFXMODE=1920x1080
sudo update-grub
```
## ubuntu18.04 安装蓝牙驱动（尚未完成）
查看是否有蓝牙进程
```bash
ps aux | grep bluetooth
```
[蓝牙_Ubuntu使用BlueZ驱动蓝牙dongle](https://blog.csdn.net/weixin_26969967/article/details/112708127)

## pip
```bash
cd ~                   # 进入家目录 
mkdir .pip             # 新建.pip隐藏文件夹
# 或者 mkdir -p .config/pip      
cd .pip                # 进入.pip文件夹
# 或者 cd .config/pip               
touch pip.conf         # 新建pip.conf文件
vim pip.conf           # 用vim编辑pip.conf文件

--------------------

[global]
 
index-url=https://pypi.tuna.tsinghua.edu.cn/simple
 
timeout = 6000
 
[install]
 
trusted-host=pypi.tuna.tsinghua.edu.cn
 
disable-pip-version-check = true
```
