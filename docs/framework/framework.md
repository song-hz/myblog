# Network

## 术语

### logits

logits在深度学习中表示模型最后一层的数据，没有经过sigmoid或者softmax处理的数据，也就是raw data，之后可以接softmax或者sigmod进行缩放
logits的范围为 [− ∞，+ ∞]

## 模型

介绍一些模型

### Transformer

[[整理\] 聊聊 Transformer - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/47812375)

### RNN

[学会区分 RNN 的 output 和 state - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/28919765)



# Pytorch

### torch.nn

PyTorch 中的 torch.nn 包提供了很多与实现神经网络中的具体功能相关的类，这些类涵盖了深度神经网络模型在搭建和参数优化过程中的常用内容，比如神经网络中的卷积层、池化层、全连接层这类层次构造的方法、防止过拟合的参数归一化方法、Dropout 方法，还有激活函数部分的线性激活函数、非线性激活函数相关的方法

## pytorch中常用函数

### Dropout

[(95条消息) 【Pytorch】nn.Dropout的用法_马里亚纳Mariana的博客-CSDN博客_nn.dropout](https://blog.csdn.net/weixin_47050107/article/details/122722516)

- Dropout是为了防止过拟合而设置的
- nn.Dropout(p = 0.3) # 表示每个神经元有0.3的可能性不被激活
- Dropout只能用在训练部分而不能用在测试部分
- Dropout一般用在全连接神经网络映射层之后，如代码的nn.Linear(20, 30)之后

### squeeze

[(95条消息) 【学习笔记】pytorch中squeeze()和unsqueeze()函数介绍_Jaborie203的博客-CSDN博客_unsqueeze](https://blog.csdn.net/flysky_jay/article/details/81607289)

- unsqueeze(n)在第n维上增加维度，维度从0开始

- squeeze(n)去掉第n维，意味着第n维的值为1

### forward

[(95条消息) pytorch中的forward函数详细理解_不知道叫啥好一点的博客-CSDN博客_forward函数](https://blog.csdn.net/A_A666/article/details/108745538)

- model(data)等价于model.forward(data)
- foward中定义了数据传送过程，model的init函数中定义使用到的网络结构，比如除了成熟大型模型之后自己加的全连接层等等

### self&init

[【Pytorch】self参数, __ init__ ()方法 和 super(Model, self).__init__() - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/477117166)

- Net类继承nn.Module，super(Net, self).__init__()就是对继承自父类nn.Module的属性进行初始化。而且是用nn.Module的初始化方法来初始化继承的属性。super().__init()__()来**通过初始化父类属性以初始化自身继承了父类的那部分属性**；这样一来，作为nn.Module的子类（LinearNet）就无需再初始化那一部分属性了，只需初始化新加的元素。
- 写神经网络模型的时候，父类Modle中还有一些属性我们不用再自己手写了，直接将其初始化就好，另外Model也是有继承的父类network.Network，这里也有一些我们不知道、不知如何自己写的属性和方法。所以最好都加上 super(MyModel,self).__init__()这样的父类初始化命令行。
- 在python中创建类后，通常会创建一个 __ init__ ()方法，这个方法会在创建类的实例的时候自动执行。

### DataLoader

[(95条消息) PyTorch学习笔记（4）--DataLoader的使用_我这一次的博客-CSDN博客_dataloader](https://blog.csdn.net/weixin_43981621/article/details/119685671)

- DataLoader是Pytorch中用来处理模型输入数据的一个工具类。组合了数据集（dataset） + 采样器(sampler)，并在数据集上提供单线程或多线程(num_workers )的可迭代对象

`epoch：所有的训练样本输入到模型中称为一个epoch；iteration：一批样本输入到模型中，成为一个Iteration；batchszie：批大小，决定一个epoch有多少个Iteration；迭代次数（iteration）=样本总数（epoch）/批尺寸（batchszie）；dataset (Dataset) – 决定数据从哪读取或者从何读取；batch_size (python:int, optional) – 批尺寸(每次训练样本个数,默认为１；shuffle (bool, optional) –每一个 epoch是否为乱序 (default: False)；num_workers (python:int, optional) – 是否多进程读取数据（默认为０);drop_last (bool, optional) – 当样本数不能被batchsize整除时，最后一批数据是否舍弃（default: False) ；pin_memory（bool, optional) - 如果为True会将数据放置到GPU上去（默认为false）`

### model.to(device)

[pytorch中model=model.to(device)用法 - 腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/1587906)

- model=model.to(device)

### tqdm

[(95条消息) 【PyTorch总结】tqdm的使用_是王同学呀的博客-CSDN博客_pytorch tqdm](https://blog.csdn.net/wxd1233/article/details/118371404)

- Tqdm 是 Python [进度条](https://so.csdn.net/so/search?q=进度条&spm=1001.2101.3001.7020)库，可以在 Python 长循环中添加一个进度提示信息。用户只需要封装任意的[迭代器](https://so.csdn.net/so/search?q=迭代器&spm=1001.2101.3001.7020)，是一个快速、扩展性强的进度条工具库。

### nn.Sequential&Linear&ReIU

[(95条消息) PyTorch 笔记（16）— torch.nn.Sequential、torch.nn.Linear、torch.nn.RelU_wohu1104的博客-CSDN博客_torch.nn.relu](https://blog.csdn.net/wohu1104/article/details/107646744)

- `torch.nn.Sequential` 类是 `torch.nn` 中的一种序列容器，通过在容器中嵌套各种实现神经网络中具体功能相关的类，来完成对神经网络模型的搭建，最主要的是，参数会按照我们定义好的序列自动传递下去。
- `torch.nn.Linear` 类接收的参数有三个，分别是输入特征数、输出特征数和是否使用偏置，设置是否使用偏置的参数是一个布尔值，默认为 `True` ，即使用偏置。
- `torch.nn.ReLU` 类属于非线性激活分类，在定义时默认不需要传入参数。



# tensorflow

## gfile的API介绍

tf.gfile.Copy\tf.gfile.MkDir\tf.gfile.Remove\tf.gfile.DeleteRecursively\tf.gfile.Exists\tf.gfile.Glob\tf.gfile.IsDirectory\tf.gfile.ListDirectorytf.gfile.MakeDirs\tf.gfile.Rename\tf.gfile.Stat\tf.gfile.Walk\tf.gfile.GFile\tf.gfile.Open\tf.gfile.FastGFile
[https://blog.csdn.net/maweifei/article/details/80723465](https://blog.csdn.net/maweifei/article/details/80723465)别人的总结

## tensorflow基础知识

### flags

flags = tf.flags FLAGS = flags.FLAGS
用于帮助**添加命令行的可选参数**，类似argparse的功能，如
tf.flags.DEFINE_string('name', 'default', 'name of the model')
tf.flags.DEFINE_integer('num_seqs', 100, 'number of seqs in one batch')
[https://www.cnblogs.com/happy-sir/p/11486272.html](https://www.cnblogs.com/happy-sir/p/11486272.html)转载

### set_verbosity

tf.logging.set_verbosity (tf.logging.INFO)
将 TensorFlow 日志信息输出到屏幕
TensorFlow有五个不同级别的日志信息。其严重性为**调试DEBUG<信息INFO<警告WARN<错误ERROR<致命FATAL**。当你配置日志记录在任何级别，TensorFlow将输出与该级别相对应的所有日志消息以及更高程度严重性的所有级别的日志信息。例如，如果设置错误的日志记录级别，将得到包含错误和致命消息的日志输出，并且如果设置了调试级别，则将从所有五个级别获取日志消息。
默认情况下，TENSFlow在WARN的日志记录级别进行配置，但是在跟踪模型训练时，需要将级别调整为INFO
[https://blog.csdn.net/weixin_38314865/article/details/83374265](https://blog.csdn.net/weixin_38314865/article/details/83374265)转载

### get_variable

[(95条消息) tf.get_variable的使用方法_Bubbliiiing的博客-CSDN博客_getvariable](https://blog.csdn.net/weixin_44791964/article/details/96134474)

  - 该函数的作用是创建新的tensorflow变量，常见的initializer有：常量初始化器tf.constant_initializer、正太分布初始化器tf.random_normal_initializer、截断正态分布初始化器tf.truncated_normal_initializer、均匀分布初始化器tf.random_uniform_initializer。

### tf.matmul

[(95条消息) tf.matmul函数用法_NLP蜗牛的博客-CSDN博客_tf.matmul](https://blog.csdn.net/weixin_41845265/article/details/106863171)

  - 将矩阵 a 乘以矩阵 b,生成a * b

### random_seed

[Tensorflow应用--tf.set_random_seed 的用法 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/109238035?from_voters_page=true)

  - 当在代码中使用了随机数，但是希望代码在不同时间或者不同的机器上运行能够得到相同的随机数，以至于能够得到相同的结果，那么久需要到设置随机函数的**seed** 参数，对应的变量可以跨**session**生成 相同的随机数

### tf.variable_scope

[(95条消息) tf.variable_scope_方如一的博客-CSDN博客_tf.variable_scope](https://blog.csdn.net/Fwuyi/article/details/125608357?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-125608357-blog-82770192.pc_relevant_vip_default&spm=1001.2101.3001.4242.1&utm_relevant_index=4)

[(95条消息) tf.variable_scope（）_gqixl的博客-CSDN博客_tf.variable_scope](https://blog.csdn.net/gqixf/article/details/82770192)

  - 可变范围允许创建新的variable并分享已创建的variable，同时提供检查，不会意外创建或共享。

### SummaryWriter

[(95条消息) Tensorboard：SummaryWriter类_shing_star的博客-CSDN博客_summarywriter](https://blog.csdn.net/Lstar_/article/details/123500095)

  SummaryWriter类可以在指定文件夹生成一个事件文件，这个事件文件可以对TensorBoard解析。

### Session

[(95条消息) tensorflow —— tf.Session()_rainbow_lucky0106的博客-CSDN博客_tensorflow tf.session()](https://blog.csdn.net/qq_21980099/article/details/85331930)

  [(95条消息) sess.run()详解_Jqlender的博客-CSDN博客_sess.run](https://blog.csdn.net/qq_34035425/article/details/122700121)

### ConfigProto

[tf.ConfigProto (allow_soft_placement=True) - 简书 (jianshu.com)](https://www.jianshu.com/p/99fca5b7fd8a)

  [(95条消息) config=tf.ConfigProto(allow_soft_placement=True)_来一包板栗的博客-CSDN博客_allow_soft_placement](https://blog.csdn.net/qq_27871973/article/details/91038691)





## 模型训练相关知识

### warmup_proportion
warmup_proportion表示，慢热学习的比例。 比如warmup_proportion=0.1，总步数=100，那么warmup步数就为10。 在1到10步中，学习率会比10步之后低，10步之后学习率恢复正常。(百度）

### tf.app.run()

tf.app.run()  **执行程序中main函数，并解析命令行参数**

```bash
if __name__ == '__main__':
    tf.app.run()
```

上述第一行代码表示如果当前是从其它模块调用的该模块程序，则不会运行main函数！而如果就是直接运行的该模块程序，则会运行main函数。
[https://www.jianshu.com/p/55cbd3753ee8](https://www.jianshu.com/p/55cbd3753ee8)转载





