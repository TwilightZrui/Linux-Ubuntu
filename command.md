解压.gz文件
```bash
gzip -d FileName.gz
```

查找文件
```bash
find ~/ -name Country.mmdb
```
回显某个应用的PID
```bash
ps aux | grep process_name 
```
nvidia-smi 实时刷新 实时显示显存使用情况
```bash
watch -n 0.1 -d nvidia-smi     #每隔0.1秒刷新一次 
不建议使用watch查看nvidia-smi，watch每个时间周期开启一个进程(PID)，查看后关闭进程，会影响cuda操作，如cudaMalloc；建议使用nvidia-smi -l x或者nvidia-smi --loop=xxx代替，这个命令执行期间一直是一个进程PID
nvidia-smi -l 1 #1ms刷新一次
```
释放GPU显存
```bash
nvidia-smi -l 1  # 1ms速度实时nvidia-smi
fuser -v /dev/nvidia* # 查看运行在gpu上的所有程序
pmap -d PID # 查看具体这个进程调用GPU的情况
kill -9 PID # 强行关掉所有当前并未执行的僵尸进程
```

```bash

```

```bash

```
```bash

```
```bash

```
```bash

```
```bash

``````bash

```
