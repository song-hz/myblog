# tensorflow

## gfile的API介绍
tf.gfile.Copy\tf.gfile.MkDir\tf.gfile.Remove\tf.gfile.DeleteRecursively\tf.gfile.Exists\tf.gfile.Glob\tf.gfile.IsDirectory\tf.gfile.ListDirectorytf.gfile.MakeDirs\tf.gfile.Rename\tf.gfile.Stat\tf.gfile.Walk\tf.gfile.GFile\tf.gfile.Open\tf.gfile.FastGFile
[https://blog.csdn.net/maweifei/article/details/80723465](https://blog.csdn.net/maweifei/article/details/80723465)别人的总结

## tensorflow基础知识
1. flags = tf.flags FLAGS = flags.FLAGS
	用于帮助**添加命令行的可选参数**，类似argparse的功能，如
	tf.flags.DEFINE_string('name', 'default', 'name of the model')
	tf.flags.DEFINE_integer('num_seqs', 100, 'number of seqs in one batch')
	[https://www.cnblogs.com/happy-sir/p/11486272.html](https://www.cnblogs.com/happy-sir/p/11486272.html)转载

2. tf.logging.set_verbosity (tf.logging.INFO)
	将 TensorFlow 日志信息输出到屏幕
	TensorFlow有五个不同级别的日志信息。其严重性为**调试DEBUG<信息INFO<警告WARN<错误ERROR<致命FATAL**。当你配置日志记录在任何级别，TensorFlow将输出与该级别相对应的所有日志消息以及更高程度严重性的所有级别的日志信息。例如，如果设置错误的日志记录级别，将得到包含错误和致命消息的日志输出，并且如果设置了调试级别，则将从所有五个级别获取日志消息。
默认情况下，TENSFlow在WARN的日志记录级别进行配置，但是在跟踪模型训练时，需要将级别调整为INFO
[https://blog.csdn.net/weixin_38314865/article/details/83374265](https://blog.csdn.net/weixin_38314865/article/details/83374265)转载
	
3. [(95条消息) tf.get_variable的使用方法_Bubbliiiing的博客-CSDN博客_getvariable](https://blog.csdn.net/weixin_44791964/article/details/96134474)

  - 该函数的作用是创建新的tensorflow变量，常见的initializer有：常量初始化器tf.constant_initializer、正太分布初始化器tf.random_normal_initializer、截断正态分布初始化器tf.truncated_normal_initializer、均匀分布初始化器tf.random_uniform_initializer。

4. [(95条消息) tf.matmul函数用法_NLP蜗牛的博客-CSDN博客_tf.matmul](https://blog.csdn.net/weixin_41845265/article/details/106863171)

  - 将矩阵 a 乘以矩阵 b,生成a * b

5. [Tensorflow应用--tf.set_random_seed 的用法 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/109238035?from_voters_page=true)

  - 当在代码中使用了随机数，但是希望代码在不同时间或者不同的机器上运行能够得到相同的随机数，以至于能够得到相同的结果，那么久需要到设置随机函数的***seed\*** 参数，对应的变量可以跨***session\***生成 相同的随机数

6. [(95条消息) tf.variable_scope_方如一的博客-CSDN博客_tf.variable_scope](https://blog.csdn.net/Fwuyi/article/details/125608357?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-125608357-blog-82770192.pc_relevant_vip_default&spm=1001.2101.3001.4242.1&utm_relevant_index=4)

  [(95条消息) tf.variable_scope（）_gqixl的博客-CSDN博客_tf.variable_scope](https://blog.csdn.net/gqixf/article/details/82770192)

  - 可变范围允许创建新的variable并分享已创建的variable，同时提供检查，不会意外创建或共享。

7. [(95条消息) Tensorboard：SummaryWriter类_shing_star的博客-CSDN博客_summarywriter](https://blog.csdn.net/Lstar_/article/details/123500095)

  SummaryWriter类可以在指定文件夹生成一个事件文件，这个事件文件可以对TensorBoard解析。

8. [(95条消息) tensorflow —— tf.Session()_rainbow_lucky0106的博客-CSDN博客_tensorflow tf.session()](https://blog.csdn.net/qq_21980099/article/details/85331930)

  [(95条消息) sess.run()详解_Jqlender的博客-CSDN博客_sess.run](https://blog.csdn.net/qq_34035425/article/details/122700121)

9. [tf.ConfigProto (allow_soft_placement=True) - 简书 (jianshu.com)](https://www.jianshu.com/p/99fca5b7fd8a)

  [(95条消息) config=tf.ConfigProto(allow_soft_placement=True)_来一包板栗的博客-CSDN博客_allow_soft_placement](https://blog.csdn.net/qq_27871973/article/details/91038691)

10. 



## 模型训练相关知识
1. warmup_proportion
	warmup_proportion表示，慢热学习的比例。 比如warmup_proportion=0.1，总步数=100，那么warmup步数就为10。 在1到10步中，学习率会比10步之后低，10步之后学习率恢复正常。(百度）
	
2. tf.app.run()  **执行程序中main函数，并解析命令行参数**
```bash
if __name__ == '__main__':
    tf.app.run()
```
上述第一行代码表示如果当前是从其它模块调用的该模块程序，则不会运行main函数！而如果就是直接运行的该模块程序，则会运行main函数。
[https://www.jianshu.com/p/55cbd3753ee8](https://www.jianshu.com/p/55cbd3753ee8)转载

3. 

