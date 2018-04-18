set，集合，在python比较常见
# 申明
set的申明很简单：
```
a = {1, 2, 3}

```

用```{}```括起来的多个元素，就是一个集合

*特别注意：集合中的元素，必须是hashable（可以简单的理解成不可变数据类型）的*

我们来看几个例子：

## hashable
```
a = {1, 1.2, 3+4j, True, "test", (1, 2)}

print(a)

```

运行结果是：
```
{(1, 2), 1, 1.2, (3+4j), 'test'}
```
上面的集合中元素的类型有：
* int
* float
* complex
* bool
* string
* tuple

## unhashable

我们在[数据结构概述](basic/data_structure.md)中讲过这些都是不可变数据类型，也就是hashable的，可以作为集合的元素，我们再来看看将可变数据类型放到集合中会发生什么

回顾一下，可变数据类型包括：
* set
* list
* dict

### unhashable：set

```
a = {1, 1.2, 3+4j, True, "test", (1, 2), {1, 2}}

print(a)

```

运行结果：

```
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 1, in <module>
    a = {1, 1.2, 3+4j, True, "test", (1, 2), {1, 2}}
TypeError: unhashable type: 'set'
```

提示我们：类型错误，unhashable类型set({1, 2})

### unhashable：list

```
a = {1, 1.2, 3+4j, True, "test", (1, 2), [1, 2]}

print(a)

```

运行结果：
```
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 1, in <module>
    a = {1, 1.2, 3+4j, True, "test", (1, 2), [1, 2]}
TypeError: unhashable type: 'list'
```

同样提示：类型错误，unhashable类型 list（[1, 2]）

### unhashable: dict

我们再来看看dict

```
a = {1, 1.2, 3+4j, True, "test", (1, 2), {"name": "Jack"}}

print(a)

```

运行结果：

```
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 1, in <module>
    a = {1, 1.2, 3+4j, True, "test", (1, 2), {"name": "Jack"}}
TypeError: unhashable type: 'dict'
```

同样提示：类型错误，unhashable类型dict({"name": "Jack"})


