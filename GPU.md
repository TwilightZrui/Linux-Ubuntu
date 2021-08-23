
动态实时监控GPU 的使用情况
```bash
pip install gpustat
watch --color -n1 gpustat -cpu
# gpustat基于nvidia-smi可以提供更美观简洁的展示
```
释放GPU显存
```bash
nvidia-smi -l 1  # 1ms速度实时nvidia-smi
fuser -v /dev/nvidia* # 查看运行在gpu上的所有程序
pmap -d PID # 查看具体这个进程调用GPU的情况
kill -9 PID # 强行关掉所有当前并未执行的僵尸进程
```
