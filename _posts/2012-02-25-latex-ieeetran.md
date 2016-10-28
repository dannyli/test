---
layout: post
title:  "用 LaTeX 写 IEEE 论文 —— IEEETran 使用笔记"
date:   2013-07-25 14:17:59 +0800
categories: 
- Notes 
tags:
- LaTeX
- IEEE

---

本文基于安装了 [CTeX 套装](http://www.ctex.org/CTeXDownload) 的 64位 Windows 7 系统。

## 一、更新 IEEETran 包
---

CTeX 套装自带适于 IEEE 期刊和论文的 IEEETran 模板包。 如果需要更新到最新版本的 IEEETran，请按照以下步骤进行：

1. 进入 IEEETran package [下载页面](https://www.ctan.org/tex-archive/macros/latex/contrib/IEEEtran)，下载 IEEETran.zip：;
2. 将压缩包里根目录的 IEEETran.cls 文件解压到本地 `C:\CTEX\MiKTeX\tex\latex\ieeetran`;
3. 将压缩包里 bibtex 文件夹下的三个 .bib 文件解压到本地 `C:\CTEX\MiKTeX\bibtex\bib\ieeetran`;
4. 将压缩包里 bibtex 文件夹下的五个 .bst 文件解压到本地 `C:\CTEX\MiKTeX\bibtex\bst\ieeetran`;

然后就可以用最新版本的 IEEETran 模板 写文章了。

## 二、IEEETran 简单说明
---

IEEETran 的使用方法可以参照压缩包里的 [IEEEtran_HOWTO.pdf](http://mirrors.ctan.org/macros/latex/contrib/IEEEtran/IEEEtran_HOWTO.pdf) 文件。

压缩包里有七个 .tex 文件可以作为模板。 其中最常用有以下几个：

* bare_conf.tex: 会议论文模板
* bare_jrnl.tex: 期刊论文模板
* bare_adv.tex: 包括一些更高级选项说明的模板

使用 IEEETran 的方法是在 .tex 文件的最顶部加上

~~~ latex
\documentclass[journal]{IEEEtran}
~~~

其中的 `journal` 还可以更改为 `conference`, `technote`, `peerreview`, `peerreviewca`。具体意义可参考上面给出的帮助文件。

## 三、其他
---

* 更新 Sumatra PDF。 [下载](http://www.sumatrapdfreader.org/download-free-pdf-viewer.html)最新的文件后，覆盖原有的 sumatraPDF.exe。 该文件位于 `C:\CTEX\CTeX\ctex\bin`