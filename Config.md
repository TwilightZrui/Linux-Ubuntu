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
