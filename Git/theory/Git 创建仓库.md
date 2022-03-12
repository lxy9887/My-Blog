[TOC]



#### 1、配置Git

设置用户名和邮箱

![image-20220307203946019](E:\TXT\Blogimge\image-20220307203946019.png)

#### 2、本地仓库Git命令

* 提交文件到git本地仓库

```bash
code . #用VScode打开当前目录
start . #打开当前目录
```

```bash
git init  #是创建本地仓库
git add  #是提交到暂存区
git status #查看暂存区
git commit -m "提交的理由" #是提交到本地仓库 如果名字里面有空格要用引号
```

✨删除本地仓库的数据 也是用 git add 来操作的

```bash
rm 1.txt
git add 1.txt
git commit -m "删除1.txt"
git status #查看删除状态
```

![image-20220307202411131](E:\TXT\Blogimge\image-20220307202411131.png)

* 创建 .gitignore #是不需要提交的变动

```bash
git commit -v #打开code 进行文件描述 并且可以看到哪个进行了变动 然后提交。
```

```bash
git log #查看有多少个版本 按ESC 再按Q  只可以看提交的文件
```

* 取回git仓库中的文件  

  ```bash
  git reset --hard xxxxxx  # 这里XXXXXX是提交号的前六位
  一定要确保已经把所有的代码commit 否则会使的没有commit的变动消失
  ```

  +-号是这一次的删减和上一次的对比。

  eg：

  先用 git log 查看所有版本的提交号
  
  ![image-20220306223133094](E:\TXT\Blogimge\image-20220306223133094.png)

这里efd5fc 就是“测试可不可以进行提及教导本地库”文件的提交号

![image-20220306223533269](E:\TXT\Blogimge\image-20220306223533269.png)

这样就文件1.html的内容就回到了 这个版本。

```bash
git reflog #看所有操作的历史  注意 按Q回到 bash页面。找到代号
再用 git reset --hard XXXXXX 回去
```

```
history 可以查看历史
```

查看历史可以看到之前的提交号，因此也可以通过git reset --hard 回到之前的版本。只要是commit过的文件都可以回来，如果没有commit 则代码则会消失。

#### 3、 git分支

```bash
git branch X # 基于当前树枝长出的新树枝 x可以是任意的名字
git checkout X #切换到分支中
git checkout master #再次切换到主分支上
```

![image-20220307192139077](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220307192139077.png)

如果使用 git reset --hard XXXXXXX 则主线路 也可以出现分支路线的文件 这一点要注意。

当前目录有未提交的代码，只要跟另一个分支不冲突，就不需要理会。

如果冲突了，就可以使用 git stash ，或者合并冲突。

```bash
git branch # 来查看所在的分支
```

![image-20220307194851791](E:\TXT\Blogimge\image-20220307194851791.png)

哪个上面有*号就说明在哪个分支上面。

#### 4、合并分支与解决冲突

**合并：**先切换到想保留的分支，

```bash
git checkout master
git merge x  # 就是你想要合并的分支
```

**解决冲突：**这时候如果出现冲突，（更改同样的内容）

```bash
git status #查看哪里出了问题
或者 git status -sb #查看冲突
```

![image-20220307195513140](E:\TXT\Blogimge\image-20220307195513140.png)

在==============================上面是当前主分支更改，下面是分支的更改，当两个分支冲突时，可以选择采用当前更改，采用传入更改，保留双方更改，比较变更，

最简单的是 ==鼠标选择==  直接删掉。

比如 在VScode 中 用ctrl +F 进行搜索 ==============================，如果全要 就要删除 这三个标记。![image-20220307195921682](E:\TXT\Blogimge\image-20220307195921682.png)

![image-20220307195929237](E:\TXT\Blogimge\image-20220307195929237.png)

![image-20220307195936905](E:\TXT\Blogimge\image-20220307195936905.png)

如果只要某几个 就删除不要的，再删除上述标记。

一定要进行commit 提交

```bash
git add 文件
git commit  #这里不用标记名字直接commit
get log # 进行·查询 发现有两个分支的文件
```

![image-20220307201114368](E:\TXT\Blogimge\image-20220307201114368.png)

**删除分支**

```bash
git branch -d x #对x分支进行删除
```

![image-20220307202112046](E:\TXT\Blogimge\image-20220307202112046.png)

#### 5、创建远程仓库 （上传云端）

![image-20220307210058243](E:\TXT\Blogimge\image-20220307210058243.png)

* **生成ssh key**

  * GitHub 有帮助文档可以查询
  * 运行ssh-keygen-t rsa -b 4096 -C
  * 然后回车
  * ![image-20220308143842556](E:\TXT\Blogimge\image-20220308143842556.png)
  * cat~/.ssh/id_rsa.pub 或者找到C盘 .ssh 文件夹中的id_rsa.pub用VScode 打开可以看到公钥
  *  得到公钥内容 ，粘贴到GitHub
  *  ![image-20220308144007879](E:\TXT\Blogimge\image-20220308144007879.png)
  * 打开GitHub 这设置页面输入公钥。
  * 在cmder中测试 ssh-Tgit@github.com
  * 如果问你yes/no 请回答yes并回车

注释：**ssh-keygen -t rsa -b 4096 -C "邮箱"：这条命令的目的是为了让本地机器ssh登录远程机器上的GitHub账户无需输入密码。对该命令进行分解：**

**ssh-keygen**

SSH 为 Secure Shell 的缩写，SSH 为建立在应用层基础上的安全协议。SSH 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。利用 SSH 协议可以有效防止远程管理过程中的信息泄露问题。
		
从客户端来看，SSH提供两种级别的安全验证：
	
第一种级别（基于口令的安全验证）：只要你知道自己帐号和口令，就可以登录到远程主机。所有传输的数据都会被加密，但是不能保证你正在连接的服务器就是你想连接的服务器。可能会有别的服务器在冒充真正的服务器，也就是受到“中间人”这种方式的攻击。
	
第二种级别（基于密匙的安全验证）ssh-keygen：需要依靠密匙，你必须为自己创建一对密匙，并把公用密匙放在需要访问的服务器上。如果你要连接到SSH服务器上，客户端软件就会向服务器发出请求，请求用你的密匙进行安全验证。服务器收到请求之后，先在该服务器上你的主目录下寻找你的公用密匙，然后把它和你发送过来的公用密匙进行比较。如果两个密匙一致，服务器就用公用密匙加密“质询”（challenge）并把它发送给客户端软件。客户端软件收到“质询”之后就可以用你的私人密匙解密再把它发送给服务器。用这种方式，你必须知道自己密匙的口令。但是，与第一种级别相比，第二种级别不需要在网络上传送口令。第二种级别不仅加密所有传送的数据，而且“中间人”这种攻击方式也是不可能的（因为他没有你的私人密匙）。但是整个登录的过程可能需要10秒 。
	
ssh-keygen有很多的参数，比如这里的-t -b -C都是他的一些参数

**-t rsa**

-t即指定密钥的类型，密钥的类型有两种，一种是RSA，一种是DSA：
	
RSA：RSA加密算法是一种非对称加密算法，是由三个麻省理工的牛人弄出来的，RSA是他们三个人姓的开头首字母组合。
	
DSA：Digital Signature Algorithm (DSA)是Schnorr和ElGamal签名算法的变种。
	
为了让两个linux机器之间使用ssh不需要用户名和密码。所以**采用了数字签名RSA或者DSA来完成这个操作。ssh-keygen默认使用rsa密钥**，所以不加-t rsa也行，如果你想生成dsa密钥，就需要加参数-t dsa。

**-b 4096**

-b 指定密钥长度。对于RSA密钥，最小要求768位，默认是2048位。命令中的4096指的是RSA密钥长度为4096位。

DSA密钥必须恰好是1024位(FIPS 186-2 标准的要求)。

命令后面还可以增加-C "注释内容"
	
补充：

-C表示要提供一个新注释，用于识别这个密钥，可以是任何内容,一个用来识别的key

**小结：当你创建ssh的时候：-t 表示密钥的类型 ，-b表示密钥的长度，-C 用于识别这个密钥的注释 ，这个注释你可以输入任何内容**

* Github上建立远程仓库
* ![image-20220308144212713](E:\TXT\Blogimge\image-20220308144212713.png)

* 选择ssh形网址

![image-20220308144308486](E:\TXT\Blogimge\image-20220308144308486.png)

在本地仓库文件夹输入图片上面的绑定代码，即可实现第一次Github远程上传。

![image-20220308145223388](E:\TXT\Blogimge\image-20220308145223388.png)

只提交选中的一条分支，不会所有分支都进行提交。

#### 6、上传代码到远程仓库

![image-20220308160224732](E:\TXT\Blogimge\image-20220308160224732.png)

首先确保你的暂存文件已经上传到本地仓库，

```bash
git push -u origin main #第一次上传时使用 -u origin main
  代表着记住第一次上传到远程仓库的main 分支的路线。
  下次更新时，直接在主分支 
  git push 即可
```

其次 ，若本地仓库有多个分支，则需要切换到分支中

```bash
git push origin x:x #可以将本地的x分支上传到远程x分支
**********************
git checkout x #切换到x 分支
git push -u origin x # 第一次上传X分支时候使用，
git push #以后上传 直接切换到分支 输入即可
```

![image-20220308160212118](E:\TXT\Blogimge\image-20220308160212118.png)

```bash
git push -u origin master -f #加了-f 就表示强制执行提交
```

其实远程仓库只是本地仓库的一个拷贝而已

#### 7、下载代码 （每次克隆就是克隆所有的分支）

* 下载自己的代码就直接使用ssh 不能在有仓库的地方进行克隆。

* ```bash
  git clone ssh 网址
  ```

* ```bash
  cd "下载的文件夹"  #进入文件夹
  ```

* ```bash
  git checkout "分支名称" #可以进入分支
  ```

* 下载别人的代码时候只能够用HTTPS下载，不能用SSH下载

* 如果别人远程更改了代码，需要先git pull 再git push

  ![image-20220308164555374](E:\TXT\Blogimge\image-20220308164555374.png)

  ```bash
  git clone git@?/XXX.git # 直接下载相应名字的仓库
  git clone git@?/XXX.git "你想要的文件夹名字" #改变下载仓库的名字
  git clone git@?/XXX.git . #直接加. 把仓库下载到当前目录
  ```

![image-20220308165131503](E:\TXT\Blogimge\image-20220308165131503.png)

**下载某个分支：**

基本上都是下载整个仓库然后 切换到某个分支

有更复杂的代码 但是不常用。

#### 8、远程仓库

创建一个远程仓库

```bash
git remote add "远程仓库的名字 一般默认origin" + ssh 网址
```

```bash
git remote #查看远程绑定的
```

```bash
git push -u "仓库名字" main /其他分支
```

删除远程仓库

```bash
git remote rm "仓库名称"
```

#### 9、上传到两个仓库

![image-20220308170005954](E:\TXT\Blogimge\image-20220308170005954.png)

![image-20220308170257069](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220308170257069.png)

#### 10、删除远程仓库的某个文件夹

* 方法一，首先进入你的main文件夹下，git pull origin main 讲远程仓库的项目拉下来， 然后进入文件夹 进行 rm 文件/rm -r 文件夹的删除操作，在进行 git add 以及 git commit -v 的操作后 git push -u origin main 讲操作传到GitHub上去
* 方法二 使用git clone .ssh地址，讲远程仓库克隆过来 然后 进行操作。
* **删除本地仓库的方法** 进入本地仓库后 输入 ls -a 查看本地隐藏目录，然后强制删除.git文件夹  这里使用 rm -rf .git   然后删除本地仓库文件夹即可 。

#### 11、git 高级操作

让命令变得简单，.bashrc就

```bash
git add = ga
vi ~/.bashrc #创建简单符号
```

![image-20220308200611386](E:\TXT\Blogimge\image-20220308200611386.png)

```bash
source ~/.bashrc #执行这个命令
```

其他方法，bash 提示符允许你自定义你的终端，并让它在你运行命令时显示提示。自定义的 bash 提示符着实能提高你在终端的工作效率。

看看这些即[有用](https://www.maketecheasier.com/8-useful-and-interesting-bash-prompts/)又[有趣](https://www.maketecheasier.com/more-useful-and-interesting-bash-prompts/)的 bash 提示符，你可以把它们添加到你的 `.bashrc` 里。

![image-20220308201139978](E:\TXT\Blogimge\image-20220308201139978.png)

```
git rebase -i XXXX #美化操作历史
```

![image-20220308202243688](E:\TXT\Blogimge\image-20220308202243688.png)

![image-20220308202332260](E:\TXT\Blogimge\image-20220308202332260.png)

```bash
 git add 后
 git stash #隐藏文件 不提交也不删除
 git stash pop #弹出隐藏文档
 基本上在 git pull 前
```

#### 11、如何搭建个人博客

Github可以直接预览markdown 一般文件后缀为 .md 或者.markdown

代码的输入模式，可以是四个空格 或者四个` 后写语言的名称。

在vscode中安装markdown all in on 拓展，用VScode 编辑.md文件，然后 ctrl+shift+P 上搜索 markdown preview 来实现 文本转换。

![image-20220308230039461](E:\TXT\Blogimge\image-20220308230039461.png)

![image-20220308231234214](E:\TXT\Blogimge\image-20220308231234214.png)

注意：安装VScode yarn插件 ，

```bash
yarn global add git-open
```

可以实现 使用git open 打开远程仓库首页。

![image-20220308232034511](E:\TXT\Blogimge\image-20220308232034511.png)

删除远程仓库的某个文件夹 但是本地仓库不删除

```bash
步骤：（以删除.idea文件夹为例）
git rm -r --cached .idea  #--cached不会把本地的.idea删除
git commit -m 'delete .idea dir'
git push -u origin master
```

