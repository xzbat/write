---
title: 利用hexo+github搭建属于你的极客范博客
date: 2018-04-29 20:20:49
tags: 博客搭建基础篇
---



> ### 想写博客？又不想用前篇一律的简书之类？那就仔细阅读本篇，搭建一个属于自己的博客吧
>
> ### 注：网上类似教程其实很多，对于程序员其实没啥难度，但一些刚学计算机的同学，或者极客爱好者，涉及到代码，node.js之类其实还是有点难度的，所以本文旨在用最小白化的文字来帮助大家避开搭建时的雷区。因此本文只教你某个东西怎么用，不会告诉你它是什么，更不会深究它的原理，感兴趣的同学可以自行google，说不定可以为你打开前端工程师的大门呦。

###  

### 一：准备工作：

1. 安装Node.js和配置好Node.js环境(你可以就简单的理解为要先装一个软件就好了，直接去官网下载安装包，选择默认安装设置即可)

   配置好之后，打开cmd命令行，以此输入

   `node -v`

   `npm -v`

   如果能返回版本号，即代表配置完成。

2. 安装Git和配置好Git环境

   这个安装成功的标志不用打开啥命令行，因为在桌面右击鼠标，会出现

   `Git GUI Here`

   `Git Bash Here`

   这两个选项

3. 注册github账号和新建一个库，库的名称应该为：你的账户名.github.io

   ### 二:hexo相关：

   新建一个文件夹，最好为英文，避免不必要的麻烦，在该文件夹外面空白处右击鼠标，打开
   `Git Bash Here`

   然后在出现的终端里（也就是黑框框）依此输入一下代码（因为有的命令涉及从远程安装东西，因此切记每次打完一句都耐心等待一段时间，再操作！

   `npm install hexo -g`    //开始安装Hexo

   `hexo init`   //初始化该文件夹，如果看到

   `Start blogging with Hexo！`  那就离成功又进了一步

   `npm install`  //安装所需要的组件

   `hexo g` 

   `hexo s`  //开启服务器，访问网址（这里只能通过localhost访问，是因为还没和github的库关联起来，接下来我们看有关github的操作）z

   ### 三：将hexo与github关联起来

   1. 设置git的user name和email

   ​     `  git config  --global user.name  "your name"`//"your name"应该改成你注册github时的  昵称

   ​      `git config --global user.email "your emali"`//"your email"应该改成你注册github时留下的邮箱

   ​

   1. 为github添加本机 SSH keys

      - 重新在桌面右击鼠标打开git bash

        `ssh-keygen -t rsa -C "youremail@example.com"` //你懂的，如上文所说，有些代码是需要你改的，每个人都不一样

      - 去c盘的user目录下找到.ssh目录，打开其子目录id_rsa.pub，这其实是一个公钥，将其内容复制下来，去github中找到"settings",然后找到"SSH and GPG keys",粘贴并保存下来，记得备注电脑名字，以防以后有多台电脑使用github账号的需求。

   2. 配置Deployment，在你最开始新建的父文件夹中，找到_config.yml文件，修改repo值（在末尾

      `deploy:`
        `type: git`
        `repository: git@github.com:your name/your name.github.io.git`  //同样的，你需要修改一些属于你的代码
       ` branch: master`

   3. `hexo new post “博客名”`  //新建一篇博客

   4. `npm install hexo-deployer-git --save`  //在生成以及部署文章之前，需要安装一个扩展

   5. 在子文件夹_posts目录下会看到你刚刚已经创建的文件，修改写完之后，两行代码生成部署一下就可以了

      `hexo g`

      `hexo d`

   ### 提醒：

   1. ### 你应该像个linux程序员那样不要使用中文命名文件夹

   2. ### 你应该像个前端程序员那样不要在文件夹命名中使用空格

   3. ### 你应该像所有程序员那样，在英文输入法下输入所有代码。

   4. ### 如果各位看官愿意给出你的小赞赞，小评论，小关注。我下次再出一篇进阶教程，深度美化和为自己的博客增加诸如评论，浏览量等更多功能呦：）

   ​

   ## happy ending!

   ​