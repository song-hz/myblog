# Anaconda

## Anaconda环境相关

### 安装

- [(95条消息) anaconda安装-超详细版_plasma-deeplearning的博客-CSDN博客_anaconda安装](https://blog.csdn.net/in546/article/details/117400839)

- [(95条消息) CondaHTTPError: HTTP 000 CONNECTION FAILED for url解决方法（不用换源，简单有效）_风吹我亦散的博客-CSDN博客_condahttperror](https://blog.csdn.net/weixin_45468845/article/details/122516155?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&utm_relevant_index=4)anaconda出现CondaHTTPError问题

  博客有点复杂，备选方案吧

  应该是源的问题，先用默认源安装  `换回默认源：conda config --remove-key channels`

- [(95条消息) Anaconda删除源及更改源_郡酱~的博客-CSDN博客_conda清除所有源](https://blog.csdn.net/weixin_40977054/article/details/115524523)

  显示目前的源conda config --show channels

  删除源conda config --remove channels

  添加清华源conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/



## pip相关

### ReadTimeoutError

raise ReadTimeoutError(self._pool, None, 'Read timed out.')
ReadTimeoutError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Read timed out.
原因：网络不好
解决：重试；延长Timeout时间；换源
[https://blog.csdn.net/qq_38316655/article/details/81463917](https://blog.csdn.net/qq_38316655/article/details/81463917)转载


### pip安装包问题

### PyHarmcrest

[(95条消息) 简单解决twisted 18.7.0 requires PyHamcrest＞=1.9.0, which is not installed.问题_晨风先生的博客-CSDN博客_pyhamcrest>=1.9.0](https://blog.csdn.net/qq_40089560/article/details/114494464?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&utm_relevant_index=3)

重试或者镜像错误利用default安装

### PyYAML

[(95条消息) ERROR: Cannot uninstall ‘PyYAML‘. It is a distutils installed project and thus we cannot..._#晚来天欲雪的博客-CSDN博客](https://blog.csdn.net/YIZHILIUSHA2020/article/details/125387390)

- `pip install --ignore-installed pyyaml`忽略已安装的PYYAML包，重新安装

  

## conda相关 



# Blog

## MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

[自动部署网页教程](https://www.ttlarva.com/master/github/06_Mkdocs.html)

### mkdocs.yml配置

还没整理的一些网页链接：

[Mkdocs 配置和使用 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/383582472)

[(95条消息) Mkdocs部署静态网页至GitHub pages配置说明(mkdocs.yml)_Wcowin的博客-CSDN博客](https://blog.csdn.net/m0_63203517/article/details/127444446)

[(95条消息) so easy！从头教你用mkdocs构建个人博客系统~_水木子_的博客-CSDN博客_mkdocs](https://blog.csdn.net/qq_41261251/article/details/116021097)

### Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start [the](https://www.jianshu.com/p/f378e3f2e7e1) live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Typora

[2020Typora小白完全使用教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/293557841)

### md文件书写格式

[如何写md格式的文档 - 简书 (jianshu.com)](https://www.jianshu.com/p/f378e3f2e7e1)

### 右键增加md文件创建

1. win+R输入regedit打开注册表

2. 在HKEY_CLASSES_ROOT找到.md文件

3. 将.md中默认值md_auto_file改为Typora.md

4. 若有ShellNew文件夹就可以直接关闭注册表，如果没有

   * 右键.md文件夹 => 新建 => 项，把新建的项命名为"ShellNew"

   - 右键ShellNew => 新建 => 字符串值，将该字符串值名称改为"NullFile"

5. step3&4（已验证成功）的另一种做法是直接新增文件名ShellNew （未验证）

   - 新建字符串值为"NullFile" 
   - 选中新建的NullFile右键修改数值数据输入"typora.md"确定保存



# Vscode

## 插件安装

- Markdown文件预览：安装Markdown All in One\Markdown Preview Enhanced\Markdown Shortcuts
- 改中英文：【Ctrl+Shift+P】->configure Display Language

# [Git相关](./git.md)

