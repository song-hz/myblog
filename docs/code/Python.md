# python

## 填充0

[python 字符串补全填充固定长度（补0）的三种方法_Fu_Lin_的博客-CSDN博客_字符串固定长度填充](https://blog.csdn.net/CLinuxF/article/details/106728237)

## 进制

[Python: 二进制、八进制、十六进制转换或者输出 - 筱筱的春天 - 博客园 (cnblogs.com)](https://www.cnblogs.com/baxianhua/p/9896926.html)

## 异常执行

for date in dates:   

​	try:        

​		***   

​	except Exception as e:        

​		pass    

​	continue

## TxT

### 读取一行转化为变量

[(111条消息) python读取TXT文件数据并转换为对应的矩阵_乐乐_16的博客-CSDN博客_python 读取txt为矩阵](https://blog.csdn.net/ZC496496/article/details/108587589)

### 多个空格转换为一个空格

import re
str1 = '  rwe fdsa    fasf   '
str1_after = re.sub(' +', ' ', str1)
print(str1_after)

## replace替换

### Dataframe

[(111条消息) Python pandas 内使用 replace 同时替换多个字符串_June056的博客-CSDN博客_python replace](https://blog.csdn.net/June056/article/details/115907676)

replace（'A','X')

replace（['A','B','C'],'X')

replace（{'A':7,'C':3})

### 字符串

[(111条消息) python字符串一次替换多个字符使用replace替换多处_云霄IT的博客-CSDN博客_python字符串替换多个字符](https://blog.csdn.net/weixin_51111267/article/details/122598793)

str2 = str1.replace("a","").replace("b","").replace("c","")

for i in ['gerr',',etrt3yge',',ew']:

​    str2 = str2.replace(i,"")

replace('2', '3'， 1) #替换第一个

[(111条消息) replace:Python 字符串的replace方法默认是全局替换，而在js中是默认只替换一个_shunzi2016的博客-CSDN博客](https://blog.csdn.net/shunzi2016/article/details/115283046)

### 中文符号去除

import re,string
text = " Hello, world! 这，是：我;第!一个程序\?()（）<>《》 "
punc = '~`!#$%^&*()_+-=|\';":/.,?><~·！@#￥%……&*（）——+-=“：’；、。，？》《{}'
print(re.sub(r"[%s]+" %punc, "",text))

## Socket

### socket通信报文接收不完整

recv(1024)指接收1024个字节的信息，当接收端和发送端速度不匹配时，接收端速度更慢会导致接收缓冲区有两次发送的信息，因此此时会取到下一个信息的头部导致下一次读取信息时缺失重要信息无法解析。

若下一包数据到达时前一包数据尚未被用户进程取走，则下一包数据放到系统接收缓冲区时就接到前一包数据之后，而用户进程根据预先设定的缓冲区大小从系统接收缓冲区取数据，这样就一次取到了多包数据

### socket中recv发送长消息

[(111条消息) Python socket 中的recv函数 | 发送长消息_讨饭的博客-CSDN博客_python socket recv](https://blog.csdn.net/qq_40418553/article/details/120674282?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-120674282-blog-121277136.pc_relevant_3mothn_strategy_and_data_recovery&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-120674282-blog-121277136.pc_relevant_3mothn_strategy_and_data_recovery&utm_relevant_index=5)

recv函数的缓冲区被设为1024字节，以太网的MTU为1500字节，不能设置得更大

一个包没有固定长度，以太网限制在46－1500字节，1500就是以太网的MTU，超过这个量，TCP会为IP数据报设置偏移量进行分片传输，现在一般可允许应用层设置8k（NTFS系统）的缓冲区，8k的数据由底层分片，而应用层看来只是一次发送。

[Socket最多一次可以接收多少字节？？？-CSDN社区](https://bbs.csdn.net/topics/390892182)

[(111条消息) socket解决粘包问题_唯尘的博客-CSDN博客_socket粘包解决方案](https://blog.csdn.net/qq_42839596/article/details/102765764)

### json.decoder.JSONDecodeError: Expecting value: line 1 column 1 (char 0)

[(111条消息) 排查解决 json.decoder.JSONDecodeError: Expecting value: line 1 column 1 (char 0)_钉洲小懒猫的博客-CSDN博客](https://blog.csdn.net/zxiang_123/article/details/104377758)

一般是json解析错误

### socket运行过程中 出现 [Errno 32] Broken pipe

这个错误发生在当client端close了当前与你的server端的socket连接，但是你的server端在忙着发送数据给一个已经断开连接的socket。

一般是服务端和客户端之间未建立连接，检查是否连接，IP是否正确

### socket缓冲区

**清空缓冲区**：[(111条消息) Python Socket编程中清空缓冲区的问题_he_yang_的博客-CSDN博客_python 清空缓冲区](https://blog.csdn.net/he_yang_/article/details/122142473)

**接收大数据**：[socket--接受大数据 - Bigberg - 博客园 (cnblogs.com)](https://www.cnblogs.com/bigberg/p/7747419.html)

[Python 清空阻塞模式socket缓冲区 - 简书 (jianshu.com)](https://www.jianshu.com/p/9cb04bb6973e)

[(111条消息) Socket缓冲区_波波仔86的博客-CSDN博客_socket buffer](https://blog.csdn.net/bobozai86/article/details/123698049)

## 字符串转数字

**int**()(转化成整型),或者float()(转化成浮点型)函数即可，但是对于“123,123,098,256”这种含有“,”的字符串来说，就不能用上述函数处理

“ // ” 表示整数除法，返回整数 比如 6//2 结果为3，7//2结果也是3
“ / ” 表示浮点数除法，返回浮点数 （即小数） 比如 6/2 结果为3.0 ，7/2=3.5
“ %” 表示取余数 比如7/4 结果为3

## 通用函数

### strip

str.strip()  ： 去除字符串两边的空格
str.lstrip() ： 去除字符串左边的空格
str.rstrip() ： 去除字符串右边的空格

line.strip().split(’,’)
strip()表示删除掉数据中的换行符，split（‘，’）则是数据中遇到‘,’ 就隔开。

## 逐行写入

#读取

f = open("test.txt","r")   
lines = f.readlines()      #读取全部内容 ，并以列表方式返回  
for line in lines   
    print line 

#写入

name_list = [1, 2, 3]
for i in tqdm(name_list):
    f = open('D:/project/tm_caption/file_names.txt', 'a')
    f.write(str(i) + '\n')
    f.close()

## pickle

import pickle

with open('mypickle.pickle','wb') as f:#写入

​	pickle.dump(some_obj,f)

with open('mypickel.pickle') as f:#读取

​	loaded_obj = pickle.load(f)

f=open('glove.pkl','rb')

content=pickle.load(f)

[(103条消息) .pkl文件的打开方式——Pickle使用说明_2233bilibili的博客-CSDN博客_pkl文件](https://blog.csdn.net/xc257556227/article/details/122310636?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-122310636-blog-104897934.pc_relevant_vip_default&spm=1001.2101.3001.4242.1&utm_relevant_index=4)

## 转义字符 / %

[(103条消息) python中的%用法_hotlong_1998的博客-CSDN博客_python %](https://blog.csdn.net/long_1998/article/details/105311101?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-105311101-blog-107541448.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-105311101-blog-107541448.pc_relevant_vip_default&utm_relevant_index=2)

[(103条消息) 超详细总结：python的转义字符及用法_data大柳的博客-CSDN博客_python 转义](https://blog.csdn.net/yawei_liu1688/article/details/108364192)

## 索引

- for i in range(3): #1 2 3
- for i, j in enumerate(3): # 0 1 2

## numpy

- ones_like 返回一个用1填充的跟输入形状和类型 一致的数组

## Json处理

import json

with open(filename) as f: #读取

​	pop_data = json.load(f)

- dumps 将字典转换成字符串
- dump 将字典转换为字符串，并写入json文件中
- loads 将字符串转换为字典
- load 把文件打开并把字符串变换为数据类型

[python︱处理与使用json格式的数据（json/UltraJSON/Demjson）、pickle模块 - 腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/1434934#:~:text=python︱处理与使用json格式的数据（json%2FUltraJSON%2FDemjson）、pickle模块 1 1、变量解码、编码为Json格式 来看看py3，.dump的 主函数 ： ... 2,json.load(f) ... 3 .  3、其他用法 （1）分离器，用来分割。 )

## 声明coding=utf-8

- [(95条消息) python文件头部声明# coding=utf-8_冰美式QAQ的博客-CSDN博客_# coding=utf-8](https://blog.csdn.net/daningliu/article/details/121617391)

## globals()

[Python globals() 函数 | 菜鸟教程 (runoob.com)](https://www.runoob.com/python/python-func-globals.html)

## namedtuple

[(95条消息) collections.namedtuple 用法详解完整版collections namedtuple](https://blog.csdn.net/m0_37586991/article/details/103713691)

返回的是一个名为 `typename` 的[元组](https://so.csdn.net/so/search?q=元组&spm=1001.2101.3001.7020)子类。这个返回的[子类](https://so.csdn.net/so/search?q=子类&spm=1001.2101.3001.7020)用于创建类似元组的对象，这些对象具有可通过属性查找访问的字段以及可索引和可迭代的字段。

## ImageDraw

ImageDraw.rectangle(xy, fill=None, outline=None, width=1)

[(98条消息) ImageDraw.rectangle(xy, fill=None, outline=None, width=1)使用举例_敲代码的小风的博客-CSDN博客_imagedraw rectangle](https://blog.csdn.net/m0_46653437/article/details/112050221)

## 保存图片

- PIL `img.save("1.jpg") `
- opencv `cv2.imwrite("1.jpg",img)`
- matplotlib `plt.savefig("./minist.jpg")`

[(98条消息) python保存图片的常用方法_Mr_寒路的博客-CSDN博客_python保存图像](https://blog.csdn.net/weixin_47873308/article/details/113627733)

http://www.kaotop.com/it/21032.html

## 保存矩阵

- np.save('a.npy',a)

  data_a=np.load('a.npy')

- np.savez('ab.npz',k_a=a,k_b=b)

  c=np.load('ab.npz')

  print(c['k_a'])

  print(c['k_b'])

- from sklearn.externals import joblib

  //保存x

  joblib.dump(x, 'x.pkl') 

  //加载x

  x = joblib.load('x.pkl') 

- https://blog.csdn.net/weixin_59644080/article/details/122730474

- **python和matlab交互**

  import numpy as np
  from scipy import io

  a=np.mat('1,2,3;4,5,6')
  b=np.array([[1,1,1],[2,2,2]])

  io.savemat('a.mat', {'matrix': a})
  io.savemat('b.mat', {'array': b})
  **Matlab read:**

  load a -->工作区出现a_matrix

  load b -->工作区出现b_array

  **Python read：**

  c=io.loadmat('a.mat')

  print(c['a_matrix'])

## if __name__ == '__main__'

https://www.cnblogs.com/zzc-Andy/p/15211112.html

## array&asarray

- 都将结构数据转化为Ndarray的数据
- 当数据源是**Ndarray**时，array方法仍会copy出一个**副本**，**占用新的内存**，但asarray方法不会，直接引用了原数据源（即**数据源Ndarray**发生改变时，**array**产生的**不会变**，**asarray**产生的会**随之变化**）

## List 

- len(list)
- list.append(t) t作为一个整体
- list.extend(t)  t中元素逐个添加
- list.insert(1,t) t作为一个整体，索引从0开始
- del list[start:end] 包括start，不包含end
- list.pop(3) 删除第三个（从0开始）
- list.pop() 删除最后一个
- list.remove(36) remove() 方法只会删除第一个和指定值相同的元素，而且必须保证该元素是存在的，否则会引发 ValueError 错误。
- list.clear() 删除列表所有元素
- list[1:5]  list[0]

## tolist()

numpy数组转化为列表

## round

a=1.23444

round(a,3)

1.234

## 多线程Thread

import threading
import time
def test_thread():
      while True:
         print("子线程运行!\n")
         time.sleep(1)

if __name__ == '__main__':
      t = threading.Thread(target=test_thread)
      t.start()
      print('主线程运行..')
      time.sleep(0.6)
      print('主线程运行...')
      time.sleep(0.6)
      print('主线程运行完毕')

- 守护线程：t.daemon = True
- t.join()  阻塞主线程
- t.terminate() 结束子线程
- 子线程里面不要加主线程的变量或全局变量，要不然好像会阻塞主线程

[(111条消息) Python之进程与线程_dr-y的博客-CSDN博客](https://blog.csdn.net/m0_49368195/article/details/107478252)

[(111条消息) Python多进程(process)和多线程(thread)的区别_rs勿忘初心的博客-CSDN博客_python多线程process](https://blog.csdn.net/sinat_33718563/article/details/119716436?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~Rate-2-119716436-blog-85109910.pc_relevant_aa2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~Rate-2-119716436-blog-85109910.pc_relevant_aa2&utm_relevant_index=5)

from multiprocessing import Process, Queue
import os, time, random

**写数据进程执行的代码:**

def write(q):
    for value in ['A', 'B', 'C']:
        print 'Put %s to queue...' % value
        q.put(value)
        time.sleep(random.random())

**读数据进程执行的代码:**

def read(q):
    while True:
        if not q.empty():
            value = q.get(True)
            print 'Get %s from queue.' % value
            time.sleep(random.random())
        else:
            break

if __name__=='__main__':

//父进程创建Queue，并传给各个子进程：

​    q = Queue()
​    pw = Process(target=write, args=(q,))
​    pr = Process(target=read, args=(q,))

//启动子进程pw，写入:

​    pw.start()    

//等待pw结束:

​    pw.join()

//启动子进程pr，读取:

​    pr.start()
​    pr.join()

//pr进程里是死循环，无法等待其结束，只能强行终止:

​    print
​    print '所有数据都写入并且读完'

https://blog.csdn.net/sqzhao/article/details/120732881

## I/O operation on closed file

with open('猫眼.csv', 'a', newline='', encoding="utf8") as f:

## for i in range(12):

0-11

## 延时函数

time.sleep()

## 程序定时循环执行

from threading import Timer
def hello(): 
    print "hello, world" 

t = Timer(10.0, hello) 
t.start()

https://blog.csdn.net/qq_38412868/article/details/100711702

## 获取当前时间

datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S'); 

dt = datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S') 

dt_ms = datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S.%f')//微妙us

'2013-09-17 08:06:17'

[(111条消息) python datetime中strftime用法_高压锅_1220的博客-CSDN博客_datetime.strftime](https://blog.csdn.net/u014651560/article/details/117262618)

## PyQtGraph

画图更快 GLLinePlotItem

[GLLinePlotItem — pyqtgraph 0.13.1.dev0 documentation](https://pyqtgraph.readthedocs.io/en/latest/api_reference/3dgraphics/gllineplotitem.html)

[(111条消息) 【PyQtGraph】显示点云_zhy29563的博客-CSDN博客_pyqtgraph 点云](https://blog.csdn.net/zhy29563/article/details/119757407)

## Object of type ‘ndarray‘ is not JSON serializable

a.tolist()

## scatter

plt.scatter(x, y, s=sizes, c=colors) 散点图

## 字符串比较

if a is b 

if a==b

## Queue

- Queue.qsize()
- Queue.empty()
- Queue.full()
- Queue.get(..)
- Queue.put(..)
- 先进先出

## 定时器

[(111条消息) python实现定时器_小胖_@的博客-CSDN博客_python 定时器](https://blog.csdn.net/weixin_45459224/article/details/102600181)

[(111条消息) python下timer定时器常用的两种实现方法_Python 学习者的博客-CSDN博客_python time 定时](https://blog.csdn.net/sinat_38682860/article/details/120845158)

## 画图

[Python Matplotlib 3D绘图详解（汇总） (biancheng.net)](http://m.biancheng.net/matplotlib/3d-plot.html)

[(111条消息) plt.ion()画动态图_点PY的博客-CSDN博客_plt 动态图](https://blog.csdn.net/weixin_42990464/article/details/112347386#:~:text=plt.ion() ：将 figure 设置为交互模式，figure 不用 plt. show (),show () 才能显示。 plt. show () ：显示所有的 figure（不管是阻塞模式的还是交互模式的）。)

[(111条消息) python多线程实现绘制动态图_浅若清风cyf的博客-CSDN博客_python多线程画图](https://blog.csdn.net/weixin_44002829/article/details/111051266)

[(111条消息) 【Python】PyQt5 实现实时数据显示_普通网友的博客-CSDN博客_pyqt5实时显示数据](https://blog.csdn.net/m0_67401499/article/details/125347510?spm=1001.2101.3001.6650.9&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-9-125347510-blog-121961910.pc_relevant_multi_platform_whitelistv4&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-9-125347510-blog-121961910.pc_relevant_multi_platform_whitelistv4&utm_relevant_index=10)

[(111条消息) python中plot实现即时数据动态显示方法_windSeS的博客-CSDN博客_python实时数据并实时画图](https://blog.csdn.net/u013468614/article/details/58689735)

[Python 如何实时绘制数据 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/165998670)

## 模型部署cpu/gpu

GPU:device = torch.device('cuda:0'if torch.cuda.is_available() else 'cpu')

CPU:device = torch.device('cpu') #默认即在cpu上

部署：net = Network().to(device)
images,labels = images.to(device),labels.to(device)

https://blog.csdn.net/weixin_41848012/article/details/104839214

## 在一个py文件中获取另一个py文件中的值

[(100条消息) python 在一个py文件中获取另一个py文件中的值（一个或多个）_不知名程序媛的博客-CSDN博客_python怎么读取py文件](https://blog.csdn.net/weixin_44606217/article/details/100191200)