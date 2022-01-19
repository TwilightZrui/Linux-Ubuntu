## Install CUDA 11.0
### Prepare
1. NVIDIA显卡正常安装
2. 禁用nouveau


```bash
创建配置文件：
sudo touch /etc/modprobe.d/blacklist_nouveau.conf
code /etc/modprobe.d/blacklist-nouveau.conf、

文件中添加：
blacklist nouveau
options nouveau modeset=0

更新内核
sudo update-initramfs -u

使用下面命令查看，如果没有输出代表成功：
lsmod | grep nouveau
```

### Download CUDA and install 
```bash
wget http://developer.download.nvidia.com/compute/cuda/11.0.2/local_installers/cuda_11.0.2_450.51.05_linux.run
sudo sh cuda_11.0.2_450.51.05_linux.run
```
安装CUDA过程中的选项select
```
```bash
Install NVIDIA Accelerated Graphics Driver for Linux-x86_64 384.00? 
(y)es/(n)o/(q)uit: n    #不安装显卡驱动，选n
 
Install the CUDA 8.0 Toolkit?
(y)es/(n)o/(q)uit: y    #安装工具包，y
 
Enter Toolkit Location
[ default is /usr/local/cuda-9.0 ]:    #cuda安装地址，一般直接默认路径回车即可
 
Do you want to install a symbolic link at /usr/local/cuda?
(y)es/(n)o/(q)uit: y    #这是问你是否需要创建链接到该cuda的软链接，如果你需要安装好后就使用这个版本的cuda，那就选y，否则选n即可，软链接可以等安装好之后再添加，这里选择n
 
Install the CUDA 8.0 Samples?
(y)es/(n)o/(q)uit: y    #安装样例，y
 
Enter CUDA Samples Location
 [ default is /root ]:    #样例安装地址默认即可
 ```

 ### Config
 ```bash
 code ~/.bashrc

add:
export PATH=/usr/local/cuda/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH

source ~/.bashrc
```

### Test cuda
```bash
nvcc -V
```

```bash
cd /usr/local
ls
cuda11-0
```
(2). 编译samples例子
```bash
#编译并测试设备 deviceQuery：
cd /usr/local/cuda-9.2/samples/1_Utilities/deviceQuery
sudo make
./deviceQuery

#编译并测试带宽 bandwidthTest：
cd ../bandwidthTest
sudo make
./bandwidthTest

如果这两个测试的最后结果都是Result = PASS，说明CUDA安装成功啦。
```

### cuda version
```bash
cat /usr/local/cuda/version.txt
```

To test if CUDA works in torch
```bash
python
>>import torch  
>>torch.cuda.is_available() 
True
```

[CUDA官网安装指南](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#runfile-nouveau-ubuntu)
[Linux安装CUDA的正确姿势](https://blog.csdn.net/wf19930209/article/details/81879514)
### warning
```bash
/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_adv_train.so.8 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_train.so.8 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn.so.8 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8 is not a symbolic link

/sbin/ldconfig.real: /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8 is not a symbolic link

```
slove
```bash
sudo ldconfig -v
sudo ln -sf 
sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_adv_train.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_adv_train.so.8

sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_train.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_train.so.8

sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_infer.so.8

sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn.so.8

sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_cnn_train.so.8

sudo ln -sf /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8.0.5 /usr/local/cuda-11.0/targets/x86_64-linux/lib/libcudnn_ops_infer.so.8
```
## Install cuDNN 8.0.5
```bash
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/cudnn-11.0-linux-x64-v8.0.5.39.tgz
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8_8.0.5.39-1+cuda11.0_amd64.deb
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8-dev_8.0.5.39-1+cuda11.0_amd64.deb
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8-samples_8.0.5.39-1+cuda11.0_amd64.deb
tar -xzvf cudnn-11.0-linux-x64-v8.0.5.39.tgz
cd /cuda
sudo cp cuda/include/cudnn* /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*
sudo dpkg -i libcudnn8_8.0.5.39-1+cuda11.0_amd64.deb
sudo dpkg -i libcudnn8-dev_8.0.5.39-1+cuda11.0_amd64.deb
sudo dpkg -i libcudnn8-samples_8.0.5.39-1+cuda11.0_amd64.deb
```
test cuDNN
```bash
cp -r /usr/src/cudnn_samples_v8/ ~ 
cd ~/cudnn_samples_v8/mnistCUDNN/ 
make clean && make 
./mnistCUDNN
```

view version
```
cat /usr/local/cuda/include/cudnn_version.h | grep CUDNN_MAJOR -A 2
```
## Install torch(CUDA 11.0)
[torch version](https://pytorch.org/get-started/previous-versions/#conda-1)
```bash
conda install pytorch==1.7.1 torchvision==0.8.2 torchaudio==0.7.2 cudatoolkit=11.0 -c pytorch
```
test torch
```bash
import torch
x = torch.rand(5, 3)
print(x)
output:
tensor([[0.3380, 0.3845, 0.3217],
        [0.8337, 0.9050, 0.2650],
        [0.2979, 0.7141, 0.9069],
        [0.1449, 0.1132, 0.1375],
        [0.4675, 0.3947, 0.1426]])
```            

Use PyTorch to view the CUDA and cuDNN versions
```bash
import torch
print(torch.__version__)
print(torch.version.cuda)
print(torch.backends.cudnn.version())
```
## Switch between different CUDA versions
```bash
ls /usr/local/
sudo rm -rf cuda
sudo ln -s /usr/local/cuda-10.2 /usr/local/cuda
```
Ubuntu 切换不同的CUDA版本https://blog.csdn.net/mathlxj/article/details/117323182
