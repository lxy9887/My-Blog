[TOC]



#### 英语小课堂

| hyper     | 超级      | blank  | 空白 |
| --------- | --------- | ------ | ---- |
| target    | 目标      | parent | 父母 |
| reference | 引用      | self   | 自己 |
| frame     | 边框 框架 | load   | 加载 |
| error     | 错误      | canvas | 画布 |

#### 一、a标签

作用：

跳转外部页面

跳转内部锚点

跳转到邮箱或电话等

**href（超级引用）：超级链接**

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <a href="https://google.com">超链接</a>
</body>
</html>
```

> 小tip

==不要双击打开html==  打开方式如下：

✨方法一：

* 在vscode终端安装 yarn global add http-server

* 通过输入 http-server

* 出现链接 按ctrl+单击 

* 跳转后 在网址输入要跳转的 html文件名

  ![image-20220312190111064](E:\TXT\Blogimge\image-20220312190111064.png)

方法二：

* 在vscode终端安装 yarn global add parcel

* 直接在终端 parcel xxx.html

* 产生一个链接 按ctrl+单击 就是在浏览器中打开html

  ![image-20220312190648357](E:\TXT\Blogimge\image-20220312190648357.png)

**a标签href的取值**

1. 网址：（外部链接）

```html
<a href="https://google.com">超链接1</a>
<a href="http://google.com">超链接2</a>
<a href="//google.com">超链接3</a>
```

https和http 以及都去掉的区别 http协议

https比http多一个s的含义是指的是Secure （安全），如果是http开头的网站，会有不安全的显示，如果是https开头的网站代表已经建立了安全连线，若需要输入个人资料信息，将会以加密的形式进行传输。

//google.com 是最高级网址 可以自动选择是哪个网址。

2. 路径 （内部链接）

```html
 到不同目录的一个文件
<a href="/a/b/c.html">c.html</a>
<a href="a/b/c.html">c.html</a><!--这里有无/是相同含义-->
链接到同一目录的文件
<a href="index.html">index.html</a>
<a href="./index.html">index.html</a><!--这里有无./都是相同含义-->
```

**注意：**这里/a/b/c 的/ 不是根目录，而是相对于a.html，之前所有的路径都是基于文件的，而http协议里面的路径 就不再是文件说法了，在这个浏览器的网址里其实是隐藏着http的。

![image-20220312220200209](E:\TXT\Blogimge\image-20220312220200209.png)

这里其实是http://10.120.242.163:8080/a/b/c.html

并且如果我们开启了http服务，他的根目录就不是硬盘的根目录，而是在哪里开启了http服务 哪里就是根目录，所以说a-href.html的根目录是 HTML-demo-02. 这也就解释了前面html文件为什么不能用双击打开，如果用双击打开，就相当于没有启动http服务，他的根目录就还是硬盘，就是以文件形式展示。

3. 伪协议

```html
<a href="javascript:alert(1);">javascript伪协议</a> 用来执行JavaScript命令 这里:; 不可以省略
<a href="javascript:;">javascript伪协议</a> 
若将:;中代码去掉，则这个标签没有意义
```

这里解释一下，为什么设置没有意义的Javascript标签？

如果我们直接不写，而是直接一个a标签，就会导致页面刷新，那么之前在页面上输入的东西将会消失，

```html
<a href=""> javascript伪协议 </a>
```

而如果在a便签里面写一个# 则不会进行刷新 而是会自动滚动到顶部。

```html
<a href="#"> javascript伪协议 </a>
```

****************************************************************************************************************************************************

```html
锚点链接 "#XXX"
<p id=xxx>查看我</p>
<a href="#xxx"> 查看xxx </a> 查看xxx所在的行
```

```html
<a href="mailto:liuxinyuucc@163.com"> 发邮件给欣宇 </a> 
```

```html
<a href="tel:18518103788"> 打电话给欣宇 </a> 
```

**target：指定在哪个窗口打开超链接**

**a标签target的取值**

1. 内置名字（_blank _self _top _parent,窗口名字，iframe名字）

   ```html
   ✨<a href="https://google.com" target="_blank">google</a>空白页打开超链接
   ✨<a href="https://google.com" target="_self">google</a>在当前页面打开
   ```

   ```html
   ✨<a href="https://google.com" target="_top">google</a>两个窗口时在最顶层打开页面
   这里需要与iframe连用，iframe是通过在页面引入另一个页面。
   <iframe src="a-traget-iframe.html" frameborder="0"></iframe>
   ```

   > 为了明显一点，我们将a-traget-iframe文件设置鲜艳一些。

   ```html
   <body style="background: red;">
       我是iframe
       里面有一个a标签
       <a href="//google.com" target="_top">链接</a>
   </body>
   ```

   ![image-20220313131301239](E:\TXT\Blogimge\image-20220313131301239.png)

这样就是层级关系，外面包裹着红色里面。点击里面链接会变成白色窗口打开，因为最顶层的是白色窗口。（top意味着最顶层打开）

但是如果把_top 改成 _self 则其实就是应该在红色区域打开链接。

```html
✨<a href="//google.com" target="_parent">parent</a>是在副级窗口打开
```

> 为了区别于top，这里再次引入iframe

新建文件 是的a的target为_parent .

```html
<body style="background: rgb(21, 255, 0);">
    我是iframe2
    <hr/>
    里面有一个a标签
    <a href="//google.com" target="_parent">parent</a>
</body>
```

我们在原来a-traget-iframe的基础上 再次iframe引入刚建文件 并且显示绿色

```html
<iframe src="a-traget-iframe-2.html" ></iframe>
```

所以如果我们点开链接 实际上是在红色窗口打开，因为是副级窗口

![image-20220313132929273](E:\TXT\Blogimge\image-20220313132929273.png)

```html
✨<a href="https://google.com" target="xxx">google</a>
    <a href="https://baidu.com" target="xxx">baidu</a>
如果有一个叫xxx的窗口，那么就在xxx里打开，如果没有xxx窗口就创建一个xxx窗口打开。
```

那么这就以为这如果你两个链接的target都是xxx，则在同一个窗口打开。

（可以重复利用同一窗口打开）

>注意：如何查看这个窗口的名字？
>
>在控制台，输入 window.name  就是这个窗口的名字

```html
✨<body>可以设置iframe的名字，这样就可以实现嵌入式的跳转
    <a href="https://google.com" target="xxx">google</a>
    <a href="https://baidu.com" target="yyy">baidu</a>
    <hr>
    <iframe src="" name="xxx"></iframe>
    <hr>
    <iframe src="" name="yyy"></iframe>
</body> 
src 是source 的简写 一般接地址（网络地址，相对路径，绝对路径均可）
```



![image-20220313160503020](E:\TXT\Blogimge\image-20220313160503020.png)

**download 是只下载文件**

**rel=noopener** 

#### 二、iframe 标签

iframe标签用来内嵌窗口

```html
<iframe id="inlineFrameExample"
    title="Inline Frame Example"
    width="300"
    height="200"
    src="https://www.openstreetmap.org/export/embed.html?bbox=-0.004017949104309083%2C51.47612752641776%2C0.00030577182769775396%2C51.478569861898606&layer=mapnik">
</iframe>
<!--代码来自mdn-->
```

#### 三、table标签

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table>
        <thead>
            <tr>
            <th>英语</th> 
            <th>翻译</th> <!--表头的一个单元格-->
            </tr> <!--table row 表格中一行-->
        </thead>
        <tbody>
            <tr>
            <td>hyper</td>
            <td>超级</td> <!--table data 表格数据 一个单元格-->
            </tr>
            <tr>
            <td>target</td>
            <td>目标</td> 
            </tr>
            <tr>
            <td>reference</td>
            <td>引用</td> 
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <td>空</td>
                <td>空</td> 
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

![image-20220313210123905](E:\TXT\Blogimge\image-20220313210123905.png)

有两个表头的情况下：

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <table>
        <thead>
            <tr>
            <th></th>
            <th>小红</th>
            <th>小明</th>
            <th>小颖</th>
            </tr> <!--table row 表格中一行-->
        </thead>
        <tbody>
            <tr>
            <th>数学</th>
            <td>61</td>
            <td>91</td> 
            <td>85</td> <!--table data 表格数据-->
            </tr>
            <tr>
            <th>语文</th>
            <td>79</td>
            <td>82</td> 
            <td>92</td> 
            </tr>
            <tr>
            <th>英语</th>
            <td>100</td>
            <td>97</td> 
            <td>87</td>
            </tr>
        </tbody>
        <tfoot>
            <tr>
                <th>总分</th>
                <td>200</td>
                <td>200</td> 
                <td>200</td> 
            </tr>
        </tfoot>
    </table>
</body>
</html>
```

![image-20220313210902393](E:\TXT\Blogimge\image-20220313210902393.png)

> 注意：

1、当我们在写代码时候不写，<tbody> 而直接写<tr> / <td>时，会直接变成<tbody>/<tr>里面的内容。

2、<thead><tbody><tfoot> 三者标签顺序无关，一定是按照头 中 脚来排列的。

**表格相关样式：**

* table-layout:

```html
<style>
    table{table-layout: auto; }
</style>        
大多数浏览器采用自动表格布局算法对表格布局，自动计算每一列和每一横排的宽和高，宽度取决于其包含等的内容。
```

```html
<style>
    table{table-layout: fixed; }
</style>  
表格狠人列的宽度通过表格的宽度来设置，某一列的宽度仅由该列首行的单元格决定，在当前列中，该单元格所在行之后的行并不会影响整个列宽。尽量进行平均分布。
```

​      inherit

​      initial

​      unset

* border-spacing

```html
<style>
        table{
            width: 600px; <!--宽度-->
            table-layout: auto;
            border-spacing: 10px;  <!---->
        }
        th,td{
            border: 1px solid blue;
        
        }
</style>
是指相邻单元格边框之间的距离
```

* border-collapse

```html
<style>
        table{
            width: 600px;
            table-layout: auto;
            border-collapse: collapse; 
            border-spacing: 0;

        }
        th,td{
            border: 1px solid blue;
        }
</style>
是指合并相邻单元格边框，通常情况下与border-spacing:0; 连用
```

#### 四、img标签

作用：发出get请求，展示一张图片

属性：

src：图片的链接，（可以是绝对路径，也可以是相对路径，或者网址）

alt：可选的，替换的 如果图片加载失败，所显示的东西

height/width：图片的高和宽，这里单位只支持像素，如果你只设置宽度，高度会自适应。

```html
<body>
    <img width=400 height=600 src="dog.png" alt="一只狗狗">
</body>
```

事件

onload/onerror  用来监督图片是否加载成功 成功则为onload 不成功为onerror，可以在图片失败的时候进行挽救。

```html
<body>
    <img id="xxx" width=400 src="dog.png" alt="一只狗狗">
<script>
    xxx.onload = function(){
        console.log('图片加载成功')
    }
    xxx.onerror= function(){
        console.log('图片加载失败')
    }
</script>
</body>
```

在控制台可以查看这一信息，在网页中不会显示出来。

![image-20220314215346281](E:\TXT\Blogimge\image-20220314215346281.png)

如何挽救？

找一张备用图，在提示加载失败后面添加src属性

```html
<body>
    <img id="xxx" width=400 src="dog.png" alt="一只狗狗">
<script>
    xxx.onload = function(){
        console.log('图片加载成功')
    }
    xxx.onerror= function(){
        console.log('图片加载失败')
    xxx.src = "/404.png"
    }
</script>
</body>  <!--这样如果成功显示则会出来，图片加载成功，如果失败则会显示图片加载失败，并且显示备用图-->
```

响应式：设置图片宽度可以满足手机要求

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        *{
            margin:0 padding:0 box-sizing: border-box
        }
        img{

            max-width: 100%;  ✨<!--就是设置宽度一直符合页面宽度-->
        }
    </style>
</head>
<body>
    <img id="xxx"  src="dog.png" alt="一只狗狗">
<script>
    xxx.onload = function(){
        console.log('图片加载成功')
    }
    xxx.onerror= function(){
        console.log('图片加载失败')
    xxx.src = "/404.png"
    }
</script>
</body>
</html>
```

#### 五、form标签

表示文档中的一个区域，此区域包含交互控件，用于向 Web 服务器提交信息。==必须有一个type="submit"这个按钮== 

![image-20220314221515512](E:\TXT\Blogimge\image-20220314221515512.png)

表单标签作用：发一个get/post请求，刷新页面。

属性：

action：用于向web服务器提交表单。

```html
<body>
    <form action="/xxx"> <!--向这个地址提交表单，就会请求到哪个页面-->
        ****************************************
         <form action="/xxx" method="POST"> <!--就会以post的形式提交表单-->
        <input type="text"> <!--输入txt 这个类型-->
        <input type="submit"><!--设置一个提交按钮-->
</body>
```

autocomplete：是否自动填充

用于指示 input 元素是否能够拥有一个默认值，此默认值是由浏览器自动补全的。此设定可以被属于此表单的子元素的 `autocomplete` 属性覆盖。 可能的值有：

- `off`：浏览器可能不会自动补全条目（在疑似登录表单中，浏览器倾向于忽略该值，而提供密码自动填充功能，参见 [自动填充属性和登录](https://developer.mozilla.org/zh-CN/docs/Web/Security/Securing_your_site/Turning_off_form_autocompletion#禁用自动填充)）
- `on`：浏览器可自动补全条目

```html
 <body>
    <form action="/xxx" method="POST" autocomplete="on">
        <input name=username <!--推荐建议用户名-->
        type="text">
        <input type="submit">
</body> 
     打开自动填充，用户名或者密码
```

method：浏览器使用这种 [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) 方式来提交 表单。

target：表示在提交表单之后，在哪里显示响应信息。在 HTML 4 中，这是一个 frame 的名字/关键字对。在 HTML5 里，这是一个*浏览上下文* 的名字/关键字（如标签页、窗口或 iframe）。下述关键字有特别含义：

- `_self`：默认值。在相同浏览上下文中加载。

- `_blank`：在新的未命名的浏览上下文中加载。

- `_parent`：在当前上下文的父级浏览上下文中加载，如果没有父级，则与 _self 表现一致。

- `_top`：在最顶级的浏览上下文中（即当前上下文的一个没有父级的祖先浏览上下文），如果没有父级，则与 _self 表现一致。

  ```html
  <body>
      <form action="/xxx" method="POST" autocomplete="on" target="a"> <!--在a里打开-->
          <input name=username
          type="text">
          <input type="submit"> <!--如果使用submit 但是在网页里显示提交，是因为网页可以自动识别你能看懂的文字，如果是英语，则直接显示submit-->
      </form>
      <iframe name ="a" src="a-traget-iframe.html"> </iframe>   
      <!--a 是一个在此页面上的另外一个页面 iframe是插入另一个页面窗口的意思-->
  </body>
  ```

可以对`<input type="submit">`进行更改，`<input type="submit" value="发送">`在后面加入一个 value，就可以实现对其显示的更改。

或者加入一个`<button>` 也可以实现，二者选其一。

🤡`<input type="submit">`与`<button type="submit"></button>`区别：input里面不可以再加入其他内容，但是button 可以加入其他内容，button里面可以含有样式标签，比如`<strong>`   可以使得字体加粗

==`button`里面如果不写 `type=submit`则就会默认是submit==

事件：

onsubmit：当用户点提交的时候就会触发这个事件

#### 六、input标签 是自闭合标签

用于为基于 Web 的表单创建交互式控件，以便接受来自用户的数据; 可以使用各种类型的输入数据和控件小部件

属性：

**类型 type**

txt：`<input type="txt"/>`可输入文本类型

color：`<input type="color"/>`可以选择颜色

password：`<input type="password"/>` 可以输入密码，不展示具体内容 ，保护密码

radio：多选 单选

```html
<input type="radio"/>男 <input type="radio"/> 女 
注意：如果单纯这样设置会导致，都可以进行选择，而不是单选。
让这两个radio拥有同一个name，可以实现二选一
<input name=gender type="radio"/>男 <input name=gender type="radio"/>女
```

![image-20220314225203184](E:\TXT\Blogimge\image-20220314225203184.png)

checkbox：可以实现多选

```html
<input type="checkbox"/>唱 
<input type="checkbox"/>跳 
<input type="checkbox"/>rap 
<input type="checkbox"/>表演 
如何让这几个选项是一组的，就是一类的，在input加上name属性 就可以实现
*************************************************************
实现默认样式：加入checked="checked"
<input type= "checkbox" name="love" checked="checked">
```

![image-20220314230453602](E:\TXT\Blogimge\image-20220314230453602.png)

file：上传文件

```html
<input type="file"/> 只能上传一个文件
<input type="file" multiple/> 可以上传多个文件
```

hidden：看不见的input，常用做机器输入，给js自动填入字符串和id信息

`<input type="hidden"/>`

submit：制作提交按钮

```html
<input type="submit" value="提交">
```

>补充：来自mdn

| Type                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [button](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/button) | 没有默认行为的按钮，上面显示 [value](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#value) 属性的值，默认为空。 |
| [checkbox](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/checkbox) | 复选框，可设为选中或未选中。                                 |
| [color](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/color) | 用于指定颜色的控件；在支持的浏览器中，激活时会打开取色器。   |
| [date](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/date) | 输入日期的控件（年、月、日，不包括时间）。在支持的浏览器激活时打开日期选择器或年月日的数字滚轮。 |
| [datetime-local](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/datetime-local) | 输入日期和时间的控件，不包括时区。在支持的浏览器激活时打开日期选择器或年月日的数字滚轮。 |
| [email](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/email) | 编辑邮箱地址的区域。类似 `text` 输入，但在支持的浏览器和带有动态键盘的设备上会有确认参数和相应的键盘。 |
| [file](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/file) | 让用户选择文件的控件。使用[accept](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#accept)属性规定控件能选择的文件类型。 |
| [hidden](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/hidden) | 不显示的控件，其值仍会提交到服务器。举个例子，右边就是一个隐形的控件。 |
| [image](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/image) | 带图像的 `submit` 按钮。显示的图像由 `src` 属性规定。如果 [src](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#src) 缺失，[alt](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#alt) 属性就会显示。 |
| [month](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input/month) | 输入年和月的控件，没有时区。                                 |
| [number](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/number) | 用于输入数字的控件。如果支持的话，会显示滚动按钮并提供缺省验证（即只能输入数字）。拥有动态键盘的设备上会显示数字键盘。 |
| [password](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/password) | 单行的文本区域，其值会被遮盖。如果站点不安全，会警告用户。   |
| [radio](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/radio) | 单选按钮，允许在多个拥有相同 [name](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#name) 值的选项中选中其中一个。 |
| [range](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input/range) | 此控件用于输入不需要精确的数字。控件是一个范围组件，默认值为正中间的值。同时使用[htmlattrdefmin](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#htmlattrdefmin)  和 [htmlattrdefmax](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#htmlattrdefmax)来规定值的范围。 |
| [reset](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/reset) | 此按钮将表单的所有内容重置为默认值。不推荐。                 |
| [search](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/search) | 用于搜索字符串的单行文字区域。输入文本中的换行会被自动去除。在支持的浏览器中可能有一个删除按钮，用于清除整个区域。拥有动态键盘的设备上的回车图标会变成搜索图标。 |
| [submit](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/submit) | 用于提交表单的按钮。                                         |
| [tel](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/tel) | 用于输入电话号码的控件。拥有动态键盘的设备上会显示电话数字键盘。 |
| [text](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/text) | 默认值。单行的文本区域，输入中的换行会被自动去除。           |
| [time](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/time) | 用于输入时间的控件，不包括时区。                             |
| [url](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/url) | 用于输入 URL 的控件。类似 `text` 输入，但有验证参数，在支持动态键盘的设备上有相应的键盘。 |
| [week](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/week) | 用于输入以年和周数组成的日期，不带时区。                     |
| 废弃的值                                                     |                                                              |
| [datetime](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/datetime) | 用于输入基于 UTC 时区的日期和时间（时、分、秒及秒的小数部分）。 |

事件：

onchange：当用户输入改变的时候，会触发事件

onfocus：当把鼠标集中到这个选项的时候，就会触发事件

onblur：当用户鼠标从选项中出来的时候，就会触发事件

验证器：

**required:**就是要求客户必须填写此表单，否则无法提交。

`<input type="text" required/>` 意味着客户必须填写text 才能提交。

**value:** 加入value属性 可以让表格里面有默认文字

```html
<input typpe="text" value="请在这里书写"> 
```



#### 七、其他标签

textarea：用户输入内容的字数不限

用户可输入内容 style 是css 可以对textarea进行修饰

```html
<textarea style="resize: none; width: 52%; height: 300px;"></textarea> 这里的resize：none 就是指不可以对输入框进行拖动。
```

select：就是可以一框进行下拉选择

```html
<select>
        <option value="">-请选择-</option>
        <option value="1">星期一</option>
        <option value="2">星期二</option>
</select>
```

![image-20220314233049412](E:\TXT\Blogimge\image-20220314233049412.png)

在<option>中定义selected="selected" 时 当前项即为默认远中项

```

```

label：表示用户界面中某个元素的说明。

将一个 `<label>` 和一个 `<input>` 元素匹配在一起，你需要给 `<input>` 一个 `id` 属性。而 `<label>` 需要一个 `for` 属性，其值和  `<input>` 的 `id` 一样。

```html
<label for="username">Click me</label>
<input type="text" id="username">
**********************************
<input type="text" id="XXX">
<lable for="xxx"><img src="imges.png"></lable>
```

另外，你也可以将 `<input>` 直接放在 `<label>` 里，此时则不需要 `for` 和 `id` 属性，因为关联已隐含存在：

```html
<label>Do you like peas?
  <input type="checkbox" name="peas">
</label>
```

注意事项：

一般不监听input的click事件

**form里面的input要有name**

**form里要放一个type=submit 才能触发submit 事件**

> 知识点：自闭合标签

在HTML中，标签分为两种：一般标签和自闭合标签。那么它们之间有什么区别呢？我们先来看一个例子。

- 1）一般标签：由于有开始符号和结束符号，因此可以在内部插入其他标签或文字。
- （2）自闭合标签：由于只有开始符号而没有结束符号，因此不可以在内部插入标签或文字。所谓的“自闭合”，指的是本来要用一个配对的结束符号来关闭，然而它却“自己”关闭了。

| 标签      | 说明                             |
| :-------- | :------------------------------- |
| <meta />  | 定义网页的信息（供搜索引擎查看） |
| <link />  | 引入“外部CSS文件”                |
| <br />    | 换行标签                         |
| <hr />    | 水平线标签                       |
| <img />   | 图片标签                         |
| <input /> | 表单标签                         |
