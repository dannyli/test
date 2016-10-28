---
layout: post
title:  "适合于 IEEE Transcations 的 EndNote 模板"
date:   2012-03-03 14:17:59
categories: 
- Notes 
tags:
- EndNote
- IEEE

---

## 基于 EndNote 自带的 IEEE.ens 修改模板 ##
---

EndNote 自带 IEEE 风格模板。但是对于一些常用的 IEEE Transactions，风格可能与默认的不太一样。 这里以 IEEE Transcations on Energy Conversion 为例子，介绍如何更改模板。

- 复制 `%ProgramFiles%\EndNote X6\Styles` (64位系统下为 `%ProgramFiles(x86)%\EndNote X6\Styles`) 里的 IEEE.ens 文件到 `%Userprofile%\Document\EndNote\Styles` 中，并改名为 `IEEE Trans.ens`
- 打开 Endnote, 从菜单栏中选择 `Edit -> Output Styles -> Open Style Manager...`
- 在列表中找到 IEEE Trans 并在前面打勾
![](/assets/images/screenshot-endnote-style-manager.png)
- 双击 IEEE Trans 进入模板编辑对话框
![](/assets/images/screenshot-template-editor.png)
- 有几个地方可能需要修改
	- `Journal Names`: 需要使用期刊的缩略名。 定义期刊缩略名的地方为 `Tools -> Open Term Lists -> Journal Term List`
	- `Bibliography -> Templates`: 由于原始模板中的期刊的时间通常只有年没有月份，而目前 IEEE Trans 一般都要都月份信息 (使用 date 标签)
	- `Bibliography -> Author Lists`: 有时会要求列出所有的作者，有时要求三人以上用 et al.

这里是我使用的风格模板：[IEEE Trans.ens](/assets/downloads/IEEE Trans.ens)

## Word中调整缩进距离 ##
---
在Word中添加Endnote引用，最后的参考列表的默认间距比较大，如图
![](/assets/images/referece-list-indent-width-word.png)
调整的方法是：点 Bibliography 标签栏右下角的箭头 -> Layout -> Hanging indent，距离改成大约 0.7 cm. 

## References ##
---
- IEEE Citation Reference [http://www.ieee.org/documents/ieeecitationref.pdf](http://www.ieee.org/documents/ieeecitationref.pdf)
- Dudley Knox Library - IEEE Citation Styles [http://libguides.nps.edu/citation/ieee](http://libguides.nps.edu/citation/ieee)