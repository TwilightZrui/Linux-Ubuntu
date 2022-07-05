## Install ROS-Melodic on ubuntu18.04
```bash
# Setup your sources.list
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

# Set up your keys
sudo apt install curl 
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

# Installation
sudo apt update
sudo apt install ros-melodic-desktop-full

# Environment setup
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Dependencies for building packages
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```
[解决sudo rosdep init和rosdep update各种疑难杂症](https://blog.csdn.net/Twilightzr/article/details/121714894)
## test ROS
```bash
roscore
rosrun turtlesim turtle
rosrun turtlesim turtle_teleop_key
```
## 为ubuntu18.04安装jsk_recognition_msgs
ros安装功能包
```bash
sudo apt-get install ros-$release-ros-numpy
```

```bash
sudo apt-get install ros-melodic-jsk-recognition-msgs
sudo apt-get install ros-melodic-jsk-rviz-plugins
```
## remove ROS 
```bash
sudo apt-get purge ros-*
sudo rm -rf /etc/ros
gedit ~/.bashrc
```

## Instruction
ros 查找包路径
```bash
rospack find package_name
```

## 绘图
```bash
sudo apt-get install ros-melodic-plotjuggler
rosrun plotjuggler PlotJuggler

cd ~/ws_plotjuggler/src
git clone https://github.com/PlotJuggler/plotjuggler_msgs.git
git clone https://github.com/facontidavide/PlotJuggler.git #源码安装已下载
git clone https://github.com/PlotJuggler/plotjuggler-ros-plugins.git

```

## Install ROS-Noetic on ubuntu18.04
```bash
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full

Environment setup:
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```
