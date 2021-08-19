## install CUDA 11.0
```bash
wget http://developer.download.nvidia.com/compute/cuda/11.0.2/local_installers/cuda_11.0.2_450.51.05_linux.run
sudo sh cuda_11.0.2_450.51.05_linux.run

code ~/.bashrc
##add
export PATH=/usr/local/cuda/bin:$PATH
export $ LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
##
source ~/.bashrc
```
test cuda
```bash
nvcc -V
```

cuda version
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
## install cuDNN 8.0.5
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
cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2
```
## install torch(CUDA 11.0)
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
