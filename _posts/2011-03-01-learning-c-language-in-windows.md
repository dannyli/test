---
layout: post
title:  "Windows 下学习 C/C++：如何开始"
date:   2011-03-01 20:17:59
categories: 
- Notes 
tags:	
- C
- C++
---

## 一、安装C编译器 ##
---
- 这里使用 MS VC 的编译器，是因为实验室电脑中都已经标配。下载并安装 Windows SDK 7.1 ： [https://www.microsoft.com/en-us/download/details.aspx?id=8279](https://www.microsoft.com/en-us/download/details.aspx?id=8279)
- 另一个常用的选择是集成了 gcc 编译器的的 [MinGW](http://www.mingw.org/)。网上很多资料介绍，这里不再介绍了。

## 二、安装集成开发环境(IDE)
---
- 这里选择 Windows下比较流行的免费IDE **[Code::Blocks](http://www.codeblocks.org/)**。下载并安装 Code Blocks： [http://www.codeblocks.org/downloads](http://www.codeblocks.org/downloads)
- 安装完毕后打开 Code Blocks 程序, 从菜单栏选择 Settings -> Compiler
- 选择 Compiler 为 `Microsoft Visual C++ 2010`
- 切换到 Linker settings 选项卡, 在 Link libraries 列表中添加 Kernel32.Lib 文件路径，如 `C:\Program Files\Microsoft SDKs\Windows\v7.1\Lib\Kernel32.Lib`

## 三、开始编程
---
建立一个新的 project, 然后就可以在 main 函数中编写自己第一个程序, 例如：

```c
#include <stdio.h>
#include <stdlib.h>

int main()
{
    printf("Hello world!\n");
    return 0;
}
```

## 四、学习参考书籍
---
C语言已经很古老了，网上的资料数不胜数。有些同学喜欢系统的学校，啃几本书：

- 千万不要用谭浩强的 [《C程序设计(第四版)》](https://book.douban.com/subject/4864940/) 作为国内很多高校的C语言教材，这本书在网上[被批的很惨](https://www.zhihu.com/question/19904116)，书中错误百出，风格也不适合教学。
