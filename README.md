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
    不管是虚拟机还是双系统，牢记一定要装 ***英文*** 版本的系统。否则每次切换路径需要打汉字真的超痛苦的。而且中文输入法经常会干扰输入。

## Q：我应该装双系统还是虚拟机？
    看个人喜好吧，我个人用的是双系统，感觉有更纯净的工作体验。从Ubuntu是可以访问到windows里面的文件的。虚拟机感觉就，卡卡。
    这个就没有更多实质性的建议了。

## Q：我是Mac OS， 可以不用linux虚拟机双系统什么的吗
    理论上讲是可以的。我不是mac用户所以了解不太多。身边用mac的朋友给出了一点建议：
        > 直接用mac不好，因为mac和linux是不同的工具链（clang + lldb VS gcc + gdb）。
        > mac本身装虚拟机用户体验不怎么样。 「 这个好迷啊 」
        > 建议shell里用ssh去服务器上写程序。    「 这个得掌握editor的使用才行呢 」
    看起来最后还是没得出什么有用的结论呢_(:з」∠)_

## Q: 我还没想到有什么问题。。。

# **Survive in Linux**
这个Section主要是介绍一些常用命令吧。
- [一个传送门](https://mp.weixin.qq.com/s?__biz=MzI5ODExMDQzNw==&mid=2650738099&idx=2&sn=8d5ed9bcef6dec090fc832e2e3fb8b2a&chksm=f4a17139c3d6f82f7515a54241c8cbd9c1177a9a1401b96082f67240b2ae108ff84439dda3e3&mpshare=1&scene=1&srcid=0806mEjre9YBrTDH6B0WZyH6&pass_ticket=ZsWsrQ%2Bk3h8EWKThRRP1DCRUFgGtXgGsCMgkUeMm824a6HmvWX7Xjg8GWXjWcx1W#rd)

## 最最基础
1. bash是什么？

     就理解为是一个命令行/控制台就ok。我们绝大多数的事情都会在这里完成。
     
    ![bash](img/bash-example.png ''Bash'')
    
2. 开启bash和基本的使用
    - 快捷键： Ctrl + Alt + T 「 可以自己设置 」
    - 切换工作路径
