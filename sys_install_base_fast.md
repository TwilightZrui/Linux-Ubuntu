# Ubuntu18.04 system install & config fast
terminator
VPN
chrome
nividia driver
CUDA
cuDNN
conda

torch

## terminator
```bash
sudo apt install terminator
```
## VPN

[Linux配置v2ray详细教程-Ubuntu为例](https://mahongfei.com/1776.html)

## chrome 
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
## CUDA 11.0 cuDNN torch
[CUDA 11.0 cuDNN torch INSTALL](https://github.com/TwilightZrui/Linux-Ubuntu/blob/main/CUDA.md)

## conda
```bash
wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
./Miniconda3-latest-Linux-x86_64.sh
```
[【Linux】conda: command not found解决办法](https://blog.csdn.net/weixin_38705903/article/details/86533863)
## cmake
```bash
sudo apt-get remove cmake
sudo apt-get install g++
sudo apt-get install libssl-dev

wget https://github.com/Kitware/CMake/releases/download/v3.21.1/cmake-3.21.1.tar.gz
./bootstrap
make 
make install
```
check version
```bash
cmake --version
```
[Ubuntu中安装Cmake](https://www.cnblogs.com/yanqingyang/p/12731855.html)
