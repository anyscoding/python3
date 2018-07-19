string，字符串，在任何编程语言中都很常用，属于不可变数据类型

# 申明

字符串的申明如下例：

```
a = "HelloWorld"

```

根据个人喜好，可以用```"HelloWorld"```或者```'HelloWorld'```，或者```"""HelloWorld"""```

如果你申明的字符串中包含```""```或者```''```，可以这样：

```
a = 'Tom say: "HelloWorld"'
b = "Jack say: 'HelloWorld'"

```

再看一个更复杂的：

```
complex_string = """HelloWorld
    Every programmer say HelloWorld to every program language
sometimes to frameworks
"""

print(complex_string)

```

运行结果：

```
HelloWorld
    Every programmer say HelloWorld to every program language
sometimes to frameworks
```

使用```""""""```申明字符串时，会完全按照原格式输出，包括换行、空格等

# 使用
## S.index(sub[, start[, end]]) -> int

说明： 在下标```start```和```end```之间，sub第一次出现的下标

**示例**：

```
a = "this is my first string"

my_index = a.index("my")

print(my_index)

```

**运行结果**：

```
8
```

**特别说明**：
* ```[, start[, end]]```表示可选参数，在调用该方法时，可以不传入。如果调用者不指定可选参数的值，就像上面的示例一样，默认```start = 0```， ```end = the length of string```
* 如果```sub```不在字符串中，则会报错，如下：
```
a = "this is my first string"

your_index = a.index("your")

print(your_index)

```

**运行结果**：

```
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 3, in <module>
    your_index = a.index("your")
ValueError: substring not found
```

## S.count(sub[, start[, end]]) -> int

说明： 在下标```start```，```end```之间，```sub```出现的次数

**示例**：

```
a = "this is my first string"

i_count = a.count("i")

print(i_count)

```

**运行结果**：

```
4
```

## S.format(*args, **kwargs) -> str

说明： 按照S指定的模板，返回填入参数后的字符串

讲起来有点抽象，我们来看一个例子：

```
a = "Hello, {}, my name is {}, I am {} years old"

formatted = a.format("Tom", "Jack", 20)

print(formatted)

```

**运行结果**：

```
Hello, Tom, my name is Jack, I am 20 years old
```

上面的方式，是将传入的参数，逐个填入```S```中```{}```的位置，不足的填入```""```，不容易控制，下面看看另外的一种方式：

```
a = "Hello, {your_name}, my name is {my_name}, I am {age} years old"

formatted = a.format(your_name="Jack", age=20, my_name="Tom")

print(formatted)

```

**运行结果**：

```
Hello, Jack, my name is Tom, I am 20 years old
```

还可以这样：

```
a = "Hello, {your_name}, my name is {my_name}, I am {age} years old"

data = {"your_name": "Jack", "my_name": "Tom", "age": 20}

formatted = a.format(**data)

print(formatted)

```

**运行结果**：

```
Hello, Jack, my name is Tom, I am 20 years old
```

这里暂时理解不了也不用担心，后续在讲函数或者方法的时候会有更加详细的解释

## S.title() -> str

说明： 返回```S```的标题格式（所有单词的首字母大写）

**示例**：

```
a = "Hello, Jack, my name is Tom, I am 20 years old"

title = a.title()

print(title)

```

**运行结果**：

```
Hello, Jack, My Name Is Tom, I Am 20 Years Old
```

## S.capitalize() -> str

说明： 返回```S```的首字母大写，其余字母小写形式

**示例**：

```
a = "Hello, Jack, my name is Tom, I am 20 years old"

capitalize = a.capitalize()

print(capitalize)

```

**运行结果**：

```
Hello, jack, my name is tom, i am 20 years old
```

## S.center(width[, fillchar]) -> str

说明： 返回一个原字符串居中,并使用空格填充至长度 width 的新字符串。默认填充字符为空格

**示例**：

```
a = "Center"

print(a.center(10))
print(a.center(10, "#"))

```

**运行结果**：

```
  Center  
##Center##
```

## S.encode(encoding='utf-8', errors='strict') -> bytes

说明： 按照```encoding```指定的编解码器将字符串S编码

**参数说明**：
* **encoding**： 编解码器，默认为```utf-8```，其他可能的值可以参考：[python standard encodings](https://docs.python.org/3/library/codecs.html#standard-encodings)
* **errors**： error handling scheme，默认是```strict```，其他可能的值可以参考[python encode error handlers](https://docs.python.org/3/library/codecs.html#error-handlers)

**示例**：

```
a = "Encode a string, utf-8, strict"

encoded = a.encode()

print(encoded)

```

**运行结果**：

```
b'Encode a string, utf-8, strict'
```

## S.endswith(suffix[, start[, end]]) -> bool

说明： 判断字符串S在```start```与```end```之间是否以特定的字符串```suffix```结尾

**参数说明**：
* **suffix**： 后缀，可以是字符串或者字符串的元组
* **start**: 可选参数，默认为0
* **end**: 可选参数，默认为字符串的长度

**示例**：

```
a = "Encode a string, utf-8, strict"
b = "Encode a string, utf-8, ignore"
c = "Encode a string, utf-8, replace"

resulta = a.endswith(("strict", "replace", "ignore"))
resultb = b.endswith(("strict", "replace", "ignore"))
resultc = c.endswith(("strict", "replace", "ignore"), 1, 8)

print(resulta, resultb, resultc)

```

**运行结果**：

```
True True False
```

## S.capitalize() -> str

说明： 将字符串首字母大写

**示例**：

```
print("this is a string".capitalize())
print("THIS IS A STRING".capitalize())

```

**运行结果**：

```
This is a string
This is a string
```

