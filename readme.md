# learn Tex

## Chapter 1
### Basics

+ `\` 加英文字母表示命令，`\TeX{}` 用 `{}` 表示命令后的空格
+ 命令格式 `\command[optional param][param]`
  ```tex
  You can \textsl{lean} on me
  Please start a new line here!\newline
  Thank you.
  ```
+ `%` 表示注释

### Input File
+ `\documentclass{..}` 文档开始
+ `\usepackage{..}` 加载包
+ `\begin{document}` 和 `\end{document}` 正式开始

### layout

+ `\documentclass[11pt,twoside,a4paper]{article}`
  说明文件的字体大小11，A4纸，适合双面打印的layout
+ `\pagestyle{style}` 页眉和页脚

### files
+ `.tex` input file
+ `.sty` 宏包
+ `.dtx` 宏包源代码
+ `.ins` installer, 解包 `.dtx` 文件
+ `.cls` 文件里和命令 `\documentclass` 一样
+ `.fd` font decription
+ `.toc` Stores all your section headers. It gets read in for the next compiler run and is used to produce the table of contents.
+ `.lof` This is like .toc but for the list of ﬁgures.
+ `.lot` And again the same for the list of tables. 

### Big Projects
有时会把 `.tex` 分成若干文件
+ `\include{filename}` 能够实现，但是会新开始一页，一般在序言里使用
+ `\includeonly{filename,filename}` 
+ `\input{filename}` 直接添加文件中的内容
+ 可以用于检查命令的语法
  ```tex
  \usepackage{syntonly} 
  \syntaxonly 
  ```

---

## Chapter 2

### Typesetting Text
+ `\\` 表示新行，如果空一行则表示新段落，新段落应该是**idea**的结合
+ `\section` 等可以用于逻辑上形成一个段

### Line Breaking and Page Breaking
+ `\\` 和 `\newline` 在一个段中产生新行
+ `\\*` 阻止新行后的 **page break**
+ `\newpage` 新页
+ `\sloppy` 宽松模式，`\fussy` 严格模式
+ `\mbox{111 000 111}` 强制要求里面的字符在一行

### ready strings
+ `\today`
+ `\TeX`

### Special Characters and Syobols
+ **`** 表示左边的引号， **'** 表示右边的引号，在英文中是这样的
+ `in-law` 是连字符，`12--67` 表示 `12—67`,`yes---no` 表示更长的 `——`，`$-1$` 这里表示负号
+ `\~`实际上是上波浪线，`$\sim$` 是真正的波浪线
+ `\slash` 表示 `/`
+ `\textdegree` 表示 **度数**
+ `\ldots` 表示省略号

### Titles, Chapters, Sections
+ `\section` `\paragraph`
+ `\part` 分部分但不影响标号

### Cross reference
+ 交叉引用
  ```tex
  A reference to this subsection \label{sec:this} looks like: ``see section~\ref{sec:this} on page~\pageref{sec:this}.''
  ```

### Footnotes
+ `\footnote{footnote text}` 创建脚注

### Emphasized words
+ `\underline{text}` 下划线
+ `\emph{text}` 斜体强调

### 枚举、列表、描述
+ `begin{enumerate}...\item...end{enumerate}` 创建数字标号的枚举
+ `begin{itemize}...\item...item[-]...end{itemize}` 创建一个列表
+ `begin{description}...\item[Stupid]...\item[Smart]...end{description}` 创建一个描述

### 左右对齐
+ `begin{flushleft}` 左对齐
+ `begin{flushright}` 右对齐
+ `begin{center}` 居中对齐

### 引用、摘要
+ `begin{quote}` 引用
+ `begin{abstract}` 摘要

### 逐字
+ `\verb+text+` 在同一个段落中可以用这个逐字显示，不会转换为内部命令，`+` 为分隔符
+ `\begin{verbatim}`

### 包含图片、图表
+ 用 `graphicx` 包，来加载图片
+ `\includegraphics[angle=90,width=\textwidth]{test.png}` 加入图片
+ 有时候图片会占很多空间，把文字挤到下一页，因此 `float` 是一个很好的选择，`\begin{figure}[placement specifier]` 或者 `\begin{table}`
  + 有用的位置标识符有 `h`，`here`
  + `t`，表示 `top`
  + `b`，表示 `bottom`
  + `p`，表示在一个特殊页面
