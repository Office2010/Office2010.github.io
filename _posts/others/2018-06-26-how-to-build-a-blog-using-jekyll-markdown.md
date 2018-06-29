---
layout: article
title:  "使用github和jekyll搭建免费博客"
categories: others
image:
    teaser: /others/jekyll/Jekyll+Github.jpg
---

>简介：本文主要介绍如何使用jekyll在github上搭建一个免费的博客


# 方案的优势
- github基于github-pages的博客方案完全免费，且有稳定性保障
- 所有博文可以通过github做版本管理
- 使用markdown语法写博客,可以专注于内容无需过度关心页面样式
- markdown语法目前有非常多的博客托管网站支持，方便日后迁移
- jekyll支持markdown to html的转换，以及YAML支持。方便跟多的样式的修改


# 搭建方法
---
>
-  申请域名（也可不用）
-  在github上建立Repository
-  在Windows上安装Ruby和Jekyll环境（方便本地调试）
-  使用Jekyll建立站点发布文章（本地调试）
-  上传github仓库

## 步骤一：申请域名
---

域名的申请不是必须的，可以直接使用github提供的二级域名，其固定格式为https://githubusername.github.io。如果想要通过自己的域名访问自己的博客的话，先在申请自己的一个域名，然后再与自己的github二级域名解析，最后在github中设置一下即可，具体操作在下一步骤中介绍。

我们只需要将自己的博客数据上传远程仓库即可，github会自动识别为是一个博客系统文件的项目。

## 步骤二：在github上建立Repository
---
登录github，进入个人主页，创建一个仓库，此时名字最好为：username.github.io ，username为你的github昵称，通过这样的命名方式，github提供的二级域名访问blog 的时候地址为：https://username.github.io
当然你也可以不用username，但必须保证结尾为XXX.github.io ,此时github提供的二级域名为：https://username.github.io/XXX.github.io
![Create Repository](/images/others/jekyll/jekyll_01.jpg)

*如果之前申请有自己的域名可进行以下设置
  
进入Setting中，在GitHub Pages中箭头位置输入自己申请的域名
![domain](/images/others/jekyll/jekyll_02.jpg)
之后的操作在步骤一中也提过，只需将自己的域名解析到github提供的地址即可。

## 步骤三：在Windows上安装Ruby和Jekyll
---

jekyll是一种可以生成静态网页Blog的工具，而它是用Ruby语言写的，我们用Jekyll时需要先装上Ruby环境。Windows下是通过第三方安装程序RubyInstaller安装，下载地址[RubyInstaller](https://rubyinstaller.org/)
![RubyInstaller](/images/others/jekyll/jekyll_03.jpg)

安装完成后我们可以通过命令测试是否成功
{% highlight bash %}
gem install jekyll
{% endhighlight %}

搭建好ruby基础环境后
{% highlight bash %}
gem install jekyll
{% endhighlight %}

## 步骤四：使用Jekyll建立站点发布文章（本地调试）

安装完jekyll以后就可以创建一个本地的博客书写目录，进入自己喜欢的路径执行以下命令。随后jekyll就会自动生成一些博客的基础文件和目录，并且包含一篇现成的博文介绍jekyll

{% highlight bash %}
{% raw %}
mkdir -p ~/Blog && cd ~/Blog
jekyll new .
{% endraw %}
{% endhighlight %}


由于jekyll自动生成博客框架中有较多的默认值，并且比针对github有特殊处理所以我们在把自己的第一版博客发布到github之前需要做一些个性化配置（博客名，个人信息等）。当然，如果你觉得留着这些默认值也可直接跳过这一段，直接进行发布:)
个性化配置主要在_config.yml中进行

当然我们也可以使用一些现有的模板主题：[Jekyll模板主题](https://jekyllthemes.io/) ，当然网上还有许多炫酷的主题，根据自己需要自行选择。

### 本地测试
开启
{% highlight bash %}
jekyll server /s /serve
{% endhighlight %}


创建完本地博客目录后，可以启动jekyll的管理进程（作用相当于apache），然后就可以通过浏览器看到效果啦！

{% highlight bash %}
{% raw %}
shell> cd ~/Blog
shell> jekyll serve
Configuration file: /Users/michellezhou/Blog/cenalulu.github.io/_config.yml
Source: /Users/michellezhou/Blog/cenalulu.github.io
Destination: /Users/michellezhou/Blog/cenalulu.github.io/_site
Generating...
done.
Auto-regeneration: enabled for '/Users/michellezhou/Blog/cenalulu.github.io'
Configuration file: /Users/michellezhou/Blog/cenalulu.github.io/_config.yml
Server address: http://127.0.0.1:4000/
Server running... press ctrl-c to stop.

{% endraw %}
{% endhighlight %}


通过浏览器访问 http://localhost:4000/ 就可以看到如下效果:
![pic](/images/others/jekyll/jekyll_04.jpg)

有些jekyll主题使用了Liquid。在开启时我们需要先进行安装bundle依赖
{% highlight bash %}
bundle install
{% endhighlight %}
*如果提示bundle不是内部命令时
{% highlight bash %}
gem bundle install
{% endhighlight %}

安装完依赖关系后，我们通过
{% highlight bash %}
bundle exec jekyll serve
{% endhighlight %}
开启jekyll 服务器，开启后便可以通过 Https://localhost:4000 访问本地站点
## 步骤五： 上传github仓库
只需要将本地工程上传github即可，github自动识别网页信息。以后的更新文章只需要更新_posts文件夹中的内容即可。

#参考信息
---
> 1. [Jekyll+Github 搭建个人博客](https://www.jianshu.com/p/43dca792e3cd) 
> 2. [Jekyll 中文社区](http://jekyllcn.com/docs/home/)
> 3. [Git 的官方API](https://git-scm.com/docs)







