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

