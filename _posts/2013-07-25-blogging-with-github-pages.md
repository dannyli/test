---
layout: post
title:  "使用 GitHub Pages 建立博客"
date:   2013-07-25 14:17:59
categories: 
- Notes 
tags:
- Jekyll
- GitHub

---
## 一、GitHub Pages
---
我们可以利用 [GitHub Pages](http://pages.github.com/ "GitHub Pages") 创建个人博客，其好处是简洁高效，因为生成的是纯静态页面，不用读取数据库内容，所以页面访问速度很快。对于小白，首先要知道什么是 Git 和 GitHub。当然，不知道也无所谓。但是利用 GitHub Pages 写博客（大多数程序员用其当笔记本），必须满足以下条件：

* 喜欢折腾；
* 喜欢简洁和格式化；
* 学会使用 [Markdown](http://daringfireball.net/projects/markdown/ "Markdown") 或其他一种标记语言；
* 其他任何这里没有提到的原因

这里并不想详细写出建立 GitHub Pages 的每一步，因为关于它的部署、设置以及使用的网上资料已经很详细。

## 二、创建 GitHub 账户
---
当然你要有一个 [GitHub](https://github.com/) 账户。注册成功后参照下面的页面下载或配置本地 Git 环境。

* <https://help.github.com/articles/set-up-git>

如果嫌手动安装配置麻烦，可以直接下载并安装使用 [GitHub Desktop](https://desktop.github.com/)。非常直观好用，不用（相对）繁琐的命令行操作。

## 三、创建 GitHub Pages
---
GitHub 为每一个用户分配一个形如 username.github.io 的个人域名。比如我的是 dannyli.github.io。但是这个网址默认是没有开启的。可以按照下面的链接指示的方法利用官网的 Automatic Page Generator 创建 GitHub Pages。

* <https://help.github.com/articles/creating-pages-with-the-automatic-generator>

## 四、使用本地 GitHub Desktop 
---
将建立的空 repo "username.github.io" clone 到本地。按照规定格式创建 markdown 源文件，再用 GitHub 程序推回 GitHub，而可以在浏览器里浏览的静态页面需要在 GitHub 服务器中更新生成后才能浏览。所以调试页面和话是比较不方便的。

也可以在本地创建编译环境。如果是 MacOS/Linux，可以按照 [Jekyll 官网](http://jekyllrb.com/docs/installation/)给的方法很轻松的创建本地 Jekyll 环境，在本地编译调试产生一个默认的网站。Windows 下似乎的方法参考[这里](/notes/windows-7-jekyll/)。

一个好办法是在 GitHub 搜索并 fork 别人的模板，例如 GitHub 创始人给出的一些网站：

* [https://github.com/mojombo/jekyll/wiki/sites
](https://github.com/mojombo/jekyll/wiki/sites)

把 fork 的 repo 下载下来，复制粘贴到之前 clone 到本地的文件夹内，然后进行相应的修改。这种“剽窃”在开源社区是合理的，但是注意保留作者的信息（如果作者有申明）。

## 五、使用 Markdown 写博客
---
Markdown 其实不是一种新语言，只是 HTML 的一种转换器。语法可参照官方的 [Syntax](http://daringfireball.net/projects/markdown/syntax)。Markdown (.md 格式)文件是纯文本文件，可以用任何文本编辑器撰写。 可视化的编辑器更直观，这里推荐：

* [Mou](http://mouapp.com/) (OS X)
* [MarkdownPad](http://markdownpad.com/) (Windows)

![](/assets/images/markdownpad-screenshot.png)

.md 文件有一个开头部分 ([Front Matter](https://jekyllrb.com/docs/frontmatter/))，以 [YAML](http://yaml.org/) 格式说明了文件的一些变量， 例如下面一段：

~~~ yaml
---
layout: post
title: Blogging Like a Hacker
---
~~~

常用的默认变量包括 layout, categories/category, tags, 具体的意义可以参照[官方说明](https://jekyllrb.com/docs/frontmatter/)，也可以自定义变量。 按照要求的文件名格式保存在 _post 子目录下。 上面的例子中，你可以在 _layouts 文件夹的 post.html 模板文件某个地方插入 `{% raw  %}{{post.title}}{% endraw %}`，这样每个 post 页面中就会把这个地方替换为 title 对应的值，如 `Blogging Like a Hacker`。

完成内容编辑后，下一步就是使用本地环境编译源文件为 HTML，然后 push 或者 sync 所有文件到 GitHub 的服务器上。 

## 六、域名绑定
---
如果购买了独立域名，可以绑定到 GitHub Pages 上来，请参考：

* [https://help.github.com/articles/about-supported-custom-domains/](https://help.github.com/articles/about-supported-custom-domains/)