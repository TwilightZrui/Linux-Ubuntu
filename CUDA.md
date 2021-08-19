install cuDNN 8.0.5
```bash
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/cudnn-11.0-linux-x64-v8.0.5.39.tgz
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8_8.0.5.39-1+cuda11.0_amd64.deb
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8-dev_8.0.5.39-1+cuda11.0_amd64.deb
wget https://developer.nvidia.com/compute/machine-learning/cudnn/secure/8.0.5/11.0_20201106/Ubuntu18_04-x64/libcudnn8-samples_8.0.5.39-1+cuda11.0_amd64.deb

tar -xzvf cudnn-11.0-linux-x64-v8.0.5.39.tgz
cd /cuda
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
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
