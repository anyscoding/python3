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

## L.count(value) -> integer -- return number of occurrences of value

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
