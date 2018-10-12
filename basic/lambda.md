某些时候，你懒得写一个函数，但也不想写成多个平铺的语句，那就轮到lambda函数上场了

在python中lambda可以定义一个匿名函数

定义语法：
```
lambda args: function body here
```

看个示例：
```
add = lambda x, y: x+y
print(add(1,2))
```

上面的例子定义了一个lambda函数并赋值给了变量add，这个lambda函数接收两个参数，返回两个参数的和

上面的```add = lambda x, y: x+y```等价于下面的函数定义：
```
def add(x, y):
    return x+y
```
