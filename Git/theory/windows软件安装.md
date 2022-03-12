windows软件安装

[TOC]

在cmder 安装过程中设置中文 直接成功后是不是不用更改语言代码

在cmder设置时，外观设置的大小，不能够进行保存？



##### 1、设置windows

**用户目录**

PerfLogs 是系统目录 

Program Files 是软件目录

Program Files（x86）是软件目录

Windows 是系统目录

用户目录中的 用户 maid 是用户可以更改的目录 其他均为系统自带。

一定要打开设置中的 **文件资源管理器**选项，在查看中打开文件的**后缀名**。

✨在查看中勾选**隐藏文件名和驱动器选项**，在电脑中的隐藏文件夹不要动。

**移动目录到D盘 --下载 文档**

在用户目录中，在下载处右键点击属性，选择位置 ，点击移动，在D盘新建文件夹（Downlode 用英文建立）然后点击移动即可。文档（Documents）移动方法和下载移动方法相同。

**修饰键**

Ctrl  shift--控制大小写 按住即为大写 alt--可选 win-windows键 Tab键 ---转  Esc键--退出键  大小写锁定，使用shift 键，✨多进行打字训练。

 **常用的快捷键**

<u>*win组合键*</u>

win+D--展示桌面

Win+方向键---移动窗口

alt+tab---切换窗口 向前移动+shift

Win+tab---不怎么常用的切换窗口 新建左面

Win+ctrl+方向键---切换桌面

<u>ctrl组合键</u>

ctrl+All --全选   ctrl+Copy/ctrl+V--复制黏贴    ctrl+Z/ctrl+Y---返回重做

ctrl+Reload/f5---刷新页面

ctrl+p ---打印

在浏览器页面ctrl+shift+n---打开无痕窗口

✨==注意，打印页面时候，在打印设置页面，选择更多设置，边距选择无，勾选背景图形。==![image-20220303203947441](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303203947441.png)

![image-20220302155036991](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220302155036991.png)

##### 2、浏览器注意事项

1、在页面右键点击查看，可以看到开发者工具窗口。

2、在开发者工具里面任何页面，按ESC可以新建控制台。

3、在sources里面的双箭头，snippets 可以保存 好用的代码 （可以添加新的代码 只支持JS）

3、Network 可以进行勾选，配置想要的数据

![image-20220303202237005](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303202237005.png)

4、Network可以进行网络模拟 。![image-20220303202203138](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303202203138.png)![image-20220303202345864](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303202345864.png)模拟断网，快3G，慢3G

5、在Network中的presevere log （保留日志）中，可以实现刷新页面但是所观测的开发者目录不变。

6、在Network中的Disable cache （停用缓存）

**chrome常用快捷键**

鼠标中键单击--关闭浏览页快捷键，若是链接形式，中键新建另一窗口打开。

 ctrl+w---关闭当前页面

ctrl+T---新建空白页面

ctrl+shift+T--撤销关闭

ctrl+R ---刷新页面 /F5

ctrl+L ---输入网址

ctrl+shift+I---打开开发者工具 /F12

alt+左/右--前进回退

在输入网址后 alt+回车---在新标签打开，shift+回车---在新窗口打开

ctrl+shift+delete---删除离世浏览数据

##### 3、VS code 设置

1、VS code 首先设置中文在拓展里 搜索‘’Chinese‘’进行安装

2、VS设置字体，保存等功能在文件选项中，‘’首选项‘’ 搜索进行修改。

3、VS拓展中 的 code Spell Checker 用来检测输入代码中的，单词错误。

4、Git Easy 增加了*vscode*中自带的*git*操作,安装后按F1调出控制台,输入*git* *easy* [options]完成*git*操作,代替*git* bash。

* 按ctrl+shift +p 搜索 git add  / git commit 可以实现 Vscode 直接运输到暂存区域，不需要使用 cmder。

5、VS code  连字设置

1. 将鼠标悬浮至 Editor: Font Ligatures，看到一个小齿轮图标，点击图标，选择下图所示的选项，点击之后会自动复制一个配置

   ![image.png](https://static.xiedaimala.com/xdml/image/3ac7c224-c23d-491f-84b5-4fabfbeab9b8/2020-1-29-16-26-34.png)image.png

2. 点击在 settings.json 中编辑，在文件中间新增一行空行，然后粘贴（上一步已经自动被配置复制了），记住在这一行末尾加一个英文逗号（如果这一行是最后一行则不能加逗号）

   ![image.png](https://static.xiedaimala.com/xdml/image/3ac7c224-c23d-491f-84b5-4fabfbeab9b8/2020-1-29-16-29-47.png)image.png

3. 如果你的控制台出现了一个奇怪的小图标，

   ![image.png](https://static.xiedaimala.com/xdml/image/5939aa7c-d446-47c4-a9c1-ea1e52b10249/2021-6-9-15-36-42.png)image.png

   虽然不影响使用，但想恢复到和视频中一致，只需删除settings.json中

   ```
   "terminal.integrated.tabs.enabled": true,
   ```

   这一行配置并保存

**VS 功能**

1、在终端选项中，新建终端，开启终端后设置默认cmd，再重新建立终端，点击‘’+‘’开启第二个终端。![image-20220303212637758](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303212637758.png)2、![image-20220303212921655](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303212921655.png)

搜索和替换代码中的关键信息、文件夹。

搜索当前文件--在当前代码里按==ctrl+F==即可搜索当前文件 ctrl +H则为替换

搜索选中区域---先选中代码区域进行搜索，按到文中等的锁定进行搜索 ，替换。![image-20220303213129216](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303213129216.png)

3、设置语法（不要用纯文本）

![image-20220303213240020](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220303213240020.png)

ctrl+N 新建文件，点击设置代码等的对应语法。

4、Emmet快捷写代码

！tab可以直接建立 HTML 文档，ctrl+shift+P 输入emmet wrap 输入所想的代码

eg

```html
<body>
    1
    2
    3
    4
</body>
```

选中 1,2,3,4，按ctrl+shift+p  搜索 emmet wrap 然后输入div*  就可以实现多行的一个代码修饰，这里*的意思就代表多个代码。

```html
<body>
	<div>1</div>
    <div>2</div>
    <div>3</div>
    <div>4</div>
</body>
```

选中 1,2,3,4，按ctrl+shift+p  搜索 emmet wrap 然后输入ul>li* 可以实现如下图所示

```html
<body>
	<ui>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
	</ui>
</body>
```

调试JavaScript/TypeScript 

5、自动换行，输入命令 wrap  就是自动换行。

6、多位置输入、  按住alt，单击选中多行， 可以进行多行输入

**VS code 快捷键**

ctrl+P-- 找文件

ctrl+shift +p--输入命令

alt+单击---多位置输入

ctrl+s --- 保存且自动格式化

##### 4、cmder安装与配置

设置里面可以设置 快捷键

分屏  左右快捷键 alt+D   默认 ctrl +D是 关掉软件分屏 (如果有代码则不能够关闭)

分屏 上下快捷键 alt+shift +D 

新建标签  ctrl +T

关闭标签   ctrl+W （有代码情况下可以实现关闭）

![image-20220304110912850](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304110912850.png)

##### 5、安装node.js

下载nodejs 最新版本，安装过程中注意PATH的设置。

<u>npm有什么用</u>

- 允许用户从NPM服务器下载别人编写的第三方包到本地使用
- 允许用户从NPM服务器下载并安装别人编写的命令行程序到本地使用
- 允许用户将自己编写的包或命令行程序上传到NPM服务器供别人使用

配置nodejs（使用淘宝源 不要用cnpm）

npm i -g nrm

nrm ls

nrm use taobao

![image-20220304131517769](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304131517769.png)

![image-20220304131647816](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304131647816.png)

安装的位置：

![image-20220304131052012](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304131052012.png)



<u>补充：cnpm是什么？</u>

众所周知`npm`（即 node package manager ）是`Node`的包管理工具，能解决NodeJS代码部署上的很多问题，

`cnpm的`官方介绍是：cnpm是一个完整 `npmjs.org` 镜像，你可以用此代替官方版本(只读)，同步频率目前为 **10分钟** 一次以保证尽量与官方服务同步。既然都一样，那么`cnpm`为什么要出现呢？

由于`npmjs.org`的服务器在国外（即在“墙”外），国（墙）内开发者做项目的时候，很多“包”的下载速度极慢，在这种环境下阿里巴巴为了众多开发者的便捷便挺身而出推出了淘宝镜像（即cnpm），它把`npm`官方的“包”全部搬到国内，供广大开发者使用。

##### 6、安装yarm

![image-20220304132329849](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220304132329849.png)

