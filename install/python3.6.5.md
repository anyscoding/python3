既然python是一门这么好的编程语言，那就让我们开始我们的python3学习之旅吧

中国有句古话：“君欲善其事，必先利其器”，想要快乐的学习python，一整套的开发环境必不可少

今天是第一篇，讲解python3.6的安装

* 如果你以前没有接触过编程，那有极大的可能性你使用的是windows系列机器
* 如果你本就是一名程序员，很可能你用的是linux系列机器

本文只考虑这两种类型的机器

# windows
python官网提供了可执行文件版本工windows用户使用，非常方便

1. 从[下载地址](https://www.python.org/ftp/python/3.6.5/python-3.6.5-amd64.exe)下载“python-3.6.5-amd64.exe”
2. 双击“python-3.6.5-amd64.exe”按照提示安装
    1. 选择Custom Install，设置安装目录到C:\\Python365
    2. Advanced Options页面勾选“Add Python to environment variables”
    3. 其他默认
3. 启动命令行，输入：`python -V`，如果得到：`Python 3.6.5`表示安装完成

# linux
前面讲到过，linux默认安装了python，但发行版本不同安装的python版本也不同，我的“CentOS Linux release 7.3.1611 (Core)”就只安装了python2.7.5

1. 从[python tarball](https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz)下载：`wget https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz`
2. 解压tarball：`https://www.python.org/ftp/python/3.6.5/Python-3.6.5.tgz`
3. 配置：`cd Python-3.6.5/ && ./configure`
4. 安装：`sudo su - && make install`（在普通用户下用sudo make install报：`stdatomic.h: No such file or directory`，使用root用户安装没有报错）
5. 验证：`python3 -V`，返回：`Python 3.6.5`表示安装成功

好了，今天的内容就到这里！

