# HTML

1. 万维网WWW的发明

   **WWW=URL + HTML+HTTP**

2. 互联网的本质是内容共享

3. 万维网和互联网的区别？

   互联网是两个Ip之间的交流，但是缺少输入地址就能看到网页，后来李爵士发明了万维网，可以基于网址就能看到网页

   在Google搜索**mdn HTML5** 可以搜索到权威的资料。

   [TOC]

   

#### HTML历史

1、HTML5 ：最新版本的HTML语言，含旧标签和32个新标签

![image-20220309225517667](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220309225517667.png)

2、H5 是手机页面不是HTML5 。

3、HTML开发工具：VScode ==WebStorm== Chrome MDN文档

​    语法：注释，DOCTYPE ，有内容标签，无内容标签，属性

   标签：元数据，章节，内容层次，文字，嵌入内容，表格，表单，可交互元素。

#### HTML 语法

DOCTYPE就是文档类型 ，属性的值与命令行一，用<!--注释-->

```html
<!DOCTYPE html>
<tag attr=value>内容</tag>
<tag attr>内容</tag>
<tag attr=value>   <!--大概有这几种类型的标签-->
<!--需要注意 大小写与引号是没有区别的，和组合的区别-->
```

```
1.<tag attr=value>内容</tag>
```

属性值

id=xxx

参数加 单/双引号和 无引号都是对的。

属性值加引号的规则与命令行一致。有特殊字符就加，没有就不加。

```
2.<tag attr>内容</tag>
```

没有等于号，没有值的属性，布尔属性(只有真和假)。

例子:<input type="checkbox" checked="false"> //运行结果为被勾选状态☑️. 新版语法不支持，只要写了checked那不管是true还是false结果都是checked。

不过要注意不是所有的语法都这样。

```
3.<tag attr=value>
```

语法：直接闭合

例子：<link href="xxx.css">

由于html有超强纠错功能有/会自动纠错,最新版规范写法是不加/

如何查看是否自己写错代码？

* 看VScode的颜色

* 看WebStorm的颜色（使用WebStorm的条件 容忍开项目需要十秒以上，内存4G，SSD固态硬盘）

* 使用HTML5验证器（在线/npm）[https://validator.w3.org](https://validator.w3.org/) （没法用 不知道为什么）

  ![image-20220310135643304](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220310135643304.png)

  选择“Validate by Dtrect Input”,粘贴代码点击按钮“Check”

* 在终端安装 w3c-validator npm  

  然后在终端输入node-w3c-validator -i "HTML文件名字" 命令 来检查HTML代码的错误。

```bash
 yarn global add node-w3c-validator
 node-w3c-validator --version 
 代码：node-w3c-validator -i index.html 
```

#### 查资料

在goolg搜索 mbn ruby 

![image-20220310142129323](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220310142129323.png)

![image-20220310142349894](C:\Users\Maid\AppData\Roaming\Typora\typora-user-images\image-20220310142349894.png)

复制js.jirengu.com 上看代码结果。

