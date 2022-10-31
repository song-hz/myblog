# Anaconda环境相关

## 安装

1. [(95条消息) anaconda安装-超详细版_plasma-deeplearning的博客-CSDN博客_anaconda安装](https://blog.csdn.net/in546/article/details/117400839)

2. [(95条消息) CondaHTTPError: HTTP 000 CONNECTION FAILED for url解决方法（不用换源，简单有效）_风吹我亦散的博客-CSDN博客_condahttperror](https://blog.csdn.net/weixin_45468845/article/details/122516155?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&utm_relevant_index=4)anaconda出现CondaHTTPError问题
   - 博客有点复杂，备选方案吧
   - 应该是源的问题，先用默认源安装  `换回默认源：conda config --remove-key channels`

3. [(95条消息) Anaconda删除源及更改源_郡酱~的博客-CSDN博客_conda清除所有源](https://blog.csdn.net/weixin_40977054/article/details/115524523)
   - 显示目前的源conda config --show channels
   - 删除源conda config --remove channels
   - 添加清华源conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
   
4. 

# pip相关

 1. raise ReadTimeoutError(self._pool, None, 'Read timed out.')
ReadTimeoutError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Read timed out.
原因：网络不好
解决：重试；延长Timeout时间；换源
[https://blog.csdn.net/qq_38316655/article/details/81463917](https://blog.csdn.net/qq_38316655/article/details/81463917)转载


## pip安装包问题

1. [(95条消息) 简单解决twisted 18.7.0 requires PyHamcrest＞=1.9.0, which is not installed.问题_晨风先生的博客-CSDN博客_pyhamcrest>=1.9.0](https://blog.csdn.net/qq_40089560/article/details/114494464?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&utm_relevant_index=3)
   - 重试或者镜像错误利用default安装

2. [(95条消息) ERROR: Cannot uninstall ‘PyYAML‘. It is a distutils installed project and thus we cannot..._#晚来天欲雪的博客-CSDN博客](https://blog.csdn.net/YIZHILIUSHA2020/article/details/125387390)
   - `pip install --ignore-installed pyyaml`忽略已安装的PYYAML包，重新安装
3. 

# conda相关 