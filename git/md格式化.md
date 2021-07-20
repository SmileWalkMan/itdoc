一、标题<br>
　　一般使用 # 来进行层级标识。共 6 个层级，再多不识别。<br>
<br>
　　#  => h1;<br>
<br>
　　## => h2;<br>
<br>
　　### => h3;<br>
<br>
　　#### => h4;<br>
<br>
　　##### => h5;<br>
<br>
　　###### => h6;<br>
<br>
　　注：h1 级别会默认带一个 <hr/><br>
<br>
<br>
<br>
二、分隔线<br>
　　至少三个 * 或 - 或 _ ，有空格也可以，不必连续。<br>
<br>
<br>
<br>
三、换行<br>
　　两个空格 + 一个回车。<br>
<br>
<br>
<br>
四、代码<br>
　　一行代码好像有简写，不过为了统一方便（偷懒，不想记），如下格式：<br>
<br>
1<br>
2<br>
3<br>
4<br>
5<br>
```<br>
code code code<br>
code code code<br>
code<br>
```<br>
　　即首尾各多行  ``` 。<br>
<br>
<br>
<br>
五、引用<br>
　　符号是 > ，引用里可以套引用，理论上无限嵌套。如：<br>
<br>
1<br>
2<br>
3<br>
4<br>
5<br>
> 一级<br>
>> 二级<br>
>>> 三级<br>
>>>> 四级<br>
...<br>
<br>
<br>
　　图片上传不了，请参考 https://www.cnblogs.com/liugang-vip/p/6337580.html。<br>
<br>
<br>
<br>
六、强调<br>
　　* 文本1 * 或 _ 文本1 _ 　　斜体；<br>
<br>
　　** 文本2 ** 或者 __ 文本2 __ 　　加重强调；<br>
<br>
　　*** 文本3 *** 或者 ___ 文本3 ___ 　　特别强调；<br>
<br>
　　七、链接<br>
　　格式：[页面文字](链接地址)，如：[百度](https://www.baidu.com/)；<br>
<br>
　　但是，md 中链接不支持 _blank，所以个人的写法还是直接写成： <a href="www.baidu.com" target="_blank">百度xx</a> ；<br>
<br>
<br>
<br>
八、列表<br>
　　有序列表（注意，' . ' 后面要跟一个空格）：<br>
<br>
1<br>
2<br>
3<br>
1. xxxx<br>
2. xxxxx<br>
3. xxxx<br>
　　无序列表（注意，' * ' 后面要跟一个空格）：<br>
<br>
1<br>
2<br>
3<br>
* xxxx<br>
* xxxx<br>
* xxxxx<br>
　　也支持嵌套，使用时在嵌套列表前按 tab 或 空格 来缩进,去控制列表的层数。<br>
<br>
<br>
<br>
九、图片<br>
　　和 链接 类似，格式：  ![Alt text](http://xxx.com/path1/path2/abc.png) 。<br>
<br>
<br>
<br>
十、表格<br>
　　<br>
<br>
　　注意：上面是三种不同的写法，第一种的分割线后面的冒号表示对齐方式，写在左边表示左对齐，右边为右对齐，两边都写表示居中。<br>
