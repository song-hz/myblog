# pytorch基本知识介绍

常用知识

## torch.nn

PyTorch 中的 torch.nn 包提供了很多与实现神经网络中的具体功能相关的类，这些类涵盖了深度神经网络模型在搭建和参数优化过程中的常用内容，比如神经网络中的卷积层、池化层、全连接层这类层次构造的方法、防止过拟合的参数归一化方法、Dropout 方法，还有激活函数部分的线性激活函数、非线性激活函数相关的方法

# pytorch中常用函数

1. [(95条消息) 【Pytorch】nn.Dropout的用法_马里亚纳Mariana的博客-CSDN博客_nn.dropout](https://blog.csdn.net/weixin_47050107/article/details/122722516)
   - Dropout是为了防止过拟合而设置的
   - nn.Dropout(p = 0.3) # 表示每个神经元有0.3的可能性不被激活
   - Dropout只能用在训练部分而不能用在测试部分
   - Dropout一般用在全连接神经网络映射层之后，如代码的nn.Linear(20, 30)之后

2. [(95条消息) 【学习笔记】pytorch中squeeze()和unsqueeze()函数介绍_Jaborie203的博客-CSDN博客_unsqueeze](https://blog.csdn.net/flysky_jay/article/details/81607289)

   - unsqueeze(n)在第n维上增加维度，维度从0开始

   - squeeze(n)去掉第n维，意味着第n维的值为1

3. [(95条消息) pytorch中的forward函数详细理解_不知道叫啥好一点的博客-CSDN博客_forward函数](https://blog.csdn.net/A_A666/article/details/108745538)
   - model(data)等价于model.forward(data)
   - foward中定义了数据传送过程，model的init函数中定义使用到的网络结构，比如除了成熟大型模型之后自己加的全连接层等等

4. [【Pytorch】self参数, __ init__ ()方法 和 super(Model, self).__init__() - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/477117166)

   - Net类继承nn.Module，super(Net, self).__init__()就是对继承自父类nn.Module的属性进行初始化。而且是用nn.Module的初始化方法来初始化继承的属性。super().__init()__()来**通过初始化父类属性以初始化自身继承了父类的那部分属性**；这样一来，作为nn.Module的子类（LinearNet）就无需再初始化那一部分属性了，只需初始化新加的元素。
   - 写神经网络模型的时候，父类Modle中还有一些属性我们不用再自己手写了，直接将其初始化就好，另外Model也是有继承的父类network.Network，这里也有一些我们不知道、不知如何自己写的属性和方法。所以最好都加上 super(MyModel,self).__init__()这样的父类初始化命令行。
   - 在python中创建类后，通常会创建一个 __ init__ ()方法，这个方法会在创建类的实例的时候自动执行。

5. [(95条消息) PyTorch学习笔记（4）--DataLoader的使用_我这一次的博客-CSDN博客_dataloader](https://blog.csdn.net/weixin_43981621/article/details/119685671)

   - DataLoader是Pytorch中用来处理模型输入数据的一个工具类。组合了数据集（dataset） + 采样器(sampler)，并在数据集上提供单线程或多线程(num_workers )的可迭代对象

   `epoch：所有的训练样本输入到模型中称为一个epoch；iteration：一批样本输入到模型中，成为一个Iteration；batchszie：批大小，决定一个epoch有多少个Iteration；迭代次数（iteration）=样本总数（epoch）/批尺寸（batchszie）；dataset (Dataset) – 决定数据从哪读取或者从何读取；batch_size (python:int, optional) – 批尺寸(每次训练样本个数,默认为１；shuffle (bool, optional) –每一个 epoch是否为乱序 (default: False)；num_workers (python:int, optional) – 是否多进程读取数据（默认为０);drop_last (bool, optional) – 当样本数不能被batchsize整除时，最后一批数据是否舍弃（default: False) ；pin_memory（bool, optional) - 如果为True会将数据放置到GPU上去（默认为false）`

6. [pytorch中model=model.to(device)用法 - 腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/1587906)

   - model=model.to(device)

7. [(95条消息) 【PyTorch总结】tqdm的使用_是王同学呀的博客-CSDN博客_pytorch tqdm](https://blog.csdn.net/wxd1233/article/details/118371404)

   - Tqdm 是 Python [进度条](https://so.csdn.net/so/search?q=进度条&spm=1001.2101.3001.7020)库，可以在 Python 长循环中添加一个进度提示信息。用户只需要封装任意的[迭代器](https://so.csdn.net/so/search?q=迭代器&spm=1001.2101.3001.7020)，是一个快速、扩展性强的进度条工具库。

8. [(95条消息) PyTorch 笔记（16）— torch.nn.Sequential、torch.nn.Linear、torch.nn.RelU_wohu1104的博客-CSDN博客_torch.nn.relu](https://blog.csdn.net/wohu1104/article/details/107646744)
   - `torch.nn.Sequential` 类是 `torch.nn` 中的一种序列容器，通过在容器中嵌套各种实现神经网络中具体功能相关的类，来完成对神经网络模型的搭建，最主要的是，参数会按照我们定义好的序列自动传递下去。
   - `torch.nn.Linear` 类接收的参数有三个，分别是输入特征数、输出特征数和是否使用偏置，设置是否使用偏置的参数是一个布尔值，默认为 `True` ，即使用偏置。
   - `torch.nn.ReLU` 类属于非线性激活分类，在定义时默认不需要传入参数。
9. 

