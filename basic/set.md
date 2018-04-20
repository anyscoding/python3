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

# 修改集合

与不可变的数据类型（例如：元组、数字）相比，可以对可变数据类型进行修改，我们一起看看集合的使用

## set.update(set, *s:Iterable[TypeVar('_T')])

更新集合，看个例子：

```
a = {1, 2}
print(a)

a.update([3, 4])
print(a)

```

运行结果：
```
{1, 2}
{1, 2, 3, 4}
```

*```*s:Iterable[TypeVar('_T')]```是指可迭代对象，例如：元组、集合、列表，这些油多个元素组成的对象*

## set.clear(set)
情况集合中的元素

```
a = {1, 2}
print(a)

a.clear()
print(a)
```

运行结果：

```
{1, 2}
set()
```

*```set()```表示没有任何元素的空集合*

## set.pop(set)
弹出一个元素

```
a = {1, 2, 3}
print(a)

a.pop()
print(a)

a.pop()
print(a)
```

运行结果：

```
{1, 2, 3}
{2, 3}
{3}
```

如果我们一直对一个集合执行pop操作，集合为空，继续执行pop操作，会发生什么呢？

```
a = {1}
print(a)

a.pop()
print(a)

a.pop()
print(a)

```

运行结果：

```
{1}
set()
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 7, in <module>
    a.pop()
KeyError: 'pop from an empty set'
```

**注意：当对一个空集合执行pop操作时，会报错：KeyError: 'pop from an empty set'**

## set.remove(set, element:TypeVar('_T'))

移除一个元素

```
a = {1, 2, 3}
print(a)

a.remove(3)
print(a)

```

运行结果：

```
{1, 2, 3}
{1, 2}
```

我们来看一个特别的例子：移除一个集合中不存在的元素，会发生什么：

```
a = {1, 2, 3}
print(a)

a.remove(4)
print(a)

```

运行结果：

```
{1, 2, 3}
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 4, in <module>
    a.remove(4)
KeyError: 4
```

**注意：当试图从集合中移除一个不存在的元素时，会报错```KeyError```**

## set.add(set, element:TypeVar('_T'))

往集合中添加一个元素

```
a = {1, 2, 3}
print(a)

a.add(4)
print(a)

```

运行结果：

```
{1, 2, 3}
{1, 2, 3, 4}
```

尝试一下，如果我们添加的是一个可变数据类型，会发生什么？

```
a = {1, 2, 3}
print(a)

a.add([3, 4])
print(a)

```

运行结果：

```
{1, 2, 3}
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 4, in <module>
    a.add([3, 4])
TypeError: unhashable type: 'list'
```

**注意：当往集合中添加可变数据类型（unhashable）时，会报错：TypeError: unhashable type: '你的数据类型'**

## set.union(set, *s:Iterable[TypeVar('_T')]) -> set

求并集

```
a = {1, 2, 3}
print(a)

b = a.union({1, 2, 4})
print(b)

```

运行结果：

```
{1, 2, 3}
{1, 2, 3, 4}
```

**这里需要注意：```set.union()```会将计算得到的并集以返回值的方式给调用者，所以需要使用一个变量来得到并集，```b = a.union({1, 2, 4})```**

