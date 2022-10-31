# Git安装

- [(95条消息) Git 详细安装教程（详解 Git 安装过程的每一个步骤）_mukes的博客-CSDN博客_git安装](https://blog.csdn.net/mukes/article/details/115693833)

  非常详细的步骤

- [(95条消息) 【已解决】git 不是内部或外部命令，也不是可运行的程序_Andone_hsx的博客-CSDN博客_git' 不是内部或外部命令,也不是可运行的程序](https://blog.csdn.net/Andone_hsx/article/details/87937329)

  加系统路径并重新开窗口

# Git SSH设置key

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

# Github建立连接

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

# Github删除连接

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

# GitHub操作

- setting滑到最底端可以change visibility和删除库

- code-branches处可以删除或者增加分支

  `git branch`列出所有分支

  `git branch newbranch` 创建新分支

  `git merge newbranch` 将新分支提交的改动合并到主分支上

  `git branch -a`显示所有分支-本地和远程

  `git branch -d local_branch_name`删除本地分支（先转移到其他分支 ）

  `git push remote_name -d remote_branch_name`删除远程分支

  `git checkout branch_name` 转移到另一分支上

# git提交文件

- `git add .`
- `git comment -m "comments"`
- `git push origin main`可能需要多试几次

# git常见错误

## Not a git repository

fatal: Not a git repository (or any of the parent directories): .git

- `git init`

## src refspec main does not match any

[(95条消息) Git 常见错误 之 error:error: src refspec main does not match any/ error: failed to push some refs to 简单解决_千寻简的博客-CSDN博客](https://blog.csdn.net/IUTStar/article/details/123078006)

本地分支和远程分支不相同（main vs master)

## unable to access

[(95条消息) git提交或克隆报错fatal: unable to access ‘https://github.com/tata20191003/autowrite.git/‘: Failed to connec_good_good_xiu的博客-CSDN博客](https://blog.csdn.net/good_good_xiu/article/details/118567249)

- 问题：OpenSSL SSL_read: Connection was reset, errno 10054 ；Failed to connect to github.com port 443: Timed out

- 原因：因为git在拉取或者提交项目时，中间会有git的http和https代理，但是我们本地环境本身就有[SSL](https://so.csdn.net/so/search?q=SSL&spm=1001.2101.3001.7020)协议了，所以取消git的https代理即可，不行再取消http的代理。或者当前代理网速过慢，所以偶尔会成功，偶尔失败。

- 解决：取消git本身的https代理，使用自己本机的代理，如果没有的话，其实默认还是用git的

  `git config --global --unset http.proxy`

  `git config --global --unset https.proxy`

  or `git config --global http.sslVerify "false"`

  重试几次

## nothing added to commit

nothing added to commit but untracked files present问题

- git add .

## ! [rejected] 

! [rejected] gh-pages -> gh-pages (non-fast-forward) or error: failed to push some refs to

远程仓库有本地没有的更新，需要先合并在push

- `git pull origin master` or `git pull --rebase origin master`
- 丢弃之前历史，用本地代码全覆盖（谨慎）`git push --force` or `gitpush -f`

## Everything up-to-date

Everything up-to-date问题；nothing to commit, working tree clean

- 忘记add和commit步骤 
- 运行git config core.ignorecase false，关闭git忽略大小写配置，即可检测到大小写名称更改
- check `git status`

## Please enter the commit message

[git commit 时出现：please enter the commit message for your changes - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/133331582)

- 原因：git commit 未提交本次说明
- 按键盘左上角"Esc" 输入":wq",注意是冒号+wq,按回车键即可 or 按键盘字母 i 进入insert模式
- 记得加-m 加说明信息



