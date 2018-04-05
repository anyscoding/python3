在前面两篇文章中，我们准备了一套本地开发环境，这一篇我们讲解如何开始我们的python编程

在程序员的世界里，接触任何新鲜事物的时候，总是会很绅士的来个：“Hello World”。比如学习一门编程语言，要写一个“HelloWorld”，学习一个框架要写一个“HelloWorld”，可以说：“程序员写过的HelloWorld比你见过的软件还多”

我们今天使用前面安装的IDE，创建一个python项目，并编写python语言的“HelloWorld”

# 创建项目
## pycharm
pycharm创建项目：
1. File >> New Project...
2. 就会弹出：“Create Project”界面，需要填写一些参数
    1. Location: 项目保存的地址（D:\Workspace\HelloWorld）
    2. Interpreter: 解释器（python.exe的地址，例如：C:\Python365\python.exe）
3. 点击 Create 项目创建成功
4. 右键单击项目，New >> Python File
5. 填写Name: 文件名称（例如：hello），点击 OK 就会创建一个hello.py的文件（.py是python文件默认的后缀名）

## Eclipse
eclipse创建项目：
1. File >> New >> Project...
2. 就会弹出“New Project”界面，选择project类型，我们这里选择：PyDev Project
3. Next 然后输入Project Name（HelloWorld）
4. Finish完成PyDev项目创建
5. 右键单击项目， New >> PyDev Module（项目列表在最左侧，如果看不到，可能是折叠起来了，点击一下最左侧上方两个小方块就可以看到展开的项目列表了）
6. Create a new Python module 页面填写Name（hello），Source Folder默认，package不填
7. Finish完成创建

## vscode
vscode比较特殊，没有创建项目的选项，我们需要预先创建一个文件夹：D:\HelloWorld
1. 文件 >> 打开文件夹(F)...[Ctrl+K Ctrl+O]
2. 选择预先创建的文件夹（D:\HelloWorld）
3. 在左侧资源管理器中可以看到HelloWorld项目，鼠标移动到项目上回出现四个图标，点击第一个“创建文件”
4. 输入文件名：hello.py

# 编写HelloWorld
来来来，是时候编写我们的第一行python代码了：
```
print("Hello World!")

```

说好的一行呢？

写程序不难，但要写好程序，是需要花心思，一点一点雕琢的，从一开始就养成良好的习惯，写好程序的几率会大很多哦

在回到正题，说说为什么是两行，一般情况下，python都会以一个空行作为文件的结尾，有些IDE甚至会提醒你，这虽然不是什么错误，但记住养成良好的习惯，写好程序的几率会大很多哦

# 运行python
代码写好了，我要怎么执行我的程序呢？

这当然没有像启动QQ或者其他程序那么简单，不同的IDE有所不同（pycharm会自动保存代码，eclipse和vscode在执行代码前需要手动保存）

## pycharm
1. 在你编写代码的文件上右键单击，点击：“▶ Run 'hello'”
2. 在IDE的下方就可以看到执行结果
```
C:\Python365\python.exe D:/GitHub/HelloWorld/hello.py
Hello World!

Process finished with exit code 0
```

第一行：C:\Python365\python.exe D:/GitHub/HelloWorld/hello.py 是执行我们编写的代码的命令

第二行：Hello World! 是我们编写的代码的执行结果，打印“Hello World!”

第三行：Process finished with exit code 0 代码执行完成后的返回结果，一般情况下，返回0表示代码执行成功

## eclipse
1. 在你编写代码的文件上右键打击，点击：“Run As” >> “1 Python Run”
2. 在IDE下方可以看到执行结果，此处不再解释


## vscode
1. 在你编写代码的文件上右键单击，点击：“在终端中运行 Python 文件”
2. 在IDE的下方可以看到执行结果（跟pycharm略像，不再做过多解释）
```
PS D:\HelloWorld> & python d:/HelloWorld/hello.py
Hello World!
PS D:\HelloWorld>
```

从本篇文章以后，不会再介绍有关IDE的使用，我们把所有的经历放到python上来，加油吧
