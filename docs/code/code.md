# Verilog

[6.3 Verilog 状态机 | 菜鸟教程 (runoob.com)](https://www.runoob.com/w3cnote/verilog-fsm.html)

[(121条消息) Verilog的$readmemb和$readmemh简介和使用_panhongfeng111的博客-CSDN博客_$readmemh](https://blog.csdn.net/qq_33231534/article/details/106167484?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-106167484-blog-79598647.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-106167484-blog-79598647.pc_relevant_vip_default&utm_relevant_index=2)



# C/C++

## CmakeList

[(122条消息) CMakeLists学习一、find_package查找包_RuiH.AI的博客-CSDN博客_cmakelist find_package](https://blog.csdn.net/qq_41035283/article/details/122469466)

[(122条消息) CMakeLists.txt链接库的基本套路_Jolen_xie的博客-CSDN博客_cmakelist 链接库](https://blog.csdn.net/Jolen_xie/article/details/119933088#:~:text=CMakeLists.txt链接库的基本套路 1 查找库文件（find_package命令） 2 判断是否找到库文件（XXX_FOUND标记），并包含头文件（include_directories命令） 3 链接库文件到目标（target_link_libraries命令） 因此，库文件、头文件的名字（大小写）我们就要清楚的写明，不要混淆。我常用的库如OpenCV%2C,Eigen等，其用法如下。常用的变量有：name_INCLUDE_DIRS%2C name_INCLUDE_DIR%2C NAME_INCLUDE_DIRS%2C NAME_INCLUDE_DIR%3B name_LIBS%2C NAME_LIBS%2C name_LIBRARIES%2C NAME_LIBRARIES等。)

[(122条消息) CMakeLists详解_淡墨映雪的博客-CSDN博客_cmakelists](https://blog.csdn.net/weixin_43837968/article/details/115257575)

## strcmp

[(113条消息) 关于字符串比较函数strcmp返回值的问题_樱风凛的博客-CSDN博客_strcmp返回值](https://blog.csdn.net/fayecy/article/details/42191913)

1.一般来说，返回值会是：1 0 -1

2.有些会把两个字符的ASCII码之差作为比较结果由函数值返回。

## 清除字符串

memset(name,'\0',sizeof(name))

memset(a, 0, sizeof a);          //清空数组 

[(113条消息) C语言直接清空数组、字符串_Vegdie的博客-CSDN博客_c语言清空字符串数组](https://blog.csdn.net/cool99781/article/details/106388593)

[(113条消息) 将字符串数组清空的操作_neeJack的博客-CSDN博客_清空字符数组](https://blog.csdn.net/neeJack/article/details/51557375)

# [Python](./Python.md)



# VScode

## remote ssh

- 搜索ssh 安装Remote - SSH

- ssh name@xxx.xxx.xxx.xxx
- 选择\.ssh\config:  Host 连接名称 Hostname 要连接的服务器ip Port 端口 User 需要登录的用户



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

## %号怎么打

加上$

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



