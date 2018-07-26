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

### D.copy() -> a shallow copy of D

说明：返回字典D的一个影子

**示例**：

```
d = {"name": "anys", "age": 29, "hobby": ["reading", "swimming"]}
d1 = d.copy()

d1["name"] = "Jack"
d1["hobby"].append("game")

print(d)
print(d1)

```

**运行结果**：

```
{'name': 'anys', 'age': 29, 'hobby': ['reading', 'swimming', 'game']}
{'name': 'Jack', 'age': 29, 'hobby': ['reading', 'swimming', 'game']}
```

**说明**：
* d1为d的拷贝
* 修改d1的```name```对应的值（字符串，不可变类型），d不会被修改
* 修改d1的```hobby```对于的值（列表，可变类型），则d也同时被修改

### D.pop(k, [default]) -> value

说明：从字典中弹出指定key的value，跟```D.get(k, [default])```不同的是：pop会在字典D中删除k

**参数说明**：
* **k**：key
* **default**：当k不在D中时，返回的值

**特别说明**：如果k不在D中，且没有设置default的值，将会返回错误：```KeyError: 'height'```

**示例**：

```
d = {"name": "anys", "age": 29, "hobby": ["reading", "swimming"]}
sex = d.pop("sex", "man")
hobby = d.pop("hobby")

print(sex)
print(hobby)

print(d)

```

**运行结果**：

```
man
['reading', 'swimming']
{'name': 'anys', 'age': 29}
```

### D.popitem() -> (k, v)

说明：删除并返回```(key, value)```对，如果D为空则出错，提示KeyError

**示例**：

```
d = {"name": "anys", "age": 29, "hobby": ["reading", "swimming"]}

k, v = d.popitem()

print(k, v)
print(d)

```

**运行结果**：

```
hobby ['reading', 'swimming']
{'name': 'anys', 'age': 29}
```

### D.clear() -> None.  Remove all items from D.

说明：清空D中的所有元素

**示例**：

```
d = {"name": "anys", "age": 29, "hobby": ["reading", "swimming"]}

d.clear()

print(d)

```

**运行结果**：

```
{}
```

### D.update([E, ]**F) -> None.  Update D from dict/iterable E and F

说明：更新字典D

**参数说明**：
* **E**：字典或者可迭代对象（每个元素是一个二元组，二元组的第一个元素作为key，第二个元素作为value）
* **F**：关键字参数，传入方式参考示例代码

**示例**：

```
d = {"name": "anys", "age": 29, "hobby": ["reading", "swimming"]}

d.update({"sex": "man"})
print(d)

d.update([("firstname", "an")])
print(d)

d.update(lastname="yushun")
print(d)

```

**运行结果**：

```
{'name': 'anys', 'age': 29, 'hobby': ['reading', 'swimming'], 'sex': 'man'}
{'name': 'anys', 'age': 29, 'hobby': ['reading', 'swimming'], 'sex': 'man', 'firstname': 'an'}
{'name': 'anys', 'age': 29, 'hobby': ['reading', 'swimming'], 'sex': 'man', 'firstname': 'an', 'lastname': 'yushun'}
```
