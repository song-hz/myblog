# Anaconda

## Anaconda环境相关

### 安装

1. [(95条消息) anaconda安装-超详细版_plasma-deeplearning的博客-CSDN博客_anaconda安装](https://blog.csdn.net/in546/article/details/117400839)

2. [(95条消息) CondaHTTPError: HTTP 000 CONNECTION FAILED for url解决方法（不用换源，简单有效）_风吹我亦散的博客-CSDN博客_condahttperror](https://blog.csdn.net/weixin_45468845/article/details/122516155?spm=1001.2101.3001.6650.3&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-3-122516155-blog-122179000.pc_relevant_vip_default&utm_relevant_index=4)anaconda出现CondaHTTPError问题
   - 博客有点复杂，备选方案吧
   - 应该是源的问题，先用默认源安装  `换回默认源：conda config --remove-key channels`

3. [(95条消息) Anaconda删除源及更改源_郡酱~的博客-CSDN博客_conda清除所有源](https://blog.csdn.net/weixin_40977054/article/details/115524523)
   - 显示目前的源conda config --show channels
   - 删除源conda config --remove channels
   - 添加清华源conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/

4. 

## pip相关

  1. raise ReadTimeoutError(self._pool, None, 'Read timed out.')
     ReadTimeoutError: HTTPSConnectionPool(host='files.pythonhosted.org', port=443): Read timed out.
     原因：网络不好
     解决：重试；延长Timeout时间；换源
     [https://blog.csdn.net/qq_38316655/article/details/81463917](https://blog.csdn.net/qq_38316655/article/details/81463917)转载


### pip安装包问题

1. [(95条消息) 简单解决twisted 18.7.0 requires PyHamcrest＞=1.9.0, which is not installed.问题_晨风先生的博客-CSDN博客_pyhamcrest>=1.9.0](https://blog.csdn.net/qq_40089560/article/details/114494464?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-2-114494464-blog-104803803.pc_relevant_vip_default&utm_relevant_index=3)
   - 重试或者镜像错误利用default安装

2. [(95条消息) ERROR: Cannot uninstall ‘PyYAML‘. It is a distutils installed project and thus we cannot..._#晚来天欲雪的博客-CSDN博客](https://blog.csdn.net/YIZHILIUSHA2020/article/details/125387390)
   - `pip install --ignore-installed pyyaml`忽略已安装的PYYAML包，重新安装
3. 

## conda相关 



# Blog

## Welcome to MkDocs

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

## mkdocs.yml配置

还没整理的一些网页链接：

[Mkdocs 配置和使用 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/383582472)

[(95条消息) Mkdocs部署静态网页至GitHub pages配置说明(mkdocs.yml)_Wcowin的博客-CSDN博客](https://blog.csdn.net/m0_63203517/article/details/127444446)

[(95条消息) so easy！从头教你用mkdocs构建个人博客系统~_水木子_的博客-CSDN博客_mkdocs](https://blog.csdn.net/qq_41261251/article/details/116021097)

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



# tools

## Vscode

### 插件安装

- Markdown文件预览：安装Markdown All in One\Markdown Preview Enhanced\Markdown Shortcuts
- 改中英文：【Ctrl+Shift+P】->configure Display Language

## Git

### Git安装

- [(95条消息) Git 详细安装教程（详解 Git 安装过程的每一个步骤）_mukes的博客-CSDN博客_git安装](https://blog.csdn.net/mukes/article/details/115693833)

  非常详细的步骤

- [(95条消息) 【已解决】git 不是内部或外部命令，也不是可运行的程序_Andone_hsx的博客-CSDN博客_git' 不是内部或外部命令,也不是可运行的程序](https://blog.csdn.net/Andone_hsx/article/details/87937329)

  加系统路径并重新开窗口

### Git SSH设置key

- 设置全局的username和email

  ```bash
  git config --global user.name  "name"//自定义用户名
  git config --global user.email "youxiang@qq.com"//用户邮箱
  ```

  - `git config --global configname configvalue`修改
  - `git config --global configname`查询
  - `git config --list`查询全部
  - `git config user.name`查看用户名
  - `git config user.email`查看用户邮箱地址

- 使用cd ~/.ssh可以查看是否已配置SSH。如果有的话会进入.ssh路径，否则会告知无此路径

- 生成SSH Key

  ```bash
  ssh-keygen -t rsa -C "youxiang@qq.com"  (直接回车三下)
  ```

- .ssh文件夹下会有 id_rsa(私钥，勿泄漏)，id_rsa.pub(公钥，可公开)

  `cat ~/.ssh/id_rsa.pub`查看公钥

- Github网页上Account settings->SSH Keys->New SSHkey ->title随意，key填写id_rsa.pub的全部内容

- 验证

  ```bash
  ssh -T git@github.com
  ```

  初次设置出现Are you sure you want to continue connecting (yes/no)?输入yes

### Github建立连接

- GitHub上创建仓库,注意不要勾选initialize with a readme,否则关联本地仓库时要首先执行git pull 不然会导致错误

- git进入本地文件夹目录，git init初始化本地文件

- 连接远程仓库(二选一)

  ```bash
  git remote add origin git@github.com:yourName/respositoryname.git
  git remote add origin https://github.com/yourname/repositoryname.git
  ```

- 从远程仓库拉取文件（若远程仓库没有文件可跳过）

  ```bash
  git pull origin "分支名"
  (git pull --rebase origin "分支名"
  ```

- 查看工作目录状态

  ```bash
  git status
  ```

  - 红字表示未add到Git仓库上的文件
  - 绿字表示已add到Git仓库上的文件

- 本地文件push到远程仓库

  ```ba
  git add <文件> #将文件添加到暂存区
  git commit -m "comment"  #提交更改（此时将暂存区的信息提交到本地仓库）
  git push -u origin master  #将本地仓库的文件push到远程仓库
  ```

  第一次`push`的时候,加上`-u`参数,Git就会把本地的master分支和远程的master分支进行关联起来,我们以后的`push`操作就不再需要加上`-u`参数了

### Github删除连接

如果添加的时候地址写错了，或者就是想删除远程库

- `git remote -v`查看远程库信息信息

  - fetch & push 实现从一个库fetch更新当前项目，向另一个库push提交最新代码（大多一样）
  - Git添加远程仓库`git remote add [远程仓库别名] <远程仓库URL>`
  - Git修改指定远程仓库的push地址`git remote set-url --push <远程仓库别名> <远程仓库URL>`

- 根据名字删除库

  ```bash
  git remote rm origin
  ```

  此处的“删除”其实是解除了本地和远程的绑定关系，并不是物理上删除了远程库。远程库本身并没有任何改动。

- 修改仓库名

  ```bash 
  git remote rename old_name new_name
  ```

### GitHub操作

- setting滑到最底端可以change visibility和删除库

- code-branches处可以删除或者增加分支

  `git branch`列出所有分支

  `git branch newbranch` 创建新分支

  `git merge newbranch` 将新分支提交的改动合并到主分支上

  `git branch -a`显示所有分支-本地和远程

  `git branch -d local_branch_name`删除本地分支（先转移到其他分支 ）

  `git push remote_name -d remote_branch_name`删除远程分支

  `git checkout branch_name` 转移到另一分支上

### git提交文件

- `git add .`
- `git comment -m "comments"`
- `git push origin main`可能需要多试几次

### git常见错误

1. fatal: Not a git repository (or any of the parent directories): .git

- `git init`

2. [(95条消息) Git 常见错误 之 error:error: src refspec main does not match any/ error: failed to push some refs to 简单解决_千寻简的博客-CSDN博客](https://blog.csdn.net/IUTStar/article/details/123078006)

   本地分支和远程分支不相同（main vs master)

3. [(95条消息) git提交或克隆报错fatal: unable to access ‘https://github.com/tata20191003/autowrite.git/‘: Failed to connec_good_good_xiu的博客-CSDN博客](https://blog.csdn.net/good_good_xiu/article/details/118567249)

   - 问题：OpenSSL SSL_read: Connection was reset, errno 10054 ；Failed to connect to github.com port 443: Timed out

   - 原因：因为git在拉取或者提交项目时，中间会有git的http和https代理，但是我们本地环境本身就有[SSL](https://so.csdn.net/so/search?q=SSL&spm=1001.2101.3001.7020)协议了，所以取消git的https代理即可，不行再取消http的代理。或者当前代理网速过慢，所以偶尔会成功，偶尔失败。

   - 解决：取消git本身的https代理，使用自己本机的代理，如果没有的话，其实默认还是用git的

     `git config --global --unset http.proxy`

     `git config --global --unset https.proxy`

     or `git config --global http.sslVerify "false"`

     重试几次

4. nothing added to commit but untracked files present问题

- git add .

5. ! [rejected] gh-pages -> gh-pages (non-fast-forward) or error: failed to push some refs to

   远程仓库有本地没有的更新，需要先合并在push

   - `git pull origin master` or `git pull --rebase origin master`
   - 丢弃之前历史，用本地代码全覆盖（谨慎）`git push --force` or `gitpush -f`

6. Everything up-to-date问题；nothing to commit, working tree clean

   - 忘记add和commit步骤 
   - 运行git config core.ignorecase false，关闭git忽略大小写配置，即可检测到大小写名称更改
   - check `git status`

7. [git commit 时出现：please enter the commit message for your changes - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/133331582)

   - 原因：git commit 未提交本次说明
   - 按键盘左上角"Esc" 输入":wq",注意是冒号+wq,按回车键即可 or 按键盘字母 i 进入insert模式
   - 记得加-m 加说明信息



