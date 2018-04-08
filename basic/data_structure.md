变量是用来存放数据的，python中的数据有多种类型：
* number
    * int
    * float
    * complex
* bool
* string
* list
* tuple
* set
* dict

除此之外，还可以定义自己的数据类型

python的数据有可变和不可变两种：
* 可变数据类型：
    * list
    * set
    * dict
* 不可变数据类型：
    * int
    * float
    * complex
    * bool
    * string
    * tuple

可变是指赋值给一个变量之后可以修改，并且不需要创建新的对象，辨别方法是：
```
my_obj = xxx
old_id = id(my_obj)
# modify my_obj
new_id = id(my_obj)

if old_id == new_id:
    print("可变")
else:
    print("不可变")
```

不同的数据类型，modify my_obj的方法不同：
* list：
```
clear()
append(item)
extend(other_list)
insert(index, item)
pop(index)
remove(item)
```
* set：
```
clear()
remove(item)
pop()
add(item)
union(Iterable[T])
update(Iterable[T])
```
* dict:
```
clear()
pop(k, default)
popitem()
update(Mapping(T(k), T(v)))
fromkeys(Iterable(keys), value)
setdefault(key, default)
```
* 其他类型只能重新赋值:
```
a = 1
a = 2
```
