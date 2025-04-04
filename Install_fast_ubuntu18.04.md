# Ubuntu18.04 system install & config fast
terminator
VPN
chrome
nividia driver
CUDA
cuDNN
conda
torch

## Terminator
```bash
sudo apt install terminator
```
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

##  VPN
### v2ray
[Linux配置v2ray详细教程-Ubuntu为例](https://mahongfei.com/1776.html)
如果需要不挂VPN访问外网，需要在setting network中disable代理

### ssr electron-ssr
download: [electron-ssr-backup](https://github.com/qingshuisiyuan/electron-ssr-backup/releases)
用ubuntu software安装
导入链接
在ubuntu setting network中设置代理

### 利用proxychains让命令走代理
```bash
sudo apt install proxychains
sudo vim /etc/proxychains.conf
socks5 127.0.0.1 1080 #端口需要根据代理软件设置
proxychains wget https://www.google.com
```

## chrome 
```bash
wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
```
## CUDA 11.0 cuDNN torch
[CUDA 11.0 cuDNN torch INSTALL](https://github.com/TwilightZrui/Linux-Ubuntu/blob/main/CUDA.md)

## Anaconda
```bash
wget https://repo.anaconda.com/archive/Anaconda3-2021.05-Linux-x86_64.sh
./Anaconda3-2021.05-Linux-x86_64.sh
```
## Sogou 
```bash
sudo apt install fcitx
wget https://ime.sogouimecdn.com/202108250027/b6abc77d89542b7352010c7cd7e88b36/dl/index/1612260778/sogoupinyin_2.4.0.3469_amd64.deb
sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb
sudo apt -f install
```
[Ubuntu搜狗输入法安装指南](https://pinyin.sogou.com/linux/help.php)
[ubuntu18.04安装搜狗输入法](https://jingyan.baidu.com/article/6c67b1d6d304f76687bb1e94.html)

## miniconda
```
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh

~/miniconda3/bin/conda init --all
source ~/.bashrc
```
