---
title: Hexo安装教程
tags: [Hexo,安装]
categories: Hexo
---

# **第一步：安装node.js**

node.js下载地址：http://nodejs.cn/download/  
找到自己系统对应的安装版本，下载安装。  
安装成功后，win+r：cmd进入控制台，进行测试  
```
        C:\Users\Administrator>node
        >console.log("Hello,Hexo!");
        Hello,Hexo!
```

至此，node.js安装成功。  
<!-- more -->

# **第二步：安装git**
1、申请Github帐号：https://github.com/join?source=header-home  
2、下载并安装git：https://git-scm.com/downloads/  
3、配置ssh：  
 - 打开git bash，设置user.name和user.email  
 -       git config \-\-global user.name "你的GitHub用户名"  
 -       git config \-\-global user.email "你的GitHub注册邮箱"

 - 生成ssh密匙
 -       ssh-keygen -t rsa -C "你的GitHub注册邮箱"
 - 此时会在.ssh中会出现密钥文件==id_rsa==和==id_rsa.pub==
  
4、将公钥添加到github上  
 - 用户头像→Settings→SSH and GPG keys→New SSH key→将id_rsa.pub中的内容复制到Key文本框中，然后点击Add SSH key(添加SSH)按钮。

# **第三步：安装Hexo**
- 更改npm源，防止默认镜像速度过慢
-       npm config set registry "https://registry.npm.taobao.org"

- 执行以下命令安装hexo。

        
```
        安装命令
        # 安装hexo
        npm install hexo-cli g
        # 初始化博客文件夹
        hexo init blog
        # 切换到该路径
        cd blog
        # 安装hexo的扩展插件
        npm install
        # 安装其它插件
        npm install hexo-server --save
        npm install hexo-admin --save
        npm install hexo-generator-archive --save
        npm install hexo-generator-feed --save
        npm install hexo-generator-search --save
        npm install hexo-generator-tag --save
        npm install hexo-deployer-git --save
        npm install hexo-generator-sitemap --save
```


# 初探hexo

        第一次使用hexo，在本地创建服务器使用。
        # 生成静态页面
        hexo generate
        # 开启本地服务器
        hexo s

打开浏览器，地址栏中输入：http://localhost:4000/,应该可以看见刚刚创建的博客了。
问题：为什么访问http://localhost:4000/，无反应？ 
解决方法：可能是由于端口问题引起的。使用Ctrl+C中断本地服务，使用命令hexo s -p 5000重新开启本地服务，访问http://localhost:5000/可以看到博客页面了。
将hexo博客部署到github上
