# markdown语法笔记

## 概述

### 哲学

markdown的目标是易阅读、易编写。

### markdown和html

markdown文件里也可以用html书写（markdown可以说是html的简化版，转换器器是把markdwon语法转换成html标签，markdown语法只对应了一部分html标签，它的语法只是涵盖html纯文字的范围）。只有区块元素（div、table、pre、p等），必须在前后加上空行，以利于内容区隔。注意：*markdown语法在html区块标签中不会被进行处理。*html的区段标签（span、cite、del等）则不受限制，可以与markdown语法混合使用。

### 特殊字符自动转换

<和&在makdown里可以直接使用，不用像html那样使用实体的形式。注意：*代码范围内(不论行内还是区块)，<和& 都一定被转换成html实体。*



## 区块元素

### 段落和换行

一个段落是由一个以上相连接的行句组成，而一个以上的空行（空行的定义是显示上看起来像是空行，便会被视为空行）则会切分出不同的段落。

markdown允许段落内强制段断行，在行尾加上两个以上的空白，然后按下enter。

### 标题

markdown支持两种标题语法，setext形式是用底线的形式，利用=（最高阶标题）和-（第二阶标题）放在标题文字的底部，任何数量的=和-都可以有效果。atx形式则是在行首插入1-6个#，对应标题1-6阶，可以选择性的关闭atx样式的标题，在行尾加上#，数量不需要和行首一样，这样看起来比较舒服。

### 块级引用

在每行的最前面加上>，也允许只在整个段落的第一行最前面加上>。区块引用可以有层级的，根据层数加上不同数量的>。引言的区块内页可以使用其它markdown语法，包括标题、清单、代码区块等。

### 清单

markdwon支持有序清单和无序清单，无序清单使用星号、加/减号作为清单标记。有序清单使用数字接着一个英文句点，清单标记上的数字并不会影响输出的html结果。

清单项目标记通常放在最左边，其实也可以缩排，最多三个空白，项目标记后面则一定要接着至少一个空白或tab。

如果清单项目间用空行分开，markdown会把项目的内容在输出时用p标签包起来。

清单项目可以包含多个段落，每个项目下的段落必须缩排4个空白或是一个tab。

如果每行都有缩排看起来会好看很多，当然也可以不缩排。如果要在清单项目内放进引言，那>就需要缩排。如果要放代码块，该区块就需要缩排两次，也就是8个空白或两个tab。

在句点前面加反斜线可以避免不小心产生的项目清单。

### 程序代码块

markdow会用pre和code标签把代码块抱起来。

markdown中建立代码块只要缩排4个空白或是1个tab。这个每行一阶的缩排，都会被移除。

程序代码块会一致持续到没有缩排的那一行（或是文件结尾）。

&、<、>会自动转换成html实体。

代码块中markdown语法不会被转换。

### 分割线

在一行中用三个或以上的星号、减号、底线来建立一个分割线，行内不能有其它东西。符号中间可以插入空白。

## 区段元素

### 链接

markdown支持两种形式链接语法：行内和引用两种。不管是哪一种，链接的文字都是用[方括号]来标记。

行内形式只要在方括号后面接着括号并插入网址链接即可。如果还想加上链接的title，在网址后面用双引号把title文字包起来即可。

引用形式使用另一个方括号接在链接文字的括号后面，第二个方括号里面填入用以辨识链接的标签。两个方括号中间可以选择性的加上空白。接着在文件的任意处把这个标签的链接内容定义出来。

链接定义的形式：

1. 方括号，里面输入链接的辨识用标签（辨识标签可以有字母、数字、空白和标点符号，不区分大小写）

2. 接着一个冒号

3. 接着一个以上的空白或tab

4. 接着链接的网址（也可以用方括号包起来）

5. 选择性的接着title内容， 可以用单引号、双引号或是括弧包裹（titile可以放到下一行，也可以加一些缩排，网址太长的话这样会比较好看）

网址定义只有在产生链接的时候用到，不会出现在文件中。

预设的链接标签功能可以省略指定连接标签，这种情形下链接标签和链接文字视为相同。使用预设链接标签只要在链接文字后面加上一个空的方括号。

引用形式的链接重点不在于好写，而是比较好读。

### 强调

使用星号（*）和底线（_）作为标记强调字词的符号，被符号包围的字词会被转成用em标签包围，用两个符号包起来的会被转成strong。用的什么符号开启标签，就要用什么符号结束。

强调可以直接插在文字中间，但是如果符号两边都有空白的话，他们会被哦当成普通的符号。

如果要插入普通的星号或底线，要在符号前面加上反斜线。

### 代码段

用反引号（`）把行内代码包起来。

要在代码段内插入反引号，可以用多个反引号来开启和结束代码段。

代码段的起始和结束端都可以放入一个空白，这样就可以在区段的一开始就插入反引号。

代码段内&和尖括号都会被转成html实体。

### 图片

插入图片语法类似链接的语法，同样有两种样式：行内和引用。

行内图片语法：

1. 一个感叹号!

2. 接着一对方括号，里面放上图片的替代文字

3. 接着一对普通括号，里面放上图片的网址，最后还可以用引号包住并加上选择性的title文字

引用式图片语法：

感叹号!开头，其余同链接引用语法。

markdown不能指定图片宽高，如果需要可以使用html的img标签。

## 其它

### 自动连接

用尖括号把网址包起来，markdown会自动转换成连接。连接的文字和连接位置一样。

自动的邮件连接也类似，只是markdown会先做一个编码转换的过程，把文字字符转成16进制码的html实体，这样可以混淆一些不好的信箱地址收集机器人。

### 反斜线

markdown可以利用反斜线来插入一些在语法中有其它意义的符号，支持下面这些符号前面加上反斜线来帮助插入普通符号：

    \	反斜线
    `	反引号
    *	星号
    _	底线
    {}	大括号
    []	方括号
    ()	括号
    #	井号
    +	加号
    -	减号
    .	英文句点
    !	感叹号