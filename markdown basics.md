Markdown Learning Basics
========================
Markdown语法快速入门
------------------------
* * *
##简介


&emsp;Markdown 是一个 Web 上使用的文本到HTML的转换工具，可以通过简单、易读易写的文本格式生成结构化的HTML文档。目前 github、Stackoverflow 等网站均支持这种格式。  
&emsp;Markdown 的目标是实现「易读易写」。  
&emsp;可读性，无论如何，都是最重要的。一份使用 Markdown 格式撰写的文件应该可以直接以纯文本发布，并且看起来不会像是由许多标签或是格式指令所构成。Markdown 语法受到一些既有 text-to-HTML 格式的影响，包括 Setext、atx、Textile、reStructuredText、Grutatext 和 EtText，而最大灵感来源其实是纯文本电子邮件的格式。  
&emsp;以下这篇简单的入门笔记就用刚刚学习的Markdown语法编写，写错了我也不会改的:)  
* * *
##段落、标题、区块代码

&emsp;一个段落是由一个以上的连接的行句组成，而一个以上的空行则会划分出不同的段落（空行的定义是显示上看起来像是空行，就被视为空行，例如有一行只有空白和 tab，那该行也会被视为空行），一般的段落不需要用空白或换行缩进。「由一个或多个连续的文本行组成」这句话其实暗示了 Markdown 允许段落内的强迫换行（插入换行符），这个特性和其他大部分的 text-to-HTML 格式不一样（包括 Movable Type 的「Convert Line Breaks」选项），其它的格式会把每个换行符都转成 <br \/> 标签。  
&emsp;如果你确实想要依赖 Markdown 来插入 <br \/> 标签的话，在插入处先按入两个以上的空格然后回车。     

&emsp;以上的空行就是用space+space+tab按出来的  
&emsp;的确，需要多费点事（多加空格）来产生 <br \/> ，但是简单地「每个换行都转换为 <br \/>」的方法在 Markdown 中并不适合， Markdown 中 email 式的 区块引用 和多段落的 列表 在使用换行来排版的时候，不但更好用，还更方便阅读。
* * *
##标题
&emsp;Markdown 支持两种标题的语法，类 Setext 和类 atx 形式。

&emsp;类 Setext 形式是用底线的形式，利用 = （最高阶标题）和 - （第二阶标题），例如：

  `This is an H1`

  `=============`

  `This is an H2`

  `-------------`
&emsp;写起来就是下面这个样子

This is an H1
=============
This is an H2
-------------   

&emsp;任何数量的 = 和 - 都可以有效果。

&emsp;类 Atx 形式则是在行首插入 1 到 6 个 # ，对应到标题 1 到 6 阶，例如：

`# 这是H1`

`## 这是H2`

`### 这是H3` view as
#这是H1
##这是H2
###这是H3
&emsp;或者你也可以闭合着写`# 啦啦啦啦啦#####`后面的#号不起作用，而前面#号的个数决定这标题的阶数。  
* * *
##区块引用
&emsp;Markdown 标记区块引用是使用类似 email 中用 > 的引用方式。如果你还熟悉在 email 信件中的引言部分，你就知道怎么在 Markdown 文件中建立一个区块引用，那会看起来像是你自己先断好行，然后在每行的最前面加上 > 。  
&emsp;引用的区块内也可以使用其他的 Markdown 语法，包括标题、列表、代码区块等。
&emsp;区块引用可以嵌套（例如：引用内的引用），只要根据层次加上不同数量的 > 。
>这是引用。

>>这是引用再引用。

>## 这是二阶字的引用。

&emsp;看，其实挺简单。
* * *
##列表
&emsp;Markdown 支持有序列表和无序列表。

&emsp;无序列表使用星号、加号或是减号作为列表标记：

```
*  RED  
*  GREEN  
*  BLUE
```
&emsp;view as
*  RED
*  GREEN
*  BLUE

&emsp;有序列表则使用数字接着一个英文句点：  
```
1.RED
2.BLUE
6.redd
```
&emsp;view as
1. RED
2. BLUE
6. redd

&emsp;列表项目标记通常是放在最左边，但是其实也可以缩进，最多 3 个空格，项目标记后面则一定要接着至少一个空格或制表符。要让列表看起来更漂亮，你可以把内容用固定的缩进整理好：  
```
*   hello world
*   hello world too
```
&emsp;view as
*   hello world
*   hello world too
***
##代码区块
&emsp;和程序相关的写作或是标签语言原始码通常会有已经排版好的代码区块，通常这些区块我们并不希望它以一般段落文件的方式去排版，而是照原来的样子显示，Markdown 会用 \<pre> 和 \<code> 标签来把代码区块包起来。
&emsp;要在 Markdown 中建立代码区块很简单，只要简单地缩进 4 个空格或是 1 个制表符就可以，例如，下面的输入：
```
这是一个普通段落：

  这是一个代码区块。
```
&emsp;Markdown 会转换成：
```
<p>这是一个普通段落：</p>

<pre><code>这是一个代码区块。
</code></pre>
```
&emsp;这个每行一阶的缩进（4 个空格或是 1 个制表符），都会被移除，例如：
```
Here is an example of AppleScript:

    tell application "Foo"
        beep
    end tell
```
&emsp;会被转化为：
```
<p>Here is an example of AppleScript:</p>

<pre><code>tell application "Foo"
    beep
end tell
</code></pre>
```
***
##分割线
&emsp;你可以在一行中用三个以上的星号、减号、底线来建立一个分隔线，行内不能有其他东西。你也可以在星号或是减号中间插入空格。下面每种写法都可以建立分隔线：
```
* * *

***

*****

- - -

---------------------------------------

```
***
##强调
&emsp;Markdown使用星号(\*)和底线(_)作为标记强调字符的符号。例如：
```
  *lalalala*
  _lalalala_
  **lalalala**
  __lalalala__
```
&emsp；就显示为：
*lalalala*
_lalalala_
**lalalala**
__lalalala__
&emsp;但是你的*号和_号如果两边都是空白，那只会当成普通的符号。如果要插入符号，请在前面用\\来进行转义。
