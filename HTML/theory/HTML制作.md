制作步骤：

1、维基百科 

2、内容布局

* 个人简介
* 重要事件
* 主要成就
* 主要作品
* 生活照
* 生平

> 制作网页过程中的一些知识点：

* VScode自动换行，用ctrl+shift+p 搜索wrap

* 如何实现多行无序列表，用ctrl+shift+p 搜索 emmet wrap（个别行包围），输入ul>li*

* 如果有批量删除的东西，在VScode的编辑里面选择替换，在替换框里可以选择使用正则表达式 ` \[\d+\]`

* ctrl+l 是选中一行代码，shift+上是选中上面代码

* 使用http-server -c-1 是 不用缓存的情况下浏览 html

* 有多行信息在制作表格时，先按住alt 然后用鼠标选中，可以实现多行的一个代码输入，如何在一整块的表格代码两端加入 tr ，先多行选中，然后进行emmet wrap 输入

* 手动格式化 是 ctrl+shift +p 搜索 format 可以看到手动格式化的知识点。

**添加 TOC (Table of Content) 目录**

使用 a herf=#xxx 来实现

```
<nav>
        <ol>
           <li><a herf=#xxx>目录文字</li>
        </ol>
</nav>
```

注意：最下面一个锚点往往无法到达页面顶部   可以通过添加额外的空白解决

**添加图片**

注意不要让图片变形

如果图片比例不对，需要使用工具剪裁一下

如果图片尺寸过大，无需特殊处理

如果图片体积过大（300kb），则需要压缩

在线jpeg压缩 png压缩 

**添加链接**

国内一般需要添加 target=_blank。

添加完了之后要自己全部点一遍，防止出错。

**手机调试：**

在`<head>`里面加入 meta:vp 和 img max-width 就可以实现

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0, maximum-scale=1.0, user-scalable=no">
```

**步骤：**

让手机和电脑处于同一 wifi

手机可以直接用ip和端口访问电脑

http-server的IP都可以尝试

用border调试法调试CSS 

用vConsole.js 调试JS

Chrome 远程调试

搜索Chrome远程调试，如果你在浏览器中找不到【远程设备】这个选项了，那么你可以：地址栏里输 chrome://inspect，回车进入

![image-20220315154805757](E:\TXT\Blogimge\image-20220315154805757.png)

**如何做到不是同一wifi 也可以实现访问：**

在开发者工具右上角 三个点，more tools 中的JavaScript Profiler

在setting 添加网址 

![image-20220315161203432](E:\TXT\Blogimge\image-20220315161203432.png)

点击链接手机可以进行手机调试。进行inspect。

> 注意 ： 上传github时候一定要备注可预览的链接

