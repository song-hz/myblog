# Mac

## 修改默认Python版本

 vi ~/.bash_profile    # 添加这一行   

alias python="/usr/local/bin/python3"   

source ~/.bash_profile

# Anaconda

## Anaconda环境相关

### 安装

- [(95条消息) anaconda安装-超详细版_plasma-deeplearning的博客-CSDN博客_anaconda安装](https://blog.csdn.net/in546/article/details/117400839)

- [(95条消息) CondaHTTPError: HTTP 000 CONNECTION FAILED for url解决方法（不用换源，简单有效）_风吹我亦散的博客-CSDN博客_condahttperror](https://blog.csdn.net/weixin_45468845/article/details/122516155?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&utm_relevant_index=4)anaconda出现CondaHTTPError问题

  博客有点复杂，备选方案吧

  应该是源的问题，先用默认源安装  `换回默认源：conda config --remove-key channels`

- [(95条消息) Anaconda删除源及更改源_郡酱~的博客-CSDN博客_conda清除所有源](https://blog.csdn.net/weixin_40977054/article/details/115524523)

  显示目前的源conda config --show channels

  删除源conda config --remove channels

  添加清华源conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

### virtual environment

- conda create --name env-name python=3.6
-  conda remove -n your_env_name --all
- conda env list
- conda list
- [conda虚拟环境复制_jing__min的博客-CSDN博客_conda复制虚拟环境](https://blog.csdn.net/jing__min/article/details/125073861?spm=1001.2101.3001.6650.17&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-17-125073861-blog-88744268.pc_relevant_aa&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-17-125073861-blog-88744268.pc_relevant_aa&utm_relevant_index=24)
- [Conda环境复制的方法_xbs118的博客-CSDN博客_conda 复制环境](https://blog.csdn.net/qq_38262728/article/details/88744268)

### 环境导入导出

- conda env export --file D:\python36_20190106.yml
- conda env create -f  D:\python36_20190106.yml

## TensorFlow安装

完整参考：[(111条消息) Tensorflow + PyTorch 安装（CPU + GPU 版本）_Netceor的博客-CSDN博客_pytorch安装tensorflow](https://blog.csdn.net/Netceor/article/details/119821270)

安装Anaconda

[Index of /anaconda/archive/ | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)[Index of /anaconda/archive/ | 清华大学开源软件镜像站 | Tsinghua Open Source Mirror](https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/)

[(111条消息) anaconda安装-超详细版_plasma-deeplearning的博客-CSDN博客_anaconda安装](https://blog.csdn.net/in546/article/details/117400839)

### Tensorflow CPU

1. conda create --name tensorflow python=3.6.2
2. conda activate tensorflow
3. pip install tensorflow
4. python
5. import tensorflow as tf（没出错即成功

### Tensorflow GPU

#### 算力&驱动

官方版本和算力查看链接：https://developer.nvidia.com/zh-cn/cuda-gpus

官方驱动链接：https://www.nvidia.com/Download/index.aspx?lang=en-us

安装后重启

#### 虚拟环境

conda create --name tensorflow-gpu python=3.6.2

conda activate tensorflow-gpu

#### 版本匹配

https://blog.csdn.net/K1052176873/article/details/114526086

#### CUDA

官方参考链接：https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html

打开**NVIDIA控制面板→帮助→系统信息→组件**，发现最高支持11.4的CUDA

CUDA下载链接：https://developer.nvidia.com/cuda-toolkit-archive (选择local版本)

添加系统环境路径：

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.4
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.4\lib\x64

控制台：nvcc -V

#### cuDNN

cuDNN下载链接：https://developer.nvidia.com/zh-cn/cudnn

解压文件夹下的bin,include,lib移动到NVIDIA GPU Computing Tookit\CUDA\v.11.4下

#### 安装TensorFlow

pip install tensorflow-gpu==2.4.0

测试：（输出TRUE则成功）

import tensorflow as tf
print(tf.test.is_gpu_available())

#### DLL文件

- 链接：https://pan.baidu.com/s/1yNBXYtw5B36FLNPd1s92UQ
  提取码：6bbw
  下载下来以后是一堆dll文件，将其全部复制到C:\Windows\System路径下

- 到链接里下载 https://pan.baidu.com/s/1kFGzdhhakMP4irRaXHUVnw 提取码：kfll

#### Failed to load the native TensorFlow runtime

版本错误

## Pytorch安装

- torch和torchvision的版本对应关系如下链接
  https://github.com/pytorch/vision

- 到该链接找到可用的torch和torchvision版本

  https://download.pytorch.org/whl/torch_stable.html

- 1.创建新环境

  conda create --name torch-gpu python=3.6.2

  2.查看是否成功

  conda info --envs

  3.激活

  activate torch-gpu

  4.安装torch

  pip install torch-1.7.1+cu110-cp36-cp36m-win_amd64.whl

  使用镜像

  pip install xx -i http://pypi.douban.com/simple --trusted-host pypi.douban.com

  pip install D:\SoftWare\Anaconda3\torch-1.7.1+cu110-cp36-cp36m-win_amd64.whl

  conda install pytorch torchvision torchaudio cudatoolkit=11.4 -c pytorch -c conda-forge

  5.安装torchvision

  pip install torchvision-0.8.2+cpu-cp36-cp36m-win_amd64.whl

- 进入python测试

  import torch
  print(torch.cuda.is_available())

## pip相关

### ReadTimeoutError

raise ReadTimeoutError(self._pool, None, 'Read timed out.')
ReadTimeoutError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Read timed out.
原因：网络不好
解决：重试；延长Timeout时间；换源
[https://blog.csdn.net/qq_38316655/article/details/81463917](https://blog.csdn.net/qq_38316655/article/details/81463917)转载


### pip安装包问题

### PyHarmcrest

[(95条消息) 简单解决twisted 18.7.0 requires PyHamcrest＞=1.9.0, which is not installed.问题_晨风先生的博客-CSDN博客_pyhamcrest>=1.9.0](https://blog.csdn.net/qq_40089560/article/details/114494464?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&utm_relevant_index=3)

重试或者镜像错误利用default安装

### PyYAML

[(95条消息) ERROR: Cannot uninstall ‘PyYAML‘. It is a distutils installed project and thus we cannot..._#晚来天欲雪的博客-CSDN博客](https://blog.csdn.net/YIZHILIUSHA2020/article/details/125387390)

- `pip install --ignore-installed pyyaml`忽略已安装的PYYAML包，重新安装

  

## conda相关 

cuda版本和Windows系统环境中的顺序前后有关，先加载排在前面的路径

### cuda no visual studio integration was found

安装Visual Studio 2019（2017 forcuda10.0&10.1) 

2019版本和2017版本可以一起兼容

## 显卡刷新

nvidia-smi

nvidia-smi -l 1每两秒刷新

# Blog

## MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

[自动部署网页教程](https://www.ttlarva.com/master/github/06_Mkdocs.html)

### mkdocs.yml配置

还没整理的一些网页链接：

[Mkdocs 配置和使用 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/383582472)

[(95条消息) Mkdocs部署静态网页至GitHub pages配置说明(mkdocs.yml)_Wcowin的博客-CSDN博客](https://blog.csdn.net/m0_63203517/article/details/127444446)

[(95条消息) so easy！从头教你用mkdocs构建个人博客系统~_水木子_的博客-CSDN博客_mkdocs](https://blog.csdn.net/qq_41261251/article/details/116021097)

### Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start [the](https://www.jianshu.com/p/f378e3f2e7e1) live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Typora

[2020Typora小白完全使用教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/293557841)

### md文件书写格式

[如何写md格式的文档 - 简书 (jianshu.com)](https://www.jianshu.com/p/f378e3f2e7e1)

### 右键增加md文件创建

1. win+R输入regedit打开注册表

2. 在HKEY_CLASSES_ROOT找到.md文件

3. 将.md中默认值md_auto_file改为Typora.md

4. 若有ShellNew文件夹就可以直接关闭注册表，如果没有

   * 右键.md文件夹 => 新建 => 项，把新建的项命名为"ShellNew"

   - 右键ShellNew => 新建 => 字符串值，将该字符串值名称改为"NullFile"

5. step3&4（已验证成功）的另一种做法是直接新增文件名ShellNew （未验证）

   - 新建字符串值为"NullFile" 
   - 选中新建的NullFile右键修改数值数据输入"typora.md"确定保存



# Vscode

## 插件安装

- Markdown文件预览：安装Markdown All in One\Markdown Preview Enhanced\Markdown Shortcuts
- 改中英文：【Ctrl+Shift+P】->configure Display Language

## 环境配置

### 颜色设置

setting-color theme-dark themes



# [Git相关](./git.md)



# Word

## 上下标

- Alt+=创建公式

- A_a  下标 a^A  上标 按空格实现

- \theta,\scriptR,\bullet 快速输入

- #(1) enter 输入右对齐编号 可插入域自动编号



