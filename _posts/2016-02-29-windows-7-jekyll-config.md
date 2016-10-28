---
layout: post
title:  "Windows 7 下安装配置 Jekyll + kramdown + Rouge 语法高亮"
date:   2016-02-29 08:17:59
categories: 
- Notes 
tags:
- Jekyll
- GitHub
- Windows
- Markdown
- Rouge

---
## 一、安装 Ruby 和 Ruby DevKit
---
在 [Ruby 官网](http://rubyinstaller.org/downloads/)下载 Ruby 和 Ruby DevKit，推荐使用 Ruby 2.0 版本。下面是 2.0 64x版本下载链接：

- Ruby 2.0.0 x64: [rubyinstaller-2.0.0-p648-x64.exe](http://dl.bintray.com/oneclick/rubyinstaller/rubyinstaller-2.0.0-p648-x64.exe)
- Ruby DevKit 4.7.2 64x: [DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe](http://dl.bintray.com/oneclick/rubyinstaller/DevKit-mingw64-64-4.7.2-20130224-1432-sfx.exe)

首先安装 Ruby。 假设安装路径为 `C:\Ruby200`。注意要把 "Add Ruby executables to your PATH" 项勾上。
Ruby 安装完毕后解压 DevKit 包到本地，如 `C:\RubyDevKit`。在 cmd 中执行以下命令初始化 DevKit:

~~~ sh
cd C:\RubyDevKit
ruby dk.rb init
~~~

然后编辑位于 `C:\RubyDevKit` 下的 config.yml 文件，在三条横杠下面添加 Ruby 的安装路径，如

~~~
---
- C:/Ruby200
~~~

注意斜杠的方向。 保存并关闭文件，在 cmd 中执行下面命令安装 DevKit:

~~~ sh
ruby dk.rb install
~~~

到这里 Ruby 和 Ruby DevKit 安装完毕。

## 二、安装 Jekyll Gem
---
cmd中执行

~~~ sh
gem install jekyll
~~~

执行时间可能较长。 耐心等待直到安装结束。 安装结束后可以新建一个本地站点测试 Jekyll 安装是否成功：

~~~ sh
jekyll new danny-li-site
cd danny-li-site
jekyll serve --force_polling --watch
~~~
	
则可在浏览器中以 `localhost:4000` 访问。`--watch` 选项开启页面 regeneration，也就是修改页面后刷新浏览器立即可以看到更新。

可以建立一个 .cmd 文件快速启动本地 jekyll 站点，文件内容如下：

~~~ batchfile
set github_username=dannyli
cd %Userprofile%\Documents\GitHub\%github_username%.github.io
jekyll serve --force_polling --watch
~~~

把 dannyli 替换成你自己的 Github 用户名即可。

## 三、 Markdown 引擎 kramdown + 语法高亮 Rouge
---
GitHub 在 2016 年宣布[更新到 Jekyll 3.0，并且开始启用新的 Markdown 以及语法高亮](https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0)：kramdown + rouge，代替以前的 rdiscount + pygments。 所以所有旧的 .md 文件都要自行更新一下。 在 cmd 中执行以下命令安装 kramdown 和 rouge：

~~~ sh
gem install kramdown
gem install rouge
~~~

然后在站点的 _config.yml 中加上以下内容：

~~~ yml
markdown: kramdown
highlighter: rouge
~~~	

在 kramdown 中使用代码高亮的句法是：

{% raw %} 
	~~~ lang
	代码内容
	~~~
{% endraw %} 

注意 kramdown 使用三个波浪号表示 \<code\>。 将 `lang` 替换成需要高亮代码语言所对应的 [Linguist](https://github.com/github/linguist) 标记, 比如 C 语言是 `c_cpp`，可以在这里找到： <https://github.com/github/linguist/blob/master/lib/linguist/languages.yml>

语法高亮是通过 CSS 实现的。 所需的 CSS 文件由以下方法产生。 在 cmd 中执行：

~~~ sh
rougify style github > highlight_github.css
~~~	

然后就可以使用产生的 CSS 文件了。上面命令中的 `github` 是 Rouge 可选 CSS 主题之一，其他的主题包括 

~~~
colorful|github|monokai|monokai.sublime|thankful_eyes|base16|base16.dark|base16.light|base16.solarized|base16.monokai 
~~~

模板文件中添加对应的 CSS 语句即可使用。例如

~~~ html
<link rel="stylesheet" href="/media/css/highlight_github.css">
~~~

我把 .css 文件放在了 `/media/css/` 目录下。

## 四、解决本地分页错误
---
升级 Jekyll 3 以后，我发现本地的分页器出现问题。 首页的文章列表无法出现。 解决方法是执行下面的语句

~~~ sh
gem install jekyll-paginate
~~~

然后在 _config.yml 文件中增加

~~~ yml
gems: [jekyll-paginate]
#safe: true
~~~

注意上面的代码，要把 safe 一行注释掉。 

## 五、学习资源
---
下面列出学习 Jekyll/Git/Markdown 的一些好资源：

* Jekyll: <http://jekyllrb.com/docs/home/>
* Kramdown: <http://kramdown.gettalong.org/syntax.html>
* Github: <https://help.github.com/>
* GotGithub: <http://www.worldhello.net/gotgithub/>

## References
---

* [Run Jekyll on Windows](http://jekyll-windows.juthilo.com/)