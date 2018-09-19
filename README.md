# **Outline**
- Linux Installation
- Survive in Linux
- Introduction to VIM
- Introduction to git

## 一点废话：
    
写这个的目的大概是帮大家能快些上手Linux系统。学习一个新东西，最重要的还是思维模式上的转变。对于大部分人来说，可能之前接触的都是“图形界面+鼠标”的工作模式，但是linux不同。从ICS这门课开始，你们以后可能就要渐渐的接触“控制台+键盘”的工作模式。「其实也难说，想用鼠标+IDE还是完全没有问题的，而且在很多情况下也是很必要的」
对我个人而言，这是一个比较痛苦的过程，尤其是刚脱离图形界面，来到命令行的环境，就仿佛自己失去了左膀右臂。在慢慢学习对过程中也走了非常多的弯路，踩了非常多的坑。但是现在看来，放弃鼠标大概就是跳出舒适区，熟练之后反而发现不用鼠标工作效率更高了w
一不小心说远了，下面是一直以来总结的一点经验和踩的坑
1. 要加强英语阅读的能力！这个真的很重要
2. CSDN不总是靠谱！大概就是：“你有一个问题 - 你决定查CSDN解决 - 你现在有10个新问题了”。不可以迷信CSDN哦。
3. 有问题，问google！ Say NO to baidu
4. 在从网上看一些solution或者copy一些命令解决问题的时候一定尽力搞清楚每个指令是什么含义。这样能极大的减少未知错误的出现率。
    
也不多说了，下面的内容大家就按需自取吧

# **Linux Installation**
如果你是dalao，那就直接跳过这个吧。

对于初次接触linux的人，推荐装ubuntu —— 简单易上手 「16.04和18.04均可」

- [虚拟机安装传送门1](https://mp.weixin.qq.com/s?__biz=MzA4MTAzMzQ5NA==&mid=2650840685&idx=1&sn=3e6b24c1c3608a302281031fb0b18340&chksm=846f1e14b3189702d3ae2f5f95702bc6c17276e8d472a98bfbf698fc4c976efcac001eb4e836&mpshare=1&scene=1&srcid=0806062LXWoLrhXx3TDr0cGh&pass_ticket=ZsWsrQ%2Bk3h8EWKThRRP1DCRUFgGtXgGsCMgkUeMm824a6HmvWX7Xjg8GWXjWcx1W#rd)
- [虚拟机安装传送门2](https://mp.weixin.qq.com/s?__biz=MzA4MTAzMzQ5NA==&mid=2650840690&idx=1&sn=b8bb7e8251dff679ef215df5a0e7df2b&chksm=846f1e0bb318971da58c2629f8874282942796244ef2a8adb579bacd82494ca301d91818049c&mpshare=1&scene=1&srcid=0806SqKlbfdN7e6phdLVguAI&pass_ticket=ZsWsrQ%2Bk3h8EWKThRRP1DCRUFgGtXgGsCMgkUeMm824a6HmvWX7Xjg8GWXjWcx1W#rd)
- [双系统传送门](https://blog.csdn.net/MrGong_/article/details/76736276)

## TIPS
    不管是虚拟机还是双系统，牢记一定要装 ***英文*** 版本的系统。否则每次切换路径需要打汉字真的超痛苦的。
    还有就是中文输入法经常会干扰输入。

## Q：我应该装双系统还是虚拟机？
    看个人喜好吧，我个人用的是双系统，感觉有更纯净的工作体验。从Ubuntu是可以访问到windows里面的文件的。虚拟机感觉就，卡卡。
    这个就没有更多实质性的建议了。

## Q：我是Mac OS， 可以不用linux虚拟机双系统什么的吗
    理论上讲是可以的。我不是mac用户所以了解不太多。身边用mac的朋友给出了一点建议：
        > 直接用mac不好，因为mac和linux是不同的工具链（clang + lldb VS gcc + gdb）。
        > mac本身装虚拟机用户体验不怎么样。 「 这个好迷啊 」
        > 建议shell里用ssh去服务器上写程序。    「 这个得掌握editor的使用才行呢 」
    看起来最后还是没得出什么有用的结论呢_(:з」∠)_


# **Survive in Linux**
这个Section主要是介绍一些常用命令吧。
- [一个传送门](https://mp.weixin.qq.com/s?__biz=MzI5ODExMDQzNw==&mid=2650738099&idx=2&sn=8d5ed9bcef6dec090fc832e2e3fb8b2a&chksm=f4a17139c3d6f82f7515a54241c8cbd9c1177a9a1401b96082f67240b2ae108ff84439dda3e3&mpshare=1&scene=1&srcid=0806mEjre9YBrTDH6B0WZyH6&pass_ticket=ZsWsrQ%2Bk3h8EWKThRRP1DCRUFgGtXgGsCMgkUeMm824a6HmvWX7Xjg8GWXjWcx1W#rd)

## 最最基础
0. 一些固定写法
    
    命令名称 <必须参数> 固定参数 [可选参数] 
    
    尖括号里一般是必须的参数 方括号里一般是可有可无的参数

1. bash是什么？

     就理解为是一个命令行/控制台就ok。我们绝大多数的事情都会在这里完成。
     
    ![bash的样子](https://github.com/IcsMaterials/Introduction/blob/master/imgs/bash-example.png)
    
2. 开启bash和基本的使用
    - 快捷键： <code> Ctrl + Alt + T </code>「 可以自己设置 」
    - 切换工作路径：<code >cd \[dir\]*</code>
    - 显示当前目录下面有什么： <code>ls \[dir\]</code>
    - 新建文件夹： <code>mkdir \<dirname\></code>
    - 删除东西： <code>rm [-rf] \<fileORdir...\></code>
        - 参数 -r 表示删除文件夹
        - 参数 -f 表示强制删除
    - 复制： <code>cp \<from\> \<to\></code>
    - 剪切/重命名：<code> mv \<from\> \<to\> </code>
    - 查看帮助信息： <code> man <想要查看的指令> </code>
        - 除了 man 以外， 绝大部分情况下还可以使用 “指令 --help” 或者 “指令 -h” 来查看帮助信息。 如 <code> ls --help </code>
        - **学会查看帮助文档是很重要的技能！！！**

3. 文本操作

    文本操作分为两种 —— 命令行中的直接操作、图形界面的操作。

    图形界面的话有很多app可以用，如gedit（系统自带）、sublimeText、vsCode等。
    而命令行中的文本编辑器主要就是vim和emacs。

    gedit是系统自带的文本编辑器，支持给代码上色，什么文件都能开，轻量好用。

    sublimeText是以前很多学长学姐推荐用来在linux环境下写代码的，对于习惯了windows和mac下用IDE的同学们来说，这个还是很友好的。

    vsCode是我个人比较推荐的一个编辑器。熟悉windows环境的同学肯定对和它关系很近的visual studio不陌生。这个编辑器有非常方便的插件管理，功能强大，而且比visual studio要轻量得多。（这篇文就是用vscode写成的hhhh） 大家慢慢的就会明白插件的重要性了！很多插件真的很好用！

    至于命令行中的编辑器，emacs我没用过，vim在后面单独开一章写。

4. 安装新的程序

    这一部分的内容我就以基于Debian的Ubuntu为例。如果是CentOS之类的系统有类似的东西，但是就不过多在这说了。所以下文的linux大家自动认为是ubuntu就好啦x

    很多同学刚接触linux的时候都会很困惑——我安装的程序都去哪里了？ 不像windows中大部分程序都有一个安装包，然后自己指定安装路径，安装完成以后那个exe文件就安静的躺在了路径下面——ubuntu有一个非常方便的包管理器：apt

    想要安装新程序，很简单，一句话就能完成
    > <code >sudo apt install <想要装的东西...></code>

    注：sudo 是作为“超级用户”用户运行的意思。具体起到什么效果大家可以去搜搜，很简单。 下面是一个示例
    > <code>sudo apt install gcc cmake libclang-6.0-dev</code>

    注：上面一行命令安装了gcc、cmake和libclang6的库，也即一次可以安装很多东西。

    除了install以外 apt还支持很多其他命令,如apt list、apt search、apt update、apt upgrade等等，都有不同的用处。具体大家可以 **man apt** 或者百度apt来查看。

    > #### Q: apt装完了的程序去了哪里啊？
    >> #### A：这是由系统决定的，如果是可执行的程序如gcc，cmake等一般是装在 /usr/bin/ 里面， 如果是库文件和一些头文件(如上面的libclang)，则是在 /usr/lib/ 和 /usr/include/ 路径下
    > #### Q: 想要卸载包怎么办？找不到要安装的包的名字怎么办？
    >> #### A: 卸载的话就 <code>sudo apt remove ...</code> ; 想要搜索包的话可以用 <code>apt search <想找的名字></code> 支持模糊搜索。
    > #### Q: 我的apt下载安装程序好慢怎么办啊?
    >> #### A: 可以给apt换下载源，用隔壁的源非常快。 可以使用命令 <code>sudo apt edit-sources</code> 或者 sudo vim /etc/sources.list 来修改。 具体怎么改可以去百度啦。 **改完以后记得运行 <code>sudo apt update</code> 和 <code>sudo apt upgrade</code>**
    >> ### 另外 系统刚装好的时候也要sudo apt update和sudo apt upgrade一下

# Introduction to VIM
为什么我一直这么安利vim？因为高效呀！

vim是linux自带的编辑器，打开控制台，输入vim，就可以开始使用了！熟练的使用vim可以让你告别鼠标操作，双手不离开键盘。不仅仅是写程序，而且包括debug、操作文件、运行程序等等一切操作。这对干活的效率是极大的提升。（但是需要一段时间的适应）

>vim有自动补全！vim有自动补全！vim有自动补全！

重要的事情说三遍！（插件名字叫YouCompleteMe）

去年我身边的很多同学就是因为linux下没有顺手的自动补全，最后不得不回到了windows里写程序，写完拷贝到linux下面编译运行再debug。真的是令人头秃。之后lab的程序越来越长，自动补全的作用就越来越大。

但是vim的学习历程也不是那么简单的，它需要非常长的时间来适应，用的越久，写代码的效率越高。

下面分享几个关于vim使用的推送吧，是从隔壁偷来的一个初步简单介绍。
- [第一部分](https://mp.weixin.qq.com/s/X4MKTIx18QMhyq2Pi59Ydw)
- [第二部分](https://mp.weixin.qq.com/s/00STAsmcZVPQ_AZMKUwWJw)
- [第三部分](https://mp.weixin.qq.com/s/2Jyk7sTjbgEM8B-A0911sg)

关于vim的使用和自动补全的插件安装，我之后应该会另外写~



# Introduction to Git
相信已经有一部分同学了解git的用法啦。

Git是一个开源的分布式版本控制系统。听起来很高级，也有很多高级的运用。不过对于现在的大家来说，可以把git当作一个很方便的“网盘”来使用。

这里的内容仅仅是快速入门，很多细节还需要去看官方文档

## 安装和初始化配置 git
很简单 只需要控制台运行
> <code> sudo apt install git </code>

之后就可以 <code>git --help</code> 查看简单介绍。安装完了以后就要设置基本信息了。没有账号同学们可以去github注册一个账号，然后回来控制台运行
> <code>git config --global user.name "你的用户名" <p>
> git config --global user.email "你注册的邮箱" <p>
> git config --global core.editor vim <p></code>

这样子你本地的vim就知道你是谁了，之后就可以开始正常使用了。

## 基本使用：clone pull 获取远程仓库
关于git clone，用法非常直接，大家可以直接尝试
> <code> git clone https://github.com/IcsMaterials/Introduction </code>

这样就直接把远程的仓库(repository)给复制到了本地。

而git pull的作用就是让你本地的仓库和远程的进行同步，获取远程的更新。

## 基本使用：init status 查看本地仓库状态
对于一个不是git仓库的文件夹，可以使用如下指令初始化一个仓库
> <code> mkdir tempgit <p> cd tempgit <p> git init </code>

而git status的作用则是查看当前仓库的状态，对于一个没做过修改的仓库，效果像下图所示

![git status](https://github.com/IcsMaterials/Introduction/blob/master/imgs/gitSstatus.JPG)

## 基本使用：add commit
在git仓库里面新加入了文件以后，需要通过git add 和 git commit来保存修改，并且留下关于修改的信息。
> <code> git status #显示当前信息 <p> git add temp.txt #添加temp.txt <p> git status #再次显示信息 <p> git commit #保存修改到本地，留下修改信息 </code>

下面是效果图：
![第一次git status](https://github.com/IcsMaterials/Introduction/blob/master/imgs/gitStatus2.JPG)
![git add之后的status](https://github.com/IcsMaterials/Introduction/blob/master/imgs/gitStatus3.JPG)
![git commit界面](https://github.com/IcsMaterials/Introduction/blob/master/imgs/gitCommit.JPG)

## 基本使用：remote push
自己初始化的仓库并没有和远程的仓库链接起来，而git remote这个命令就是负责链接本地和远程仓库。 链接上了远程仓库以后，就可以在commit完成之后通过git push来更新远程仓库。
- 注 远程仓库需要自己在github中建立。在GitHub中建了仓库之后，就可以看到相关的remote和push指令的用法。

一般情况下的使用就是
> <code> git remote add origin \<url\> <p> git push -u origin master </code>


