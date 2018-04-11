python中的数字包括：
* int
* float
* complex

# int
python中的int没有位数（8位、16位、32位、64位等）的限制，可以无限大

```
a = 123456789012345678901234567890123456789012345678901234546787909123546578789023344546578798
```

int数据类型有几个方法

## bit_length() -> int
计算一个int数据的位数(bits)

```
a = 100
print(a.bit_length())
```

运行结果：
```
7
```

## to_bytes(length, byteorder, *, signed=False) -> bytes
将一个整数转换为bytes，参数说明：
* length，目标bytes数
* byteorder
    * big
    * little
    * default is sys.byteorder(后续会详细讲)
* signed，默认False，无符号

```
a = 1000
print(a.to_bytes(2, "little"))
```

运行结果：
```
b'\xe8\x03'
```

## int.from_bytes(bytes, byteorder, *, signed=False) -> int
将bytes转换为int，跟to_bytes互逆，参数说明：
* bytes，to_bytes的输出结果?
* byteorder，同to_bytes
* signed，同to_bytes

```
print(int.from_bytes(b'd', "little"))
```

运行结果：
```
100
```

# float
同样地，python中的float没有位数限制，可以无限大
```
f = 13454678909937823445678909543457678789809086454656789097689.0
print(f)
```
运行结果
```
1.3454678909937823e+58
```
float也有几个方法，我们来看一下

## float.as_integer_ratio() -> (int, int)
将float转换成分数表示，来看个例子
```
f = 0.25
print(f.as_integer_ratio())

f = 0.66
print(f.as_integer_ratio())

```
运行结果
```
(1, 4)
(5944751508129055, 9007199254740992)
```
第一个结果1/4无可厚非，第二个结果有些出人意料，这跟它的实现有关

## float.hex() -> string
float的十六进制表示
```
f = 0.25
print(f.hex())
```
运行结果
```
0x1.0000000000000p-2
```

## float.fromhex(string) -> float
float.fromhex(string) -> float跟float.hex() -> string互逆
```
print(float.fromhex("0x1.0000000000000p-2"))
```
运行结果
```
0.25
```

## float.is_integer() -> bool
判断一个float是否为整数
```
f = 0.25
print(f.is_integer())

f = 1.0
print(f.is_integer())
```
运行结果
```
False
True
```

# complex
复数在大多数程序员的工作中，并不会被使用，本文只做最简单的介绍

复数的定义方法
```
c = 1+3j
```
## complex.conjugate() -> complex
[共轭复数](https://baike.baidu.com/item/%E5%85%B1%E8%BD%AD%E5%A4%8D%E6%95%B0)，示例
```
c = 1+3j
print(c.conjugate())
```
运行结果
```
(1-3j)
```

除此之外，复数还有两个属性：
* real，实部
* imag，虚部

示例
```
c = 1+3j
print(c.real)
print(c.imag)

```
运行结果
```
1.0
3.0
```

关于python中的数字，就讲到这里
