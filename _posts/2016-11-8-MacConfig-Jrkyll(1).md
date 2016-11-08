---
layout: post
title:  "Mac用户搭建GitHub-Pages(1)"
date:   2016-11-8 23:30:00 +0800
categories: jekyll
tag: jekyll
---

* content
{:toc}


一、安装Jekyll
========================

由来
------------------------

最近很多身边的朋友都开始弄起了个人技术博客主页，最近本人也一直有这个想法，在机缘巧合下朋友正好推荐了我配合`Jekyll`搭建`GitHub`主页，查了下也确实是时下比较流行的玩法，于是才有了这篇文章，网上Mac下的环境搭建教材大多层次不齐，本文在经过本人实践后整理所得，有不足之处望大家多多指正交流。

+ 感谢 [Fiona](https://fionalu.github.io/) 提供的技术顾问和参考。

+ 本人Mac环境，Mac mini（2012），RMBP（2014），macOS Sierra 10.12.1。

1、安装ruby
------------------------
（0）由于ruby安装会用到读写系统的`/usr/bin`下的文件权限，用于10.11以后MacOS已强制关闭该文件夹的读写权限，所以我们要先打开该权限：

点击重启，听见启动声按住option键，选择恢复（Recovery）模式，点击菜单栏中实用工具打开命令行（Terminal），输入如下：
{% highlight bash %}
csrutil disable
{% endhighlight %}
重启即可。如果要恢复默认，那么：
{% highlight bash %}
csrutil enable
{% endhighlight %}

（1）然后重启正常进入系统我们便可以放心安装ruby了，应用程序中打开命令行（Terminal）：
{% highlight bash %}
curl -L get.rvm.io | bash -s stable
{% endhighlight %}
等待一段时间后就可以成功安装好 RVM,然后启用rvm:
{% highlight bash %}
source ~/.rvm/scripts/rvm
{% endhighlight %}
保险起见测试一下是否安装正常：
{% highlight bash %}
rvm -v  
{% endhighlight %}
看见版本号则说明安装正常
{% highlight bash %}
TomydeMac-mini:usr tomy$ rvm -v
rvm 1.27.0 (latest) by Wayne E. Seguin <wayneeseguin@gmail.com>, Michal Papis <mpapis@gmail.com> [https://rvm.io/]
{% endhighlight %}

（2）用rvm升级Ruby
查看当前ruby版本：
{% highlight bash %}
ruby -v  
{% endhighlight %}
得到如下信息：
{% highlight bash %}
ruby 1.8.7  
{% endhighlight %}
显然版本号偏低，再输入：
{% highlight bash %}
rvm list known 
{% endhighlight %}
在列出的ruby分支表里可以尽量安装最新版本，这里安装2.3.0版本：
{% highlight bash %}
rvm install  2.3.0
{% endhighlight %}
然后我们查看系统已安装的ruby:
{% highlight bash %}
rvm list
{% endhighlight %}
现设置新版的ruby为默认项：
{% highlight bash %}
rvm use 2.3.0 --default 
{% endhighlight %}
后移除旧版本：
{% highlight bash %}
rvm remove 1.8.7
{% endhighlight %}


2、安装gem
------------------------
Mac系统自带的`gem`比较老旧我们需要对他进行换新和换源
（1）更换Ruby默认源，先查看现有的源地址：
{% highlight bash %}
gem sources -l
{% endhighlight %}
删除被强的源：
{% highlight bash %}
gem sources --remove https://rubygems.org/
{% endhighlight %}
添加淘宝源：
{% highlight bash %}
gem sources -a https://ruby.taobao.org/
{% endhighlight %}
更新`gem`：
{% highlight bash %}
gem update --system 
{% endhighlight %}
安装`rubygems`:
{% highlight bash %}
gem install rubygems-update
{% endhighlight %}
更新`rubygems`:
{% highlight bash %}
update_rubygems    
{% endhighlight %}

3、安装Jekyll
------------------------
{% highlight bash %}
gem install jekyll    
{% endhighlight %}
`Jekyll`依赖的组件会自动下载安装,待安装好后我们测试下`Jekyll`服务：
{% highlight bash %}
jekyll serve --safe --watch    
{% endhighlight %}

至此就Mac端准备工作就全部完毕，安装`Jekyll`的目的是让本机可以在发布到`GitHub`上前可以在本地测试页面样式等。



接下来的步骤请参考：[Mac用户搭建GitHub-Pages(2)]({{ '/2016/11/09/MacConfig-Jrkyll(2)/' | prepend: site.baseurl  }})
