# scp 传输文件

[Linux scp命令 | 菜鸟教程 (runoob.com)](https://www.runoob.com/linux/linux-comm-scp.html)

scp -r -P 8080 shan@2xx.2xx.1xx.1xx:/home/workspace/data /d/data (-P 端口 -r 文件夹)

问题：scp报错：not a regular file 原因：传输的是文件夹非文件 解决：加-r参数

# 不是内部或外部命令

2. “wget”不是内部或外部命令，也不是可运行的程序或批处理文件

   wget是linux系统下自带，windows不自带，去wget官网（[GNU Wget 1.21.3 for Windows](https://eternallybored.org/misc/wget/)）下载：将下载下来的wget.exe文件放到C:\Windows\System32即可。

3. 