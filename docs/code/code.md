# python

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

# terminal

## scp 传输文件

[Linux scp命令 | 菜鸟教程 (runoob.com)](https://www.runoob.com/linux/linux-comm-scp.html)

scp -r -P 8080 shan@2xx.2xx.1xx.1xx:/home/workspace/data /d/data (-P 端口 -r 文件夹)

问题：scp报错：not a regular file 原因：传输的是文件夹非文件 解决：加-r参数

## 不是内部或外部命令

- “wget”不是内部或外部命令，也不是可运行的程序或批处理文件

wget是linux系统下自带，windows不自带，去wget官网（[GNU Wget 1.21.3 for Windows](https://eternallybored.org/misc/wget/)）下载：将下载下来的wget.exe文件放到C:\Windows\System32即可。

- sh/bash不是内部或外部命令

  安装Git     conda install git

## kill

kill -9 5188  （5188指PID）

ps -ef | grep XXXX.sh   (查看进程编号)

# Matlab

## 函数

### norm

n=norm(A,p) p-范数

[(98条消息) MATLAB中范数norm()函数精讲_爱趣无穷的博客-CSDN博客_matlab norm](https://blog.csdn.net/weixin_40857506/article/details/120436911)

### 左除右除

- 左除A\B=inv(A)*B
- 右除B/A=B*inv(A)

### vrho

求谱半径

### tril、triu

tril 矩阵下三角部分 triu举证上三角部分

### pgm读写

- cover=imread('1.pgm')

- stego=unit(stego);

  imwrite(stego,'stego.pgm')

### 获取文件夹下所有名称

coverPath = ‘E:\song_study\images’;

dirOutput=dir(fullfile(coverpath,'*.pgm'));

for i=1:size(dirOutput,1)

​	name=dirOutput(i).name;

​	pgmPath=fullfile(coverPath,name);

​	cover=imread(pgmPath);

end

### 字符串处理

str=['show_',num2str(i)];

str=fullfile('show','image.pgm');

fprintf(' %d- DONE\n',i);

### 既有数组又有字符

changerate=cell(size(dirOutput,1),2);

changerate{1,1}=name;

changerate{1,2}=sum(cover(:)~=stego(:))/numel(cover);

(或者考虑用struct，但是不知道如何动态赋值)

### 矩阵拼接

A=[];

A=[A [1,2]]; A=[A,[1,2]];行拼接  A=[A;[1;2]]；列拼接

### 保存变量

save('name.mat','variable1','variable2')

### 整除 求余

rem(a,b)==0  a整除b,结果符号与a相同

mod(a,b)==0  a整除b,结果符号与b相同

### single函数

一般来说，大矩阵计算，如果用single类型的数据能节省一半的内存空间,double数据类型占8个字节，single类型占4个字节，matlab在内部执行的时候是默认转换成double类型进行运算，据说可以从菜单里面改设置变成默认single 未尝试过，matlab里面有single命令可以转换数据格式

## 画图

### 均值加标准差

Average=[12,11,7,7,6,5];
Variance=[0.5,0.4,0.3,1,0.3,0.5];
Time=0:1:5;

errorbar(Time,Average,Variance,'-or')

### 坐标轴

xlim([0.05 0.55]);
ylim([0 0.5]);
xticks([0.1 0.2 0.3 0.4 0.5]);
yticks([0 0.1 0.2 0.3 0.4 0.5]);

### 网格

ax=gca;

ax.YGrid='on'

## 设置

### 设置打印精确度

- format long

```
>> str=['the value of pi=' num2str(pi)];
>> disp(str);
the value of pi=3.1416
```

[(98条消息) MATLAB 显示输出数据的三种方式_Anne033的博客-CSDN博客_matlab输出](https://blog.csdn.net/Anne033/article/details/122817857?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-122817857-blog-83996365.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-122817857-blog-83996365.pc_relevant_vip_default&utm_relevant_index=3)



# error

## UnicodedecodeError

UnicodedecodeError:gbk codec can't decode
原因：编码方式不对
解决：二进制读取；或者改变编码方式（在open相关的地方加上`encoding='utf-8'`)
[https://blog.csdn.net/qq_31267769/article/details/109128882](https://blog.csdn.net/qq_31267769/article/details/109128882)转载





