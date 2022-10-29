# Bert的tensorflow版学习
## Bert

 1. cased和uncased的区别
 	cased区分大小写，不需要lower-case
	uncased不区分大小写(这句话是错的，所谓不区分大小写实际上是不能区分大小写，因为词表只有小写)，需要lower-case
	[https://blog.csdn.net/weixin_43301333/article/details/113967056](https://blog.csdn.net/weixin_43301333/article/details/113967056)转载
 2. 夫人
 3. 不
 4. iibn
 5. 

## tensorflow
### gfile的API介绍
tf.gfile.Copy\tf.gfile.MkDir\tf.gfile.Remove\tf.gfile.DeleteRecursively\tf.gfile.Exists\tf.gfile.Glob\tf.gfile.IsDirectory\tf.gfile.ListDirectorytf.gfile.MakeDirs\tf.gfile.Rename\tf.gfile.Stat\tf.gfile.Walk\tf.gfile.GFile\tf.gfile.Open\tf.gfile.FastGFile
[https://blog.csdn.net/maweifei/article/details/80723465](https://blog.csdn.net/maweifei/article/details/80723465)别人的总结

### tensorflow基础知识
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



### 模型训练相关知识
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

