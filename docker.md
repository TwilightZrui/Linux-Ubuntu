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

docker run --name ros2_humble_v194 -d \
  --security-opt seccomp=unconfined \
  --gpus all \
  --env NVIDIA_DRIVER_CAPABILITIES=graphics,compute,utility,video,display \
  --env NVIDIA_VISIBLE_DEVICES=all \
  -e DISPLAY=$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  --privileged=true \
  -u root \
  --device /dev/:/dev/ \
  -v /dev/shm:/dev/shm \
  -v /home/blue/studio/docker/doc:/root/ \
  --network=host \
  ros-humble-nuc:v1.9.4
```

## 进入docker
```
docker exec -it $container_name /bin/bash
```

```
# local, for mujoco
xhost +SI:localuser:root 
export DISPLAY=:1
```
