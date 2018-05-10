列表在python中非常常用

# 申明

list的申明很简单：

```
a = [1, 2, 3]

```

用```[]```括起来的多个元素，就是一个列表，列表的元素可以是任意类型

# 修改
列表是可变数据类型，意味着我们可以直接修改一个对象，其id不会改变，我们一个一个来看

## L.append(object) -> None -- append object to end

说明：在列表尾部追加一个元素

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.append(4)
print(id(a), a)

```

**运行结果**：
```
1713134487176 [1, 2, 3]
1713134487176 [1, 2, 3, 4]
```

## L.clear() -> None -- remove all items from L

说明：清空列表中所有的元素

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.clear()
print(id(a), a)

```

**运行结果**：
```
1965631587976 [1, 2, 3]
1965631587976 []
```

## L.extend(iterable) -> None -- extend list by appending elements from the iterable

说明：将一个可迭代对象（列表、元组、字符串、字典等）的所有元素扩展到列表尾部

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.extend([4, 5])
print(id(a), a)

```

**运行结果**：

```
1660918482568 [1, 2, 3]
1660918482568 [1, 2, 3, 4, 5]
```

参数为list、tuple的比较容易理解，我们来看一个比较特殊的：参数为字符串和字典

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.extend("456")
print(id(a), a)
a.extend({"name": "Tom", "age": 26})
print(id(a), a)

```

**运行结果**：
```
2237471835592 [1, 2, 3]
2237471835592 [1, 2, 3, '4', '5', '6']
2237471835592 [1, 2, 3, '4', '5', '6', 'name', 'age']
```

从执行结果来看：
* 对于字符串的扩展，是将逐个将字符串中的字符添加到列表尾部
* 对于字典的扩展，是将字典的key逐个添加到列表的尾部

## L.insert(index, object) -- insert object before index

说明：在index前插入一个元素

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.insert(0, 0)
print(id(a), a)

```
**运行结果**：
```
1650031380104 [1, 2, 3]
1650031380104 [0, 1, 2, 3]
```

## L.remove(value) -> None -- remove first occurrence of value.

说明：从下标0开始，删除第一个等于value的元素，value不在列表中时报错

**示例**：
```
a = [1, 2, 2, 3]

print(id(a), a)
a.remove(2)
print(id(a), a)
a.remove(2)
print(id(a), a)
a.remove(2)

```

**运行结果**：
```
2394059687560 [1, 2, 2, 3]
2394059687560 [1, 2, 3]
2394059687560 [1, 3]

Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 8, in <module>
    a.remove(2)
ValueError: list.remove(x): x not in list
```

列表中有两个2，第一次remove掉掉index为1的，第二次remove剩下的那一个2，此时列表中元素```[1, 3]```，再一次remove(2)的时候，因为找不到```2```，报错

## L.pop([index]) -> item -- remove and return item at index (default last).

说明：弹出下标为index（可选参数，默认为最后一个元素的下标），当列表为空或者指定的index超出列表下标范围时报错```IndexError```

**示例**：
```
a = [1, 2]

print(id(a), a)
a.pop()
print(id(a), a)
a.pop(0)
print(id(a), a)
a.pop()

```

**运行结果**：
```
2232475305608 [1, 2]
2232475305608 [1]
2232475305608 []
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 8, in <module>
    a.pop()
IndexError: pop from empty list
```

从运行结果来看：
* 不传任何参数时，会弹出列表最后一个元素
* 对一个空列表执行pop操作，会报错```IndexError: pop from empty list```

再看另外一个示例：
```
a = [1, 2]

print(id(a), a)
a.pop(2)
print(id(a), a)

```

**运行结果**：
```
2777060460168 [1, 2]
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 4, in <module>
    a.pop(2)
IndexError: pop index out of range
```

从执行结果来看：
* 列表有两个元素，下标分别为：```0, 1```，我们pop下标为2的元素时，报错：```IndexError: pop index out of range```

## L.reverse() -- reverse *IN PLACE*

说明：将列表中的元素逆序排列

**示例**：
```
a = [1, 2, 3]

print(id(a), a)
a.reverse()
print(id(a), a)

```
**运行结果**：
```
1802482402952 [1, 2, 3]
1802482402952 [3, 2, 1]
```
## L.sort(key=None, reverse=False) -> None -- stable sort *IN PLACE*

说明：将列表中的元素排序

**示例**：
```
a = [1, 3, 5, 2, 4]

print(id(a), a)
a.sort()
print(id(a), a)

```

**运行结果**：
```
2823296763528 [1, 3, 5, 2, 4]
2823296763528 [1, 2, 3, 4, 5]
```

sort有两个参数，```key=None```和```reverse=False```，我们详细说明一下：
* reverse表示逆序，同样是上面的代码，把```a.sort()```修改为```a.sort(reverse=True)```后的执行结果变成了从大到小排列：
```
2346456041096 [1, 3, 5, 2, 4]
2346456041096 [5, 4, 3, 2, 1]
```
* key用来评估两个元素的大小关系。不管你是什么排序，必然要比较两个元素的大小来决定元素在排好序之后的列表中的位置


# 其他操作

## L.count(value) -> integer -- return number of occurrences of value

说明：列表中value的个数

**示例**：
```
a = [1, 2, 2, 3, 3, 3]

print(a.count(1))
print(a.count(2))
print(a.count(3))

```

**运行结果**：
```
1
2
3
```

## L.index(value, [start, [stop]]) -> integer -- return first index of value.

说明：从start下标到stop下标之间，value最早出现的下标

**示例**：
```
a = [1, 2, 3, 2, 3, 4]

print(a.index(1))
print(a.index(2, 2, 5))
```

**运行结果**：
```
0
3
```

这里有必要说明一下:
* 在很多编程语言中，在表示参数时，使用```L.index(value, [start, [stop]])```表明index方法至少需要一个参数：```value```，```start```,```stop```可选（在调用时可以不指定，```start```默认为0，```stop```默认为列表的最后一个元素）
* 在python中，下标是从0开始的，```a = [1, 2, 3]```，第0个元素是1, 第1个元素是2,......

我们再来看看另外一个特殊的例子：
**示例**：
```
a = [1, 2, 3]

print(a.index(5))

```

**运行结果**：
```
Traceback (most recent call last):
  File "D:/GitHub/HelloWorld/hello.py", line 3, in <module>
    print(a.index(5))
ValueError: 5 is not in list
```

**注意：当index的元素不在列表中时，会报错**
