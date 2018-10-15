在[3.3 python project的结构](basic/program_structure.md)中讲到什么是module

“python module：是一个文件，文件一般以.py结尾，文件中是python代码”

我们新建一个工程（一个目录），然后在目录中新建两个文件，如下：
```
hello---------
  `-- hello.py
  `-- main.py
```
在hello.py中编写如下代码：
```
def hello(name):
    return "hello, {}".format(name)

```
在main.py中编写如下代码：
```
import hello

print(hello.hello("Jack"))

```
我们运行main.py：```python main.py```得到如下结果：```hello, Jack```

上面的hello.py就是一个module，main.py也是module，但因为它仅仅提供入口，此处忽略不讲，我们重点来讲一讲hello.py

hello.py定义了一个函数：```hello(name) -> string```

在main.py中我们需要使用这个函数，于是我们引入hello这个module：```import hello```。module的名字不带.py后缀

当执行```import hello```时，python会从以下路径搜索```hello.py```的文件：
- 当前目录
- python lib（我的环境中是：C:\Python365\Lib）
- lib/site-packages（我的环境中是：C:\Python365\Lib\site-packages）

以上路径都没有，就会得到一个错误：```ModuleNotFoundError: No module named 'hello'```

我们再回到hello.py，module可以对外提供函数（hello(name) -> string），常，变量，类等等
