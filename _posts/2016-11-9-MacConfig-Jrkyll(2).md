---
layout: post
title:  "Mac用户搭建GitHub-Pages(2)"
date:   2016-11-9 00:30:00 +0800
categories: jekyll
tag: jekyll
---

* content
{:toc}


创建GitHub代码仓库
------------------------
登陆你的`GitHub`账号，然后`Create a repository`:

![1]({{ '/styles/images/jekyll-config/1.png' | prepend: site.baseurl  }})

新建一个`repository`时, 命名方式切记！！！一定要为 `你的用户名 + github.io`。如我的用户名为 `joeyqiang`，所以`repository`命名为 `joeyqiang.github.io`，如下图。

![2]({{ '/styles/images/jekyll-config/2.png' | prepend: site.baseurl  }})

上`https://desktop.github.com/`下载`GitHub`官方代码托管客户端`GitHub Desktop`:

![3]({{ '/styles/images/jekyll-config/3.png' | prepend: site.baseurl  }})

打开`GitHub Desktop`客户端按提示登陆后克隆自己的项目，如下图：

![4]({{ '/styles/images/jekyll-config/4.png' | prepend: site.baseurl  }})

克隆到本地后是一个空白的文件夹：

![5]({{ '/styles/images/jekyll-config/5.png' | prepend: site.baseurl  }})

在空白文件夹内创建一个index.html文件，完成我们`GitHub-Pages`的第一个页面：

![6]({{ '/styles/images/jekyll-config/6.png' | prepend: site.baseurl  }})

然后在回到`GitHub Desktop`客户端中,点击提交到本地分枝`Commit`—>然后点击同步`Sync`或者`Publish`到`GitHub`远端就好啦，如下图:
![7]({{ '/styles/images/jekyll-config/7.png' | prepend: site.baseurl  }})

然后回到自己主页 如：`https://cs64188.github.io/` 就可以看到效果了！


===========================基础教程已结束=========================



附录：Jekyll本地调试和模版推荐
------------------------

上`http://jekyllthemes.org/`找一个自己喜欢的模板，本blog主页选了这个`http://jekyllthemes.org/themes/Less-Or-More/`主题，简介大方，我喜欢～
点下载下来以后，先解压缩，放在本地测试一下，打开命令行：

![8]({{ '/styles/images/jekyll-config/8.png' | prepend: site.baseurl  }})

进入到下载的模板下面，执行`jekyll server`：

![9]({{ '/styles/images/jekyll-config/9.png' | prepend: site.baseurl  }})

本地`Jekyll`启动了，地址`http://127.0.0.1:4000/` 在浏览器中输入，就可以看到效果,觉得OK的话把模板文件直接复制到自己的Git文件夹下面（之前自己创建`index.html`的文件的地方），然后在`GitHub`客户端上提交同步代码，提交完后回自己的主页就有效果啦 ~ （`GitHub`用的就是`Jekyll`服务器，所以发布后就可以直接看效果）

PS*:每个Jekyll的模板都有自己的编写规范，最基础的一定要在模板文件夹下面的_config.yml文件下修改相关配置，例如下图所示的事`Less-Or-More`的编写规范：
![10]({{ '/styles/images/jekyll-config/10.png' | prepend: site.baseurl  }})

每个模板都有自己的配置介绍，相对都写得比较简单易懂，自己再琢磨琢磨就行。

好好休息，程序员们 : )


