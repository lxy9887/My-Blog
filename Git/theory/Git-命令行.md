[TOC]

##### 1、设置终端 bash 类型

文档里有写如何设置终端 

用 touch test.txt 创建测试。

##### 2、终端里如何实现复制粘贴

<u>命令行如何实现复制黏贴?</u>

在 Windows 的 cmder 里

1. 用鼠标选中文字即自动复制
2. 单击鼠标右键就是粘贴
3. Shift + Insert 也是粘贴

在 Windows 的 Git Bash 里

1. 用鼠标选中文字，然后右键 copy 就是复制
2. 用鼠标选中文字，然后按 ctrl + insert 也是复制
3. 点击鼠标中键就是粘贴
4. Shift + Insert 也是粘贴

##### 3、英语小课堂 -iciba.com

元音：a e i o u

常用单词

file  文件         		         link 链接                ln

make 制作  mk     		 find 找到                     find

move 动 	mv			    echo 回声                  echo

remove 删除	rm		 touch 触摸                     touch

copy拷贝 	cp		       change 改变                      cd 中的c

list 列表 	ls				    directory 目录/文件夹     cd中的d

recursive  递归的（） 	force 强制

##### 4、增删改查

* ==查：查看文件和目录==

* ![image-20220304193515225](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304193515225.png)

  cd ~/Desttop/    如果想进入某个盘 可以输入 cd D:\  

  cd /c/Users/Maid/.ssh  进入某个盘的某个目录里的某个目录

  查看当前目录绝对路径   

  **pwd**

  ```bash
  cd ~/Desktop/ # ✨用户目录的缩写是~ 所以 这个代码的意思为打开用户目录中的桌面
  pwd  #查看详细路径
  ```

  注意：绝对路径和相对路径的区别？

  **绝对路径**就是文件的真正存在的路径，是指从硬盘的根目录(盘符)开始，进行一级级目录指向文件。

  eg：/d/Software/cmder

  **相对路径**就是以当前文件为基准进行一级级目录指向被引用的资源文件。

  ​         ../             表示当前文件所在的目录的上一级目录

  ​         ./               表示当前文件所在的目录(可以省略)

  ​         /                表示当前站点的根目录(域名映射的硬盘目录)

  ![image-20220306152202554](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220306152202554.png)

  查看当前目录内容

  **ls**

  ```bash
  ls #查看文件夹里的内容（不显示以.开头）
  ls -a #就是查看整个目录里的内容 （可以查看到隐藏目录并进行删除）
  ```

  查看制定目录内容

  **ls 路径** (  ls 默认不显示已以.开头的文件  ) 

  ```bash
  ls a #只查看a文件夹里面的内容
  ```

  查看文件内容 （多指的是代码文件）

  **cat 路径**      查看全部文件内容

  **head 路径**  只显示前十行    head style.css  -n 15   可以通过增加 -n来查看几行 **tail 路径**     只显示后十行      

  **less 路径**   表示可以滚动查看 按上下 / j k 滚动查看  

  ✨**按Q键退出查看** 

* ==增：创建文件==

  创建1.txt  

  ```bash
  touch 1.txt  #可以创建空文件
  echo hi
  echo hi > 4.txt #可以创建带有字的文件
  echo hello > 4.txt # 是对文件里的文字进行替代
  echo hehe >> 4.txt # 双大于号表示追加内容
  echo -e "haha\n3333" >> 4.txt #代表在文件里增加两行 \n 为回车 如果直接打回车也可行
  echo -n "123"  #不换行输出
  ```
  
  对echo的[参数](https://so.csdn.net/so/search?q=参数&spm=1001.2101.3001.7020)使用查阅了下：
  -n do not output the trailing newline
  -e enable interpretation of backslash escapes
  -E disable interpretation of backslash escapes (default)
  
  **echo -e 处理特殊字符**
  
  若[字符串](https://so.csdn.net/so/search?q=字符串&spm=1001.2101.3001.7020)中出现以下字符，则特别加以处理，而不会将它当成一般文字输出：
  \a 发出警告声；
  \b 删除前一个字符；
  \c 最后不加上换行符号；
  \f 换行但[光标](https://so.csdn.net/so/search?q=光标&spm=1001.2101.3001.7020)仍旧停留在原来的位置；
  \n 换行且光标移至行首；
  \r 光标移至行首，但不换行；
  \t 插入tab；
  \v 与\f相同；
  \ 插入\字符；
  \nnn 插入nnn（八进制）所代表的ASCII字符；
  
  **echo -e 设置字体颜色**
  格式: echo -e "\033[字背景颜色;字体颜色m字符串\033[0m"
  
  例如:
  
  ```
  echo -e "\033[41;36m something here \033[0m" 
  ```
  
  其中41的位置代表底色, 36的位置是代表字的颜色
  
  那些ascii code 是对颜色调用的始末.
  
  ```
  \033[ ; m …… \033[0m 
  ```
  
  附1：字背景颜色范围:
  30:黑
  31:红
  32:绿
  33:黄
  34:蓝色
  35:紫色
  36:深绿
  37:白色
  40:黑
  41:深红
  42:绿
  43:黄色
  44:蓝色
  45:紫色
  46:深绿
  47:白色
  
  附2：ANSI控制码的说明:
  \33[0m 关闭所有属性
  \33[1m 设置高亮度
  \33[4m 下划线
  \33[5m 闪烁
  \33[7m 反显
  \33[8m 消隐
  \33[30m – \33[37m 设置前景色
  \33[40m – \33[47m 设置背景色
  \33[nA 光标上移n行
  \33[nB 光标下移n行
  \33[nC 光标右移n行
  \33[nD 光标左移n行
  \33[y;xH设置光标位置
  \33[2J 清屏
  \33[K 清除从光标到行尾的内容
  \33[s 保存光标位置
  \33[u 恢复光标位置
  \33[?25l 隐藏光标
  \33[?25h 显示光标
  
  创建目录a/（创建文件夹）
  
  ```bash
  mkdir a
  ```
  
  创建多层目录a/b/c/d/e
  
  ```bash
  mkdir a
  cd a
  mkdir b
  cd b
  mkdir c
  cd c  #多次创建文件夹并且进入文件夹再次创建
  ***********************
  mkdir -p  a/b/c/d # 快速创建深层目录
  ```
  
  同时创建多个文件
  
  ```bash 
  touch 1.txt 2.txt 3.txt
  ```
  
  同时创建多个目录

```bash
mkdir a b c 
mkdir -p a/b/c  a/b/d
```

复制文件

```bash
cp 1.txt 2.txt #从文件1复制到文件2
```

复制目录

```bash
cp -r a b #对目录进行复制
```

* 删：删除

  删除文件

  ```bash
  rm 1.txt  #删除文件
  ```

  删除目录

  ```bash 
  rm -r a #对目录a进行删除 
  rm -rf a #强制删除目录a
  ```

* 改：修改文件或目录

  清空文件

  ```bash
  echo '' > 1.txt
  code 1.txt 全选删除
  ```

  修改文件内容

  ```bash
  code 1.txt #直接用命令打开文件进行修改
  start 1.txt # 用默认程序打开 ，这里就是指文件已经设置好默认编码程序
  ```

  追加文件内容

  ```bash
  echo hehe >> 4.txt # 双大于号表示追加内容
  ```
  
  移动文件/目录
  
  ```bash
  mv 1.txt   a   #把文件1.txt放入a文件夹
  mv a/1.txt .   #把文件夹a中的文件1.txt移除
  ```
  
  重命名文件/目录
  
  ```bash
  mv 1.txt 2.txt #把文件1.txt复制到2.txt  就是相当于重命名
  ```
  
  修改文件最后更新时间

  ```bash
  cd a  #进入文件夹
  ls #显示文件名称信息
  ls -l 或者 ll #显示文件时间信息
  touch 1.txt  # 触摸更改时间
  ```
  
  查看命令手册
  
  ```bash
  ls --help #查询命令    linux 可以 用 man ls
  # 如果命令太长了  用以下形式
  ls --help | less
  ***************
  npm i -g tldr 或 yarn global add tldr  #安装tldr
  查询方法：
  tldr ls   需要在前面加上tldr
  ```

##### 5、多命令组合

如果执行命令的时候，成功不显示结果，失败返回非0，查询反馈用 

```bash
echo $?  
```

用echo 来查询返回值 error 返回非0 （不一定非要是1）成功返回0

如果想让命令成功后给予反馈，则需要对rm 进行特定的指令，这时用**&&**连接。==可以多次叠加，但是如果第一次失败则后面的命令不会执行==

```bash
touch 1.txt && echo 成功 #这里成功不加双引号 加了就执行不了命令
rm 1.txt && echo 删除成功 
touch 1.txt && rm 1.txt && touch 2.txt && echo 成功 #按顺序执行 
```

==若直接全部执行，不管前面命令是否成功，都执行另一条，用**；**连接==

```bash
rm 1.txt ；echo 执行完毕 #失败了也会执行echo
```

![image-20220306103610644](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220306103610644.png)

##### 6、bash脚本文件

* 把命令变成文件 

  ✨Alt+. 可以返回上一次最后的参数直接复制下来

  1、创建一个文件，后缀不限

  2、把要执行的命令书写到文件里

  3、添加执行权限  chmod +x  文件

  [chmod](https://so.csdn.net/so/search?q=chmod&spm=1001.2101.3001.7020)：改变权限

  u：文件所有用户

  +x: 增加可执行权限

  运行 .sh 文件类型的文件：
  用file命令测试一下看是什么类型的
  file xxxx.sh
  如果是Bourne-Again shell script 

  可以sh xxxx.sh 或者chmod +x xxxx.sh 再 ./xxx.sh
  一般 .sh 的直接添加x(可执行属性) chmod +x xxx.sh 然后./xxx.sh就可以了
  chmod是一个改变用户拥有指定文件的权限的命令.r:只读,w:写,x执行.也可以用数字

```bash
touch script # 脚本
code script /start script
```

```bash
#输入命令 
mkdir x
cd x
touch index.html
touch style.css
touch main.js
echo -e "<!DOCTYPE html>\n<h1>标题</h1>" >> index.html
```

```bash
chmod +x script #加入可执行权限 MAC系统必须直接添加而windows系统非必要添加
```

```bash
./script # 运行当前目录下的 script ✨注意这里不能够有空格✨
sh script #sh 和./ 同理
~/Desktop/script xxx #如果想在其他目录里运行所写脚本就要书写绝对路径 
```

上述命令只能创建 x目录 如果想创建不同文件名的目录 就要设置参数。

```bash
mkdir $1 
cd $1
touch index.html
touch style.css
touch main.js
echo -e "<!DOCTYPE html>\n<h1>标题</h1>" >> index.html
```

这样就可以建立想要目录名的目录。

4、运行【sh正确的路径】即可执行

.sh文件 

linux中.sh文件是脚本文件，一般都是bash脚本。

脚本文件英文为Script。实际上脚本就是程序，一般都是由应用程序提供的编程语言。应用程序包括浏览器(javaScript、VBScript)、多媒体创作工具，应用程序的宏和创作系统的批处理语言也可以归入脚本之类。

脚本文件类似于DOS操作系统中的批处理文件，它可以将不同的命令组合起来，并按确定的顺序自动连续地执行。脚本文件是文本文件，用户可使用文本编辑器来创建脚本文件。

5、如果在脚本文件中加了shebang，删掉sh也能执行

```bash
#!/usr/bin/env sh  #是一种注释就是可以允许其他程序运行脚本
mkdir $1 
cd $1
touch index.html
touch style.css
touch main.js
echo -e "<!DOCTYPE html>\n<h1>标题</h1>" >> index.html
```

6、但是你必须用正常的路径

7、==如果你把脚本的目录的路径加进环境变量的PATH ，就可以直接运行脚本文件。==而且不限制目录。 可以只用脚本文件名就能执行。

==如果有相同的脚本文件名，改变环境变量的顺序可以实现优先使用。==

注意：windows系统里优先执行 .exe 文件 MAC系统里没有区分

```bash
script xxx
```

命令行的本质就是可以执行的文件。

####  7、补绝对路径和相对路径的区别

![image-20220306213954212](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220306213954212.png)

基本概念
　　文件路径就是文件在电脑中的位置，表示文件路径的方式有两种，相对路径和绝对路径。在网页设计中通过路径可以表示链接，插入图像、Flash、CSS文件的位置。
　物理路径：物理路径就是硬盘上文件的路径，比如下面的文件：

```
d:\dreamdu\exe\1.html
d:\dreamdu\exe\first\2.html
d:\dreamdu\exe\first\3.html
d:\dreamdu\exe\first\second\4.html
```

下面的例子使用了上面四个文件进行了相互链接

**相对路径(Relative Path)**
　　相对路径就是相对于当前文件的路径。网页中一般表示路径使用这个方法。如何表示同级目录的文件？
　　2.html和3.html在同一个文件夹下， 如果2.html链接到3.html，可以在2.html中这样写:

```html
<a href="3.html">同目录下文件间互相链接</a>
```

如何表示上级目录的文件？
　　1.html是2.html和3.html的上级目录中的文件，如果2.html或3.html链接到1.html，可以在2.html或3.html中这样写

```html
<a href="../1.html">链接到上级目录中的文件</a>
```

../ 代表一级上级目录(间隔一个目录)
 ../../代表二级上级目录(间隔两个目录)
比如4.html链接到1.html，可以在4.html中这样写

```html
<a href="../../1.html">链接到上级目录的上级目录中的文件</a>
```

如何表示下级目录的文件？
　　2.html和3.html是1.html的下级目录中的文件，如果在1.html中链接到2.html， 可以在1.html中这样写

```html
<a href="first/2.html">链接到下级目录(first)中的文件</a>
```

如果在1.html中链接到4.html，可以在1.html中这样写

```html
<a href="first/second/4.html">链接到下级目录(first/second/)中的文件</a>
```

**绝对路径(Absolute Path)**
　　绝对路径又分为本地绝对路径和网络绝对路径。

本地路径是指文件在硬盘上真正存在的路径。

网络路径就是带有网址的路径，比如你有一个域名www.dreamdu.com，和一个网站空间，上面的四个文件就可以这么表示。

```html
<a href="http://www.dreamdu.com/exe/1.html">链接到1.html</a>
<a href="http://www.dreamdu.com/exe/first/2.html">链接到2.html</a>
<a href="http://www.dreamdu.com/exe/first/3.html">链接到3.html</a>
<a href="http://www.dreamdu.com/exe/first/second/4.html">链接到4.html</a>
```

使用绝对路径的缺点
　　使用根目录和绝对路径的好处是表示路径比较简单，都是从网站的最开始目录里查找，一级一级的向下查。缺点是程序不容易移植(比如把网站做为另一个网站的一个栏目，移动到一个新的文件夹中就不行了)。

**根目录**
　　使用根目录的方式表示的路径和绝对路径的表示方式相似，去掉前面的域名就可。
　　比如：

```html
<a href="/exe/1.html">链接到1.html</a>
<a href="/exe/first/2.html">链接到2.html</a>
```



