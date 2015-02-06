<!-- 
.. title: markdown syntax
.. slug: markdown-syntax
.. tags: markdown
.. date: 2014/06/24 22:46:28
.. link: 
.. description: 
-->

<!--
  ::最后一次在成都测试组KM吧发文了
-->

想写文章但一直纠结于文章的排版？屌丝哪有那么多时间在排版上纠结，于是试试最近比较火的`markdown`吧，从此告别各种一级标题，二级标题各种纠结的排版。

Markdown的目标是实现[易读易写]。

可读性，无论如何，都是最重要的。一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。Markdown语法受到一些既有 text-to-HTML的影响，包括Setext、atx、Textile、reStructuredText、Grutatext 和EtText，而最大灵感来源其实是纯文本电子邮件的格式。

# 区块元素
## 标题
标题就是word中我们经常看到的标题1...，是文档的必备元素。以下为各级标题的效果展示和基础语法。

# 标题1
```
# 标题1
```
## 标题2
```
## 标题2
```
###### 标题6
```
###### 标题6
```
####### 标题7
```
####### 标题7；没有标题7了，该格式无效
```

## 区块引用
Markdown标记区块引用类似email中用`>`的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上`>`

> markdown syntax
> markdown2
> markdown 3

```
> markdown syntax
> markdown2
> markdown 3
```
区块引用可以嵌套（例如：引用内的引用），只要加上不同数量的`>`即可。
> markdown syntax
> > markdown2
> > 

```
> markdown syntax
> > markdown2
```

## 列表
Markdwon支持有序和无序两种列表。

无序列表使用星号、加号或减号作为列表标记：

* 列表1
* 列表2
* 列表3

```
* 列表1
* 列表2
* 列表3
```

有序列表使用数字加英文句点的方式：

1. 有序1
2. 有序2
3. 有序3

## 代码区块
Here is an example of python:

    import os
    print "hello world"
## 分隔线
在一行中使用三个以上的星号，建号，底线来建立分隔线。

-------------------
**************
```
-------------------
**************
```
# 区段元素
## 链接
Markdown 支持两种形式的链接语法： 行内式和参考式两种形式。不管是哪一种，链接文字都是用 [方括号] 来标记。
### 行内式
This is [OA](http://www.oa.com/ "tips") website.
```
This is [OA](http://www.oa.com/ "tips") website.
```
### 参考式
This is [OA] [1] website.
[1]: http://www.oa.com/ "tips"
```
This is [OA] [1] website.
[1]: http://www.oa.com/ "tips"
```
## 强调文字
Markdown使用星号(`*`)和底线(`_`)作为强调字词的符号。
*this is markdown*
```
*this is markdown*
```

**this is markdown too**
```
**this is markdown too**
```

本文只是markdown一些常用语法的小科普，更多详细内容请自行脑补。
[Markdown](http://zh.wikipedia.org/wiki/Markdown "markdown维基百科")
[马克飞象](http://maxiang.info/ "比较有意思的插件")