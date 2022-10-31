# C++

- 

# python

## 声明

- [(95条消息) python文件头部声明# coding=utf-8_冰美式QAQ的博客-CSDN博客_# coding=utf-8](https://blog.csdn.net/daningliu/article/details/121617391)

## 一些函数

1.[Python globals() 函数 | 菜鸟教程 (runoob.com)](https://www.runoob.com/python/python-func-globals.html)

## 一些库

1. [(95条消息) collections.namedtuple 用法详解完整版_Who is abc的博客-CSDN博客_collections namedtuple](https://blog.csdn.net/m0_37586991/article/details/103713691)
   - 返回的是一个名为 `typename` 的[元组](https://so.csdn.net/so/search?q=元组&spm=1001.2101.3001.7020)子类。这个返回的[子类](https://so.csdn.net/so/search?q=子类&spm=1001.2101.3001.7020)用于创建类似元组的对象，这些对象具有可通过属性查找访问的字段以及可索引和可迭代的字段。
2. 

# terminal

## scp 传输文件

[Linux scp命令 | 菜鸟教程 (runoob.com)](https://www.runoob.com/linux/linux-comm-scp.html)

scp -r -P 8080 shan@2xx.2xx.1xx.1xx:/home/workspace/data /d/data (-P 端口 -r 文件夹)

问题：scp报错：not a regular file 原因：传输的是文件夹非文件 解决：加-r参数

## 不是内部或外部命令

2. “wget”不是内部或外部命令，也不是可运行的程序或批处理文件

   wget是linux系统下自带，windows不自带，去wget官网（[GNU Wget 1.21.3 for Windows](https://eternallybored.org/misc/wget/)）下载：将下载下来的wget.exe文件放到C:\Windows\System32即可。

3. 

# error

## UnicodedecodeError

UnicodedecodeError:gbk codec can't decode
原因：编码方式不对
解决：二进制读取；或者改变编码方式（在open相关的地方加上`encoding='utf-8'`)
[https://blog.csdn.net/qq_31267769/article/details/109128882](https://blog.csdn.net/qq_31267769/article/details/109128882)转载





