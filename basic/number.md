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
讲bytes转换为int，跟to_bytes互逆，参数说明：
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
