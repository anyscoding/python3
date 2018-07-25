dict，字典，在python常用。属于可变数据类型
# 申明

dict的申明如下：

```
d1 = {}
d2 = dict()
d3 = {"key": "value"}
print(d1, d2, d3)

```

有三种申明方式：
* ```{}```申明没有任何key的字典
* ```dict()```申明没有任何key的字典
* ```{"key": "value"}```申明包含key：```key```，且对应value为：```value```

# 使用
## 查询
### D.items() -> a set-like object providing a view on D's items

说明：返回字典的所有元素，返回结果类似列表，列表的每个元素是元组，元组的第一个元素是key，第二个元素是value。一般结合for使用

**示例**：

```
d = {"name": "anys", "age": 29}
print(d.items())

```

**运行结果**：

```
dict_items([('name', 'anys'), ('age', 29)])
```

### D.keys() -> a set-like object providing a view on D's keys

说明：返回字典的所有key，返回结果类似列表，列表的每个元素为字典的key

**示例**：

```
d = {"name": "anys", "age": 29}
print(d.keys())

```

**运行结果**：

```
dict_keys(['name', 'age'])
```

### D.values() -> an object providing a view on D's values

说明：返回字典的所有value，返回结果类似列表，列表的每个元素为字典的value

**示例**：

```
d = {"name": "anys", "age": 29}
print(d.values())

```

**运行结果**：

```
dict_values(['anys', 29])
```

### D.get(k, default=None) -> value

说明：返回字典中指定key的value，如果不存在则返回default指定的值

**参数说明**：
* **k**：key
* **default**：指定的k不在字典中时，返回的默认值。默认为None

**示例**：

```
d = {"name": "anys", "age": 29}
print(d.get("name"))
print(d.get("height"))
print(d.get("height", 175))

```

**运行结果**：

```
anys
None
175

```

## 修改
### D.setdefault(k[,d]) -> D.get(k,d), also set D[k]=d if k not in D

说明： 如果字典D中没有k，则设置D[k] = d，否则不做任何修改

**参数说明**：
* **k**： key
* **d**： default value，默认为None

**示例**：

```
d = {"name": "anys", "age": 29}

d.setdefault("sex")
d.setdefault("height", 175)

print(d)

```

**运行结果**：

```
{'name': 'anys', 'age': 29, 'sex': None, 'height': 175}
```

### D.fromkeys(keys, value) -> dict

说明： 返回一个新的字典，字典的key来自可迭代对象keys，value全部设置为value

**参数说明**：
* **keys**：字典所有的key
* **value**：所有key对应的value，默认为None

**示例**：

```
d = {}.fromkeys(["name", "age", "sex"])
d1 = {}.fromkeys(["name", "age", "sex"], "not set")

print(d)
print(d1)

```

**运行结果**：

```
{'name': None, 'age': None, 'sex': None}
{'name': 'not set', 'age': 'not set', 'sex': 'not set'}
```

