## docker 去sudo操作
```
sudo groupadd docker
sudo usermod -aG docker $USER

退出当前终端并重新登录，或运行以下命令立即生效：
newgrp docker
```
