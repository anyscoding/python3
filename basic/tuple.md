tuple，元组，在python中比较常见，因为其不可变的性质，使用起来简单了不少

# 申明
在python中可以通过如下方式申明一个元组
```
info = ("Jack", 26, "man")

```

一般情况下，元组就是用```()```括起来的两个或者更多的元素，括号是可选的，下面的方式跟上面的代码等价

```
info = "Jack", 26, "man"

```

元组中的元素可以是任意类型（元素类型可以不同，就像上面的代码第2个元素是int类型，另外两个是string）

# 不可变性质
在[数据结构概述](basic/data_structure.md)章节中我们说过tuple（元组）属于不可变类型，其实不完全正确，我们来看个例子

```
data = (1, 2, [1])

print("id: {}, data: {}".format(id(data), data))

data[2].append(2)
print("id: {}, data: {}".format(id(data), data))

```

运行结果如下：
```
id: 2083215131056, data: (1, 2, [1])
id: 2083215131056, data: (1, 2, [1, 2])

```

我们可以看到：id没有变化，但值已经改变了。严格来说，元组是不是可变类型取决于元素的类型，如果包含了可变类型的元素，元组就是“可变”的

# 常见用法
元组的操作很少，只有两个：
* T.count(value) -> integer -- return number of occurrences of value
* T.index(value, [start, [stop]]) -> integer -- return first index of value

下面是一组示例：
```
data = (1, 2, 3, 2, 1)

print("count of 1: {}".format(data.count(1)))
print("index of 2: {}".format(data.index(1)))

```

