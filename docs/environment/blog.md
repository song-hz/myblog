# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

[自动部署网页教程](https://www.ttlarva.com/master/github/06_Mkdocs.html)

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start [the](https://www.jianshu.com/p/f378e3f2e7e1) live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

# mkdocs.yml配置

还没整理的一些网页链接：

[Mkdocs 配置和使用 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/383582472)

[(95条消息) Mkdocs部署静态网页至GitHub pages配置说明(mkdocs.yml)_Wcowin的博客-CSDN博客](https://blog.csdn.net/m0_63203517/article/details/127444446)

[(95条消息) so easy！从头教你用mkdocs构建个人博客系统~_水木子_的博客-CSDN博客_mkdocs](https://blog.csdn.net/qq_41261251/article/details/116021097)



# md文件书写格式

[如何写md格式的文档 - 简书 (jianshu.com)](https://www.jianshu.com/p/f378e3f2e7e1)



## 右键增加md文件创建

1. win+R输入regedit打开注册表

2. 在HKEY_CLASSES_ROOT找到.md文件

3. 将.md中默认值md_auto_file改为Typora.md

4. 若有ShellNew文件夹就可以直接关闭注册表，如果没有

   * 右键.md文件夹 => 新建 => 项，把新建的项命名为"ShellNew"

   - 右键ShellNew => 新建 => 字符串值，将该字符串值名称改为"NullFile"

5. step3&4（已验证成功）的另一种做法是直接新增文件名ShellNew （未验证）
   - 新建字符串值为"NullFile" 
   - 选中新建的NullFile右键修改数值数据输入"typora.md"确定保存

# Typora

[2020Typora小白完全使用教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/293557841)



