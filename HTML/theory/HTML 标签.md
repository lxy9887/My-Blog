## HTML 标签

[TOC]

#### 英语小课堂

![image-20220310143336790](E:\TXT\Blogimge\image-20220310143336790.png)

heading          标题                      order     顺序秩序

body           身体正文                  ordered   有顺序的

paragraph  段落                         unordered  无顺序的

section        章 节                       description   描述

article           一篇文章                 term  术语

main           主要                         data  数据

aside          旁边的                        quote  引用

anchor       定点，锚                    block 块

strong         强壮 重要                    inline  行内 内联

emphasis    强调 重读                   break  打断

#### 学习工具

《网道HTML教程》

习惯：每次联系都新建目录，每个项目也都建立一个目录

VScode 插件 ：Prettier

如何获得代码连接：

* 使用JS Bin  [The W3C Markup Validation Service](https://validator.w3.org/)
* 饥人谷 JS Bin 使用 jsjirengu.com

代码沙盒 ：codesandbox.io （可以插入图片，保存分享）[CodeSandbox: Online Code Editor and IDE for Rapid Web Development](https://codesandbox.io/)

#### HTML 起手式

Vscode中起手式的快捷打开方式，! +tab

![image-20220310192335907](E:\TXT\Blogimge\image-20220310192335907.png)

```html
<!DOCTYPE html> <!--文档类型-->
<html lang="zh-CN"> <!--html必要，lang 表示语言是什么 这里的 en 指的是英文，zh-CN指的是中文-->
<head><!--head里面包含着看不见的标签，它和body一般不缩进-->
    <meta charset="UTF-8"> <!--文件的字符编码是UTF-8(支持所有)，如果写的编码和实际html编码不同的话会出现乱码-->
    <meta http-equiv="X-UA-Compatible" content="IE=edge"> <!--最新版本的Ie浏览器-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  <!--防止页面缩放-->
    <title>标题</title> <!--标题-->
</head>
<body>
    
</body>
</html>
```

#### HTML 章节标签

用来表示文章/书的层级

1. h1-h6 标题
2. section 小节
3. article  文章
4. p 段落
5. header 头部
6. footer 脚部
7. main 主要内容
8. aside 旁支内容
9. div 划分

```html
<!DOCTYPE html>
<html>

<head><!--head里面包含着看不见的标签-->
  <meta charset="utf-8">
  <title>HTML标签</title>  
</head>  
<body>
  <header>顶部广告</header> <!--头部-->
    <div> <!--划分-->
  <main> <!--主要内容-->
    <h1>文章标题</h1>
    <section> <!--小节-->
      <h2>第一章</h2> 
      <p>这是一段话一段话</p>
    </section>
    <section>
      <h3>1.2节</h3>
      <p>一段话就是好多好多人嗷嗷</p> <!--段落-->
    </section>
    <footer>&copy饥人谷版权所有</footer> <!--脚部-->
  </main>
  <alisd><!--次要内容-->
    参考资料 1 2 2
  </alisd>
  </div>
</body>
</html>
```

```html
<footer>&copy  </footer> <!--&copy 是防伪编制-->
```

* **全局属性** （任何标签都可以具有的属性）

class ：给标签分类  就是某一部分是什么样子的进行归类 

contenteditable ： 可编辑任何元素  就是客户可以直接编辑 可以用作调试技巧

hidden : 就是隐藏 

id  ：给标签加名字然后添加样式与class 类似，

id 属性规定 HTML 元素的唯一的 id。id 在 HTML 文档中必须是唯一的。id 属性可用作链接锚（link anchor），通过 JavaScript（HTML DOM）或通过 CSS 为带有指定 id 的元素改变或添加样式。不到万**不得已不用id** **在控制台打出windows.时 控制台所显示的所有单词都不能作为 id的名字**  就是忌讳

style：规定元素的样式  css html js属性同时存在的话，**js优先级会覆盖css。**

tabindex：规定元素的tab键次序，就是相当于鼠标，tab 顺序根据后面数字大小的顺序来规定的 但是不一定是连着的  🤡注意如果 tabindex=0 则tab顺序为最后一个，tabindex=-1 则不会进行访问。tabindex=1，它会按照1 2 3顺序走，**特殊值0**“最后访问”，**特殊值-1**“别访问我”。

title：规定有关元素的额外信息  **鼠标放上去显示完整的一段话**

contextmenu ：规定元素的上下文菜单，上下文菜单在用户点击元素时显示

1. **class**

```html

<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
  <style> <!--表示风格，一般放在head里 这样隐藏风格设置-->
      .middle{background:black;color:white;
  } <!--.middle=[class=middle] 但是注意 这里是指 只要出现 middle 这个字样 都符合这个格式-->
      .bordered{border: 10px solid red;
      }
  </style>
</head>
<body>
  <header>顶部广告</header>
   <div class="middle bordered">  <!--如果是这样的class 在head 里面设置的 class 一定要是一样的名字 为了解决一定要一样的问题 通常用.middle 表示-->
  <main>
    <h1>文章标题</h1>
    <section>
      <h2>第一章</h2>
      <p>这是一段话一段话</p>

    </section>
    <section>
      <h3>1.2节</h3>
      <p>一段话就是好多好多人嗷嗷</p>
    </section>
    <footer>&copy饥人谷版权所有</footer>
  </main>
  <alisd>
    参考资料 1 2 2
  </alisd>
  </div>
</body>

</html>
```

2. **contenteditable**

![image-20220310222737875](E:\TXT\Blogimge\image-20220310222737875.png)

如果把style 放在head 外面会如何？

将style 放在body 下面会显示，并加入style {display: block;} 

并且将style 设置成可以编辑 就可以实现客户端编辑样式的操作

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
 
</head>

<body>
  <style contenteditable>
       style {display: block;} .middle{background:black;color:white;
    }
      .bordered{border: 10px solid red;
      }
  </style>
  <header>顶部广告</header>
  <div class="middle bordered" contenteditable>
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话一段话</p>

      </section>
      <section>
        <h3>1.2节</h3>
        <p>一段话就是好多好多人嗷嗷</p>
      </section>
      <footer>&copy饥人谷版权所有</footer>
    </main>
    <alisd>
      参考资料 1 2 2
    </alisd>
  </div>
</body>

</html>
```

![image-20220310224905995](E:\TXT\Blogimge\image-20220310224905995.png)

3.  **hindden 隐藏**

![image-20220310231427955](E:\TXT\Blogimge\image-20220310231427955.png)

4. **id**

```html
<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
 <style>
        .middle{background:black;color:white;
    }
      .bordered{border: 10px solid red;
      }
     #xxx{border: 10px solid yellow}<!--专门设置id的样式-->   
  </style>
</head>

<body>
  <header id="xxxx">顶部广告</header> <!--可以在head里对id 进行设置-->
  <div  class="middle bordered" contenteditable>
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话一段话</p>

      </section>
      <section>
        <h3>1.2节</h3>
        <p>一段话就是好多好多人嗷嗷</p>
      </section>
      <footer hidden>&copy饥人谷版权所有</footer>
    </main>
    <alisd>
      参考资料 1 2 2
    </alisd>
  </div>
</body>

</html>
```

5. **style**

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
 <style>
        .middle{background:black;color:white;
    }
      .bordered{border: 10px solid red;
      }
    #xxx{border: 10px solid yellow} ✨✨✨
  </style>
</head>

<body>
  <header id="xxx" style="border: 10px solid green">顶部广告</header> <!--可以在head里对id 进行设置-->✨✨✨
    🤡这里需要注意两个标星的地方，当同时定义id和style时，style会覆盖id 的样式。style具有更高的优先级，因为style是HTML的属性不是CSS，但是若css HTML js 同时存在以js 为准。
  <div  class="middle bordered" contenteditable>
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话一段话</p>

      </section>
      <section>
        <h3>1.2节</h3>
        <p>一段话就是好多好多人嗷嗷</p>
      </section>
      <footer hidden>&copy饥人谷版权所有</footer>
    </main>
    <alisd>
      参考资料 1 2 2
    </alisd>
  </div>
</body>

</html>
```

6. **tabindex**

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
 <style>
        .middle{background:black;color:white;
    }
      .bordered{border: 10px solid red;
      }
    #xxx{border: 10px solid yellow} 
  </style>
</head>

<body>
  <header id="xxx" style="border: 10px solid green;" tabindex=1>顶部广告</header> <!--可以在head里对id 进行设置-->
  <div  tabindex=2 class="middle bordered" contenteditable> <!--tab 顺序根据后面数字大小的顺序来规定的 但是不一定是连着的  🤡注意如果 tabindex=0 则tab顺序为最后一个 tabindex=-1 则不会进行访问-->
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话一段话</p>

      </section>
      <section>
        <h3>1.2节</h3>
        <p>一段话就是好多好多人嗷嗷</p>
      </section>
      <footer tabindex=3>&copy饥人谷版权所有</footer>
    </main>
    <alisd>
      参考资料 1 2 2
    </alisd>
  </div>
</body>

</html>
```

知识点：如果一行文字太多想用省略号来代替 在head 里面输入一下三个代码

![image-20220310235025056](E:\TXT\Blogimge\image-20220310235025056.png)

7. title 指的是鼠标放在文字上所显示的内容

![image-20220310235852120](E:\TXT\Blogimge\image-20220310235852120.png)

```html
<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <title>HTML标签</title>
 <style>
        .middle{background:black;color:white;
    }
      .bordered{border: 10px solid red;
      }
    #xxx{border: 10px solid yellow;
     white-space:nowrap;
      overflow:hidden;
   text-overflow:ellipsis; 
   } 
   
  </style>
</head>

<body>
  <header id="xxx" style="border: 10px solid green;" tabindex=1 title="完整内容">顶部广告这里很多字很多字很多字多到溢出来溢出来溢出来溢很多字很多字多到溢出来溢出来溢出来很多字很多字多到溢出来溢出来溢</header> <!--可以在head里对id 进行设置-->
  <div  tabindex=2 class="middle bordered" contenteditable>
    <main>
      <h1>文章标题</h1>
      <section>
        <h2>第一章</h2>
        <p>这是一段话一段话</p>

      </section>
      <section>
        <h3>1.2节</h3>
        <p>一段话就是好多好多人嗷嗷</p>
      </section>
      <footer tabindex=3>&copy饥人谷版权所有</footer>
    </main>
    <alisd>
      参考资料 1 2 2
    </alisd>
  </div>
</body>

</html>
```

#### 默认样式

为什么有默认样式：因为HTML被发明的时候 css还没出生

如何查看默认样式：浏览器看开发者工具，elements->点击标签样式->Style->user agent stylesheet(指的是浏览器默认的样式)

在elements style{}中输入css 语法 就可以实现对HTML传统样式的更改。

![image-20220312110921566](E:\TXT\Blogimge\image-20220312110921566.png)

css rest 就是 把HTML原有的样式进行更改

可以参考各大厂代码： 

进入大厂首页，chrome开发者工具，点开，复制到自己的项目，命名为reset.css

关于表格的设置：

```css
table{
border-collapse: collapse;  <!--将网格合并起来-->
border-spacing:0;
}
```

![image-20220312123611013](E:\TXT\Blogimge\image-20220312123611013.png)

#### 内容标签

1. ol+li  有顺序列表

   ```html
   
   <body>
     <div>
       <main>
         <h1>前端是什么</h1>
         <section>
           <h2>第一章：工作内容</h2>
           <p>前端每天要做的事情有</p>
           <ol><!--ordered list 有顺序的列表-->
             <li>发邮件</li> 
             <li>跟产品经历沟通</li>
             <li>写页面</li>
             <li>打lol</li><!--list item ol只能还有li-->
           </ol>
     </div>
   </body>
         
   ```

   ![image-20220312132324331](E:\TXT\Blogimge\image-20220312132324331.png)

2. ul+li  无序列表

   ```html
   <body>
     <div>
       <main>
         <h1>前端是什么</h1>
         <section>
           <h2>第一章：工作内容</h2>
           <p>前端每天要做的事情有</p>
   <ul> <!--unordered list 没有顺序的列表-->
             <li>写作业</li>
             <li>打游戏</li>
             <li>查资料</li>
           </ul>
      </div>
   </body>
               
   ```

   ![image-20220312132909846](E:\TXT\Blogimge\image-20220312132909846.png)

3. dl+dt+dd

   ```html
   <dl> <!--表述列表-->
             <dt>思思</dt> <!--表述东西-->
               <dd>大美女</dd><!--表述内容-->
   </dl>
   ```

4. pre （由于默认多个连续的空白都显示一个空, 所以加上pre就可以实现 与代码操作相同）

   ```html
     <h2><pre>第一章：   
           
           
           
           工作内容</pre></h2>
   ```

   ![image-20220312133632129](E:\TXT\Blogimge\image-20220312133632129.png)

5. hr 用来做分割线 （单）

6. code （写代码时，代码字母等宽，且默认不会换行 ）

   这里一般是pre 包裹 code

   ```html
    <pre>
           <code>
             var a =1
             console.log(a)     
           </code>
    </pre>
   ```

7. br 换行使用（单）

8. a 网址

   ![image-20220312134739208](E:\TXT\Blogimge\image-20220312134739208.png)

```html
<p>
          访问网站<a href="http://qq.com" target="-blank">qq</a>  <!--这里target 是只用新窗口打开-->
</p>
```

9. em 语气上的强调
10. strong 是强调内容本身的重要性
11. quote 引用的意思 
12. blockqute 是一种一整块引用的意思

![image-20220312135525539](E:\TXT\Blogimge\image-20220312135525539.png)

#### 总结：

最近，跟着pink老师学完了html，整理了常用标签。
首先介绍一下双标签
双标签
1.标题标签`<h1>-<h6> `特点：1.作为标题使用，并且重要性依次递减 2.加了标题的文字会变得加粗，字号也会依次增大 3.一个标题独占一行
2.段落标签`<p> </p>`特点：1.文本会根据浏览器窗口的大小自动换行 2.段落和段落之间有间隙
3.加粗标签`<strong></strong> <b></b>`
4.倾斜标签`<em></em> <i></i>`
5.删除标签`<del></del> <s></s>`
6.下划线标签`<ins></ins> <u></u>`
7.盒子标签`<div>`我是一个div标签（大盒子），我自己独占一行`</div>` `<span>`我是一个span标签（小盒子），多个自己占一行`</span>`

8.超链接标签：
分类：外部链接和内部链接
外部链接`<a href="调转目标" target="目标窗口的弹出方式">文本或者图像</a>`
herf:用于指定链接目标的url地址，为必须属性，当标签应用href属性时，他就具有了超链接功能。(必须要以http://开头)
target用于指定链接页面的打开方式，`_self`为默认值，`_blank`为在新窗口打开方式
列如：`<a href="http://jwc.uzz.edu.cn/" target="_blank">枣庄学院界教务处</a>内部链接`
网站内部页面的相互链接
列如`<a href="06图像标签.html" target="_blank">跳转到图像标签的网页</a> （两个网页处在同一级）`
空链接：没有想好链接目标
列如：`<a href="#">首页</a>`
下载文件链接：当href不是网页网站，而是文件或者压缩包时，会下载文件
列如：`<a href="新建 DOCX 文档.docx" target="_blank">下载文件</a>`
网页元素链接：网页中的各项元素，如图形，表格，照片都可以添加超链接（把照片当文字就可以）
例如： `<a href="06图像标签.html"><img src="123.jpg"></a>`
锚点链接：点击链接，可以快速定位到页面中的某个位置
例如：在链接文本的href属性中，设置属性值为#名字的形式，如`<a href="#two">第二集</a>`
找到目标位置标签，里面添加一个id属性=刚才的名字，如：``<h3 id="two">`第二季介绍`</h3>``

单标签
换行标签`<br /> `特点：单标签，没有大缝隙
图像标签：`<img src="图像url" /> ` src是标签的必须属性，用于指定图像文件的路径和文件名
（通常将html文件和图片放到同一文件夹下,则src=“img.png”)
图像的其他标签：alt：替换文本，用于：图片不能显示时（即图片加载出错时）文字显示出来
图片加载成功的时候，alt命令相当于做了个无用功
title：鼠标放置到图像上，显示的文字
width：给图像设定宽度
height：给图像设定高度(高和宽通常设定一个,会按比例缩放)
border：给图像设定边框粗细

```html
<img src="123.jpg" alt="我是小芬"  title="我是小粉123" height="100" />
```

