# Python 标准库数据结构的基本用法

Python不需要声明变量类型，这是因为像 C 语言和 Java 语言来说，它们是静态的，而 python 是动态的，变量的类型由赋予它的值来决定。

Python内置了基本的数据结构类型，如list，tuple，dict，set，而collections模块包含了几种常见的数据结构。Deque是一个双端队列，可以快速地在队列两端插入和删除元素。defaultdict扩展了dict，当访问的key不存在时，返回一个默认值，而不是抛出异常。OrderedDict会记住元素加入进来的顺序		

## 基本的数据类型

（引用网站https://www.runoob.com/python3/python3-data-type.html）：

- **不可变数据（3 个）：**Number（数字）、String（字符串）、Tuple（元组）；
- **可变数据（3 个）：**List（列表）、Dictionary（字典）、Set（集合）。

### Number（数字）

Python3 支持 **int、float、bool、complex（复数）**。

在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。

```python
>>> a, b, c, d = 20, 5.5, True, 4+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
```

当你指定一个值时，Number 对象就会被创建：

```
var1 = 1
var2 = 10
```

#### 数值运算实例

\>>> 5 + 4 # 加法
9
\>>> 4.3 - 2 # 减法
2.3
\>>> 3 * 7 # 乘法
21
\>>> 2 / 4 # 除法，得到一个浮点数
0.5
\>>> 2 // 4 # 除法，得到一个整数
0
\>>> 17 % 3 # 取余
2
\>>> 2 ** 5 # 乘方
32

**注意：**

- 1、Python可以同时为多个变量赋值，如a, b = 1, 2。
- 2、一个变量可以通过赋值指向不同类型的对象。
- 3、数值的除法包含两个运算符：**/** 返回一个浮点数，**//** 返回一个整数。
- 4、在混合计算时，Python会把整型转换成为浮点数。

Python 还支持复数，复数由实数部分和虚数部分构成，可以用 **a + bj**，或者 **complex(a,b)** 表示， 复数的实部 **a** 和虚部 **b** 都是**浮点型**。

#### 扩展（类型判断&布尔&del）

##### 类型判断

可以用 isinstance 来判断：

\>>> a = 111
\>>> isinstance(a, int)
True
\>>>

isinstance 和 type 的区别在于：

- type()不会认为子类是一种父类类型。
- isinstance()会认为**子类是一种父类类型**。

```
>>> class A:
...     pass
... 
>>> class B(A):
...     pass
... 
>>> isinstance(A(), A)
True
>>> type(A()) == A 
True
>>> isinstance(B(), A)
True
>>> type(B()) == A
False
```

##### bool

注意：**Python3 中，bool 是 int 的子类，True 和 False 可以和数字相加， **True==1、False==0** 会返回 **True**，但可以通过 **is** 来判断类型。

```
>>> issubclass(bool, int) 
True
>>> True==1
True
>>> False==0
True
>>> True+1
2
>>> False+1
1
>>> 1 is True
False
>>> 0 is False
False
```

在 Python2 中是没有布尔型的，它用数字 0 表示 False，用 1 表示 True。

##### del

可以使用del语句删除一些对象引用。

del语句的语法是：

```
del var1[,var2[,var3[....,varN]]]
```

您可以通过使用del语句删除单个或多个对象。例如：

```
del var
del var_a, var_b
```

### String（字符串）

Python中的字符串用单引号 **'** 或双引号 **"** 括起来，同时使用反斜杠 `\` 转义特殊字符。

字符串的截取的语法格式如下：

```
变量[头下标:尾下标]
```

索引值以 0 为开始值，-1 为从末尾的开始位置。

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/123456-20200923-1.svg)

加号 **+** 是字符串的连接符， 星号 ***** 表示复制当前字符串，与之结合的数字为复制的次数。实例如下：

```python
#!/usr/bin/python3

str = 'Runoob' # 定义一个字符串变量

print(str)      # 打印整个字符串
print(str[0:-1])   # 打印字符串第一个到倒数第二个字符（不包含倒数第一个字符）
print(str[0])     # 打印字符串的第一个字符
print(str[2:5])    # 打印字符串第三到第五个字符（包含第五个字符）
print(str[2:])    # 打印字符串从第三个字符开始到末尾
print(str * 2)    # 打印字符串两次
print(str + "TEST") # 打印字符串和"TEST"拼接在一起
```

执行以上程序会输出如下结果：

```
Runoob
Runoo
R
noo
noob
RunoobRunoob
RunoobTEST
```

Python 使用反斜杠 \ 转义特殊字符，如果你不想让反斜杠发生转义，可以在字符串前面添加一个 **r**，表示原始字符串：

\>>> **print**('Ru**\n**oob')
Ru
oob
\>>> **print**(r'Ru**\n**oob')
Ru\noob

另外，反斜杠(`\`)可以作为续行符，表示下一行是上一行的延续（较少行建议使用）。也可以使用 **"""..."""** 或者 **'''...'''** 跨越多行（多行时使用）。

注意，Python 没有单独的字符类型，一个字符就是长度为1的字符串。

\>>> word = 'Python'
\>>> **print**(word[0], word[5])
P n
\>>> **print**(word[-1], word[-6])
n P

与 C 字符串不同的是，Python 字符串不能被改变。**向一个索引位置赋值，比如 word[0] = 'm' 会导致错误**。（可以用list()变成list)

**注意：**

- 1、反斜杠可以用来转义，使用r可以让反斜杠不发生转义。
- 2、字符串可以用+运算符连接在一起，用*运算符重复。
- 3、Python中的字符串有两种索引方式，从左往右以0开始，从右往左以-1开始。
- 4、Python中的字符串不能改变。

### List（列表）

List（列表） 是 Python 中使用最频繁的数据类型。

>  (列表（list）数据结构的底层实现是动态数组（Dynamic Array）)

列表可以完成大多数集合类的数据结构实现（队列、栈）。列表中元素的类型可以**不相同**，它支持数字，字符串甚至可以包含列表（所谓嵌套）。

列表是写在方括号 **[]** 之间、用逗号分隔开的元素列表。

和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的**新列表**。

列表截取的语法格式如下：

```
变量[头下标:尾下标]
```

索引值以 **0** 为开始值，**-1** 为从末尾的开始位置。

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/list_slicing1_new1.png)

加号 **+** 是列表连接运算符，**星号 * 是重复操作**。如下实例：

list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ] # 定义一个列表
tinylist = [123, 'runoob']

**print** (list)       # 打印整个列表
**print** (list[0])     # 打印列表的第一个元素
**print** (list[1:3])    # 打印列表第二到第三个元素（不包含第三个元素）
**print** (list[2:])     # 打印列表从第三个元素开始到末尾
**print** (tinylist * 2)   # 打印tinylist列表两次
**print** (list + tinylist) # 打印两个列表拼接在一起的结果

以上实例输出结果：

```
['abcd', 786, 2.23, 'runoob', 70.2]
abcd
[786, 2.23]
[2.23, 'runoob', 70.2]
[123, 'runoob', 123, 'runoob']
['abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob']
```

与Python字符串不一样的是，列表中的元素是可以改变的：

\>>> a = [1, 2, 3, 4, 5, 6]
\>>> a[0] = 9
\>>> a[2:5] = [13, 14, 15]
\>>> a
[9, 2, 13, 14, 15, 6]
\>>> a[2:5] = []  # 将对应的元素值设置为 []
\>>> a
[9, 2, 6]

**注意：**

- 1、列表写在方括号之间，元素用逗号隔开。
- 2、和字符串一样，列表可以被索引和切片。
- 3、列表可以使用 **+** 操作符进行拼接。
- 4、列表中的元素是可以改变的。

Python 列表截取可以接收第三个参数，参数作用是截取的步长，以下实例在索引 1 到索引 4 的位置并设置为步长为 2（间隔一个位置）来截取字符串：

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/py-dict-1.png)

如果第三个参数为负数表示逆向读取，以下实例用于**翻转字符串**：

```python
def reverseWords(input): 
      
    # 通过空格将字符串分隔符，把各个单词分隔为列表
    inputWords = input.split(" ") 
  
    # 翻转字符串
    # 假设列表 list = [1,2,3,4],  
    # list[0]=1, list[1]=2 ，而 -1 表示最后一个元素 list[-1]=4 ( 与 list[3]=4 一样) 
    # inputWords[-1::-1] 有三个参数
    # 第一个参数 -1 表示最后一个元素
    # 第二个参数为空，表示移动到列表末尾
    # 第三个参数为步长，-1 表示逆向
    inputWords=inputWords[-1::-1] 
  
    # 重新组合字符串
    output = ' '.join(inputWords) 
      
    return output 
  
if __name__ == "__main__": 
    input = 'I like runoob'
    rw = reverseWords(input) 
    print(rw)
```

输出结果为：

```
runoob like I
```

#### 常用方法

List 内置了有很多方法，例如 append()、pop() 等等，这在后面会讲到。

### Tuple（元组）

元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 **()** 里，元素之间用逗号隔开。

元组中的元素类型也可以不相同：

tuple = ( 'abcd', 786 , 2.23, 'runoob', 70.2 )
tinytuple = (123, 'runoob')

**print** (tuple)       # 输出完整元组
**print** (tuple[0])      # 输出元组的第一个元素
**print** (tuple[1:3])     # 输出从第二个元素开始到第三个元素
**print** (tuple[2:])     # 输出从第三个元素开始的所有元素
**print** (tinytuple * 2)   # 输出两次元组
**print** (tuple + tinytuple) # 连接元组

以上实例输出结果：

```
('abcd', 786, 2.23, 'runoob', 70.2)
abcd
(786, 2.23)
(2.23, 'runoob', 70.2)
(123, 'runoob', 123, 'runoob')
('abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob')
```

元组与字符串类似，可以被索引且下标索引从0开始，-1 为从末尾开始的位置。也可以进行截取（看上面，这里不再赘述）。

其实，可以**把字符串看作一种特殊的元组。**

\>>> tup = (1, 2, 3, 4, 5, 6)
\>>> **print**(tup[0])
1
\>>> **print**(tup[1:5])
(2, 3, 4, 5)
\>>> tup[0] = 11 # 修改元组元素的操作是非法的
Traceback (most recent(最近) call last):
 File "<stdin>", line 1, **in** <module>
TypeError: 'tuple' object(对象) does **not** support(支持) item(项目) assignment(分配)

虽然tuple的元素不可改变，但它可以包含可变的对象，比如list列表。

构造包含 0 个或 1 个元素的元组比较特殊，所以有一些额外的语法规则：

```
tup1 = ()    # 空元组
tup2 = (20,) # 一个元素，需要在元素后添加逗号
```

如果你想创建只有一个元素的元组，需要注意在元素后面添加一个逗号，以区分它是一个元组而不是一个普通的值，这是因为在没有逗号的情况下，Python会将括号解释为数学运算中的括号，而不是元组的表示。

如果不添加逗号，如下所示，它将被解释为一个普通的值而不是元组：

```
not_a_tuple = (42)
```

这样的话，not_a_tuple 将是整数类型而不是元组类型。

string、list 和 tuple 都属于 sequence。

**注意：**

- 1、与字符串一样，元组的元素不能修改。
- 2、元组也可以被索引和切片，方法一样。
- 3、注意构造包含 0 或 1 个元素的元组的特殊语法规则。
- 4、元组也可以使用 **+** 操作符进行拼接。
- 5、函数的返回值返回多个值的时候是以元组的方式返回的。
- 6、函数还可以接收可变长参数，会将所有的参数收集到一个元组上，如*args参数

### Set（集合）

Python 中的集合（Set）是一种无序、可变的数据类型，用于存储唯一的元素。

> 底层实现是哈希表（Hash Table）

集合中的元素不会重复，并且可以进行交集、并集、差集等常见的集合操作。

在 Python 中，集合使用大括号 **{}** 表示，元素之间用逗号 **,** 分隔。

另外，也可以使用 **set()** 函数创建集合。

**注意：**创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

创建格式：

```
parame = {value01,value02,...}
或者
set(value)
```

\#!/usr/bin/python3

sites = {'Google', 'Taobao', 'Runoob', 'Facebook', 'Zhihu', 'Baidu'}

**print**(sites)  # 输出集合，重复的元素被自动去掉

\# 成员测试
**if** 'Runoob' **in** sites :
  **print**('Runoob 在集合中')
**else** :
  **print**('Runoob 不在集合中')


\# set可以进行集合运算
a = set('abracadabra')
b = set('alacazam')

**print**(a)

**print**(a - b)   # a 和 b 的差集

**print**(a | b)   # a 和 b 的并集

**print**(a & b)   # a 和 b 的交集

**print**(a ^ b)   # a 和 b 中不同时存在的元素

以上实例输出结果：

```
{'Zhihu', 'Baidu', 'Taobao', 'Runoob', 'Google', 'Facebook'}
Runoob 在集合中
{'b', 'c', 'a', 'r', 'd'}
{'r', 'b', 'd'}
{'b', 'c', 'a', 'z', 'm', 'r', 'l', 'd'}
{'c', 'a'}
{'z', 'b', 'm', 'r', 'l', 'd'}
```

### Dictionary（字典）

字典（dictionary）是Python中另一个非常有用的内置数据类型。

> 底层实现是哈希表（Hash Table）

列表是有序的对象集合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是**通过键来存取的，而不是通过偏移存取**。

字典是一种映射类型，字典用 **{ }** 标识，它是一个无序的 **键(key) : 值(value)** 的集合。、

注意：

1. 键(key)必须使用**不可变类型**。
2. 键(key)必须是唯一的。

dict = {}
dict['one'] = "1 - 菜鸟教程"
dict[2]   = "2 - 菜鸟工具"

tinydict = {'name': 'runoob','code':1, 'site': 'www.runoob.com'}

**print** (dict['one'])    # 输出键为 'one' 的值
**print** (dict[2])      # 输出键为 2 的值
**print** (tinydict)      # 输出完整的字典
**print** (tinydict.keys())  # 输出所有键
**print** (tinydict.values()) # 输出所有值

以上实例输出结果：

```
1 - 菜鸟教程
2 - 菜鸟工具
{'name': 'runoob', 'code': 1, 'site': 'www.runoob.com'}
dict_keys(['name', 'code', 'site'])
dict_values(['runoob', 1, 'www.runoob.com'])
```

构造函数 dict() 可以直接从**键值对序列**中构建字典如下：

\>>> dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
{'Runoob': 1, 'Google': 2, 'Taobao': 3}
\>>> {x: x**2 **for** x **in** (2, 4, 6)}
{2: 4, 4: 16, 6: 36}
\>>> dict(Runoob=1, Google=2, Taobao=3)
{'Runoob': 1, 'Google': 2, 'Taobao': 3}

**{x: x\**2 for x in (2, 4, 6)}** 该代码使用的是字典推导式，更多推导式内容可以参考：[Python 推导式](https://www.runoob.com/python3/python-comprehensions.html)。（格式：结果值1 if 判断条件 else 结果2  for 变量名 in 原列表）

**注意：**

- 1、字典是一种映射类型，它的元素是键值对。
- 2、字典的关键字必须为**不可变类型**，且不能重复。
- 3、创建空字典使用 **{ }**。
- 4、如果把一个字典对象作为for的迭代对象，将会遍历字典的键

#### 常用方法

另外，字典类型也有一些内置的函数，例如 clear()、keys()、values() 等。

### bytes 类型

在 Python3 中，bytes 类型表示的是不可变的二进制序列（byte sequence）。

与字符串类型不同的是，bytes 类型中的元素是整数值（0 到 255 之间的整数），而不是 Unicode 字符。

bytes 类型通常用于处理二进制数据，比如图像文件、音频文件、视频文件等等。在网络编程中，也经常使用 bytes 类型来传输二进制数据。

创建 bytes 对象的方式有多种，最常见的方式是使用 b 前缀：

此外，也可以使用 bytes() 函数将其他类型的对象转换为 bytes 类型。bytes() 函数的第一个参数是要转换的对象，第二个参数是编码方式，如果省略第二个参数，则默认使用 UTF-8 编码：

```
x = bytes("hello", encoding="utf-8")
```

与字符串类型类似，bytes 类型也支持许多操作和方法，如切片、拼接、查找、替换等等。同时，由于 bytes 类型是不可变的，因此在进行修改操作时需要创建一个新的 bytes 对象。例如：

x = b"hello"
y = x[1:3] # 切片操作，得到 b"el"
z = x + b"world" # 拼接操作，得到 b"helloworld"

需要注意的是，bytes 类型中的元素是整数值，因此在进行比较操作时需要使用相应的整数值。例如：

x = b"hello"
**if** x[0] == ord("h"):
  **print**("The first element is 'h'")

其中 ord() 函数用于将字符转换为相应的整数值。

## Python数据类型转换

Python 数据类型转换可以分为两种：

- 隐式类型转换 - 自动完成
- 显式类型转换 - 需要使用类型函数来转换

### 隐式类型转换

在隐式类型转换中，Python 会自动将一种数据类型转换为另一种数据类型，不需要我们去干预。

以下实例中，我们对两种不同类型的数据进行运算，较低数据类型（整数）就会转换为较高数据类型（浮点数）以避免数据丢失。

> Python的数据类型的"高低"可以按照如下顺序理解：布尔（bool）< 整型（int） < 浮点型（float）< 复数（complex）。这个顺序主要根据数据类型可以表示的信息范围和精度来确定的。

num_int = 123
num_flo = 1.23

num_new = num_int + num_flo

**print**("num_int 数据类型为:",type(num_int))
**print**("num_flo 数据类型为:",type(num_flo))

**print**("num_new 值为:",num_new)
**print**("num_new 数据类型为:",type(num_new))

以上实例输出结果为：

```
num_int 数据类型为: <class 'int'>
num_flo 数据类型为: <class 'float'>
num_new: 值为: 124.23
num_new 数据类型为: <class 'float'>
```

我们再看一个实例，整型数据与字符串类型的数据进行相加：

num_int = 123
num_str = "456"

**print**("num_int 数据类型为:",type(num_int))
**print**("num_str 数据类型为:",type(num_str))
**print**(num_int+num_str)

以上实例输出结果为：

```
num_int 数据类型为: <class 'int'>
num_str 数据类型为: <class 'str'>
Traceback (most recent call last):
  File "/runoob-test/test.py", line 7, in <module>
    print(num_int+num_str)
TypeError: unsupported operand type(s) for +: 'int' and 'str'
```

从输出中可以看出，整型和字符串类型运算结果会报错，输出 TypeError。 Python 在这种情况下无法使用隐式转换。

但是，Python 为这些类型的情况提供了一种解决方案，称为显式转换。

### 显式类型转换

在显式类型转换中，用户将对象的数据类型转换为所需的数据类型。 我们使用 int()、float()、str() 等预定义函数来执行显式类型转换。

**int()** 强制转换为整型：

x = int(1)  # x 输出结果为 1
y = int(2.8) # y 输出结果为 2
z = int("3") # z 输出结果为 3

**float()** 强制转换为浮点型：

x = float(1)   # x 输出结果为 1.0
y = float(2.8)  # y 输出结果为 2.8
z = float("3")  # z 输出结果为 3.0
w = float("4.2") # w 输出结果为 4.2

**str()** 强制转换为字符串类型：

x = str("s1") # x 输出结果为 's1'
y = str(2)   # y 输出结果为 '2'
z = str(3.0) # z 输出结果为 '3.0'

整型和字符串类型进行运算，就可以用强制类型转换来完成：

num_int = 123
num_str = "456"

**print**("num_int 数据类型为:",type(num_int))
**print**("类型转换前，num_str 数据类型为:",type(num_str))

num_str = int(num_str)   # 强制转换为整型
**print**("类型转换后，num_str 数据类型为:",type(num_str))

num_sum = num_int + num_str

**print**("num_int 与 num_str 相加结果为:",num_sum)
**print**("sum 数据类型为:",type(num_sum))

以上实例输出结果为：

```
num_int 数据类型为: <class 'int'>
类型转换前，num_str 数据类型为: <class 'str'>
类型转换后，num_str 数据类型为: <class 'int'>
num_int 与 num_str 相加结果为: 579
sum 数据类型为: <class 'int'>
```

以下几个内置的函数可以执行数据类型之间的转换。这些函数返回一个新的对象，表示转换的值。

| 函数                                                         | 描述                                                    |
| :----------------------------------------------------------- | :------------------------------------------------------ |
| [int(x [,base\])](https://www.runoob.com/python3/python-func-int.html) | 将x转换为一个整数                                       |
| [float(x)](https://www.runoob.com/python3/python-func-float.html) | 将x转换到一个浮点数                                     |
| [complex(real [,imag\])](https://www.runoob.com/python3/python-func-complex.html) | 创建一个复数                                            |
| [str(x)](https://www.runoob.com/python3/python-func-str.html) | 将对象 x 转换为字符串                                   |
| [repr(x)](https://www.runoob.com/python3/python-func-repr.html) | 将对象 x 转换为表达式字符串                             |
| [eval(str)](https://www.runoob.com/python3/python-func-eval.html) | 用来计算在字符串中的**有效Python表达式,并返回一个对象** |
| [tuple(s)](https://www.runoob.com/python3/python3-func-tuple.html) | 将序列 s 转换为一个元组                                 |
| [list(s)](https://www.runoob.com/python3/python3-att-list-list.html) | 将序列 s 转换为一个列表                                 |
| [set(s)](https://www.runoob.com/python3/python-func-set.html) | 转换为可变集合                                          |
| [dict(d)](https://www.runoob.com/python3/python-func-dict.html) | 创建一个字典。d 必须是一个 (key, value)元组序列。       |
| [frozenset(s)](https://www.runoob.com/python3/python-func-frozenset.html) | 转换为不可变集合                                        |
| [chr(x)](https://www.runoob.com/python3/python-func-chr.html) | 将一个整数转换为一个字符                                |
| [ord(x)](https://www.runoob.com/python3/python-func-ord.html) | 将一个字符转换为它的整数值                              |
| [hex(x)](https://www.runoob.com/python3/python-func-hex.html) | 将一个整数转换为一个十六进制字符串                      |
| [oct(x)](https://www.runoob.com/python3/python-func-oct.html) | 将一个整数转换为一个八进制字符串                        |

并非所有类型的数据都可以被转换成其他任意类型。转换是否可行，主要取决于数据本身是否包含足够的信息来表示目标类型。
