---
id: windows-gpu
sidebar_position: 2
---

# Windows NVIDIA GPU 版本安装教程

## CUDA 安装

更加具体详细的安装教程请参考官方文档：https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html

首先打开自己的NVIDIA控制面板，点击左下角的系统信息，查看组件，了解自己显卡的CUDA适应版本

![7](img\7.png)

或者打开cmd命令行，输入nvidia-smi来查看CUDA Version

![8](img\8.png)

结合[PyTorch的官方文档](https://pytorch.org/)来选择对应的CUDA版本，若主页面中没有自己对应的版本，点击Previous versions of PyTorch选项，去寻找自己版本所对应的pip安装指令

![2](img\2.png)

这里以11.8版本为例

进入[CUDA官网](https://developer.nvidia.com/cuda-toolkit-archive)选择自己对应的版本：


![3](img\3.png)

可以按照下列选项进行安装：

![4](img\4.png)

安装过程中有两种安装选项，一个是精简安装，一个是自定义安装。精简安装会安装CUDA相关组件，同时也会将显卡驱动重新安装，如果不想重新安装显卡驱动，可以选择自定义安装，这里选择自定义安装

![5](img\5.png)

之后选择需要安装的组件，这里将驱动组件取消，其他保持勾选

![6](img\6.png)

之后会让选择CUDA开发组件、文档、示例的安装位置，建议保持默认

安装完成CUDA，使用 nvcc -V 验证是否安装成功

## cuDNN 安装

更加具体详细的安装教程请参考官方文档：https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html#install-windows

查看与自己的CUDA版本的适配版本：https://developer.nvidia.com/rdp/cudnn-archive

首先要注册一个NVIDIA账号

下载得到一个压缩包，将cuDNN解压后得到的三个文件夹复制到cuda文件里面覆盖原有的这三个文件夹里的内容

![9](img\9.png)

加下来检验cuDNN安装是否是成功，在命令行中进入“ cuda安装的位置\CUDA\v11.8(视自己的版本而定)\extras\demo_suite ”，然后输入bandwidthTest.exe，得到Result = PASS则可视为cuDNN安装成功

![10](img\10.png)

## 安装PyTorch

好了，现在可以使用之前的pip指令来进行安装了
