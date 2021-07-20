Installing cuDNN On Linux-Ubuntu18.04

Nvidia官方文档 ：https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html
https://blog.csdn.net/chch2010523/article/details/107929168
https://blog.csdn.net/xhw205/article/details/116297555

我的环境：
Ubuntu： 18.04
CUDA 11.0.2

1.Prerequisites
  CUDA, the CUDA driver, and the NVIDIA hardware are installed.
2.Down cuDNN for Linux
  https://developer.nvidia.com/rdp/cudnn-archive
  根据适配的CUDA版本和Ubuntu版本，下载 cuDNN Libaray for Linux 和下面的三个 Runtime、Developer 和 Code Samples
  
  下载：
  cuDNN Library for Linux (x86_64)
  
  cuDNN Runtime Library for Ubuntu18.04 x86_64 (Deb)
  cuDNN Developer Library for Ubuntu18.04 x86_64 (Deb)
  cuDNN Code Samples and User Guide for Ubuntu18.04 x86_64 (Deb)
3.Install CUDA
  解压 cuDNN 代码：
  cd ~/Download
  tar -xzvf cudnn-x.x-linux-x64-v8.x.x.x.tgz
  
  将文件复制到 CUDA 路径下（这个路径我并没有直接设置为cuda，好像是默认的cuda-xx.x这样一个文件名，请按自己实际情况自行修改）
  sudo cp cuda/include/cudnn*.h /usr/local/cuda/include 
  sudo cp -P cuda/lib64/libcudnn* /usr/local/cuda/lib64 
  sudo chmod a+r /usr/local/cuda/include/cudnn*.h /usr/local/cuda/lib64/libcudnn*
4.Package install
  安装 runtime library:
  sudo dpkg -i libcudnn8_x.x.x-1+cudax.x_amd64.deb
  安装developer library:
  sudo dpkg -i libcudnn8-dev_8.x.x.x-1+cudax.x_amd64.deb
  
  安装 code samples 和 cuDNN library documentation:
  sudo dpkg -i libcudnn8-doc_8.x.x.x-1+cudax.x_amd64.deb
  
5.使用例子测试是否安装成功
  复制 cuDNN sample到有读写权限的文件夹下：
  cp -r /usr/src/cudnn_samples_v8/ $HOME

  cd到复制的mnistcudnn目录下
  cd  $HOME/cudnn_samples_v8/mnistCUDNN

  编译mnistCUDNN sample.
  $make clean && make

  运行mnistCUDNN sample.
  ./mnistCUDNN

  一番运行后，出现如下信息表明安装成功:
  Test passed!
  
  编译mnistCUDNN时如果出错：fatal error: FreeImage.h: No such file or directory
  sudo apt-get install libfreeimage3 libfreeimage-dev
  
  重新编译后，运行
  ./mnistCUDNN

