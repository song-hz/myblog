# [Python](./Python.md)

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

https://blog.csdn.net/Anne033/article/details/122817857?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-122817857-blog-83996365.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-122817857-blog-83996365.pc_relevant_vip_default&utm_relevant_index=3)



# [Matlab](./matlab.md)



# Overleaf

## 绝对值

[(100条消息) Overleaf中绝对值符号以及\lvert和\mid区别_王大央的博客-CSDN博客_overleaf符号大全](https://blog.csdn.net/weixin_50637207/article/details/126125516)

## 行内行间公式

\begin{equation}

\end{equation}

$...$:行间

[(100条消息) 最全overleaf在线编辑数学公式以及遇到错误的解决方法！_Lesliecc96的博客-CSDN博客_overleaf公式](https://blog.csdn.net/weixin_44699871/article/details/107701731)

## 格式

### 粗体

\textbf

### 斜体

\emph \textit

### 下划线

\underline

## 紧跟制定文字

\begin{table}[H] % 注意，必须是大写的H

[c]是水平居中，[l]水平左居中，[r]水平右居中

## 表格生成器

[Create LaTeX tables online – TablesGenerator.com](https://tablesgenerator.com/)

# error

## AttributeError: Can‘t get attribute ‘xxx‘ on ＜module ‘__main__‘ from ‘xxx‘

某个类没有导入

[(103条消息) 解决pytouch导入模型报错：AttributeError: Can‘t get attribute ‘XXX‘ on ＜module ‘__main__‘ from XXX＞_呆萌的代Ma的博客-CSDN博客](https://blog.csdn.net/weixin_35757704/article/details/115762931?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-115762931-blog-120475329.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-115762931-blog-120475329.pc_relevant_vip_default&utm_relevant_index=2)

## UnicodedecodeError

UnicodedecodeError:gbk codec can't decode
原因：编码方式不对
解决：二进制读取；或者改变编码方式（在open相关的地方加上`encoding='utf-8'`)
[https://blog.csdn.net/qq_31267769/article/details/109128882](https://blog.csdn.net/qq_31267769/article/details/109128882)转载

##  Loaded runtime CuDNN library: 7.4.2 but source was compiled with: 7.6.5.  

 Loaded runtime CuDNN library: 7.4.2 but source was compiled with: 7.6.5.  CuDNN library major and minor version needs to match or have higher minor version in case of CuDNN 7.0 or later version. If using a binary install, upgrade your CuDNN library.

可能是cuda版本错误，调整cuda多版本顺序



