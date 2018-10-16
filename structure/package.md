在[3.3 python project的结构](../basic/program_structure.md)中讲到什么是package

python package： 是一个文件夹，文件夹中包含一个__init__.py，任意数量的.py文件。一般会将相关性很强的多个.py文件放到一起组成一个package

我们来创建一个工程：
```
test
  `-- say
  `    `-- __init__.py
  `    `-- hello.py
  `    `-- bye.py
  `-- main.py
```

代码如下：
- ```main.py```
```
import say

print(say.hello.someone("Jack"))
print(say.bye.someone("Jack"))

```
- ```say/__init__.py```
```
from . import hello
from . import bye

```
- ```say/hello.py```
```
def someone(name):
    return "Hello, {}".format(name)

```
- ```say/bye.py```
```
def someone(name):
    return "Bye, {}".format(name)

```

我们来运行main.py：
```
>python main.py
Hello, Jack
Bye, Jack
```

这里的say就是一个package

我们可以在一个package中包含多个module

一般情况下```__init__.py```为空，这时如果要使用package中的module，import方式如下：
```
from say import hello

print(hello.someone("Jack"))

```
