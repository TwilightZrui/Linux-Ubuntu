## docker 去sudo操作
```
sudo groupadd docker
sudo usermod -aG docker $USER

退出当前终端并重新登录，或运行以下命令立即生效：
newgrp docker
```

## docker 挂载
```
docker run --name ros2_humble_v194 -d --security-opt seccomp=unconfined --gpus 'all,"capabilities=compute,utility,graphics"' -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix --privileged=true -u root -v /dev/shm:/dev/shm -v /home/blue/studio/docker/doc:/root/ --network=host ros-humble-nuc:v1.9.4
```
