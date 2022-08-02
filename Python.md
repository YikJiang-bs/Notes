##  基础语法

### for-in循环

```python
for	a in 'Python'  #遍历输出''中的每一个字符赋值给a
```

### else语句

​	和while和for配合使用时，程序正常执行完后执行else，当遇到break时，不执行else

![image-20211106102746904](D:\桌面\笔记\Pricture\image-20211106102746904.png)

### 不换行输出

```python
# 输出三行四列的矩阵
for i in range(1,4):
    for j in range(1,5):
        print('*',end='\t') #不换行输出
    print()
```

```python
# 9*9
for i in range(1,10):
    for j in range(1,i+1):
        print(i,'*',j,'=',i*j,end='\t')
    print()
```

### 可变序列与不可变序列

- ​	不可变序列：字符串、元组
  - 不可变序列：没有增、删、改的操作
- 可变序列：列表、字典、集合
  - 可变序列:可以进行增、删、改的操作，对象的地址不发生改变

### input------获取到的都为字符串

## 列表

创建列表`list()`

### 获取列表索引`index（）`

1. ​	如果查询的列表中存在相同的N个元素，只返回第一个元素的索引

2. 还可以在指定的`start`和`stop`之间查找 

   ```python
   list=['hello','world',23]
   print(list.index('hello',1,4))  #在list列表中索引为1到3的中间查找hello的索引
   ```

### 获取列表中的多个元素

```python
list[start:stop:step]  #列表名[开始，结束，步长],step默认为1
```

1. step为正数时从start开始计算
2. step为复数时从start往左计算

### 遍历列表元素

```python
list = ['hello', 'world', 23]
for a in list:
    print(a)
```

### 列表元素的增删改 

#### 给列表中添加元素

##### 	`addpend`  在列表的末尾添加一个元素，添加列表时会作为一个元素添加

```python
list = ['hello', 'world', 23]
list2 = ['yang', 'yu', 'bo']
print('添加以前的列表为：', list)
list.append(list2)         #每次只能添加一个元素
print('添加以后的列表为：', list)
#没有创建新的列表对象
-----------------------------------
添加以前的列表为： ['hello', 'world', 23]
添加以后的列表为： ['hello', 'world', 23, ['yang', 'yu', 'bo']]
```

##### 	`extend`在列表的末尾至少添加一个元素，添加列表时会对列表中的每一个元素都作为一个新的元素添加进去

```python
list = ['hello', 'world', 23]
list2 = ['yang', 'yu', 'bo']
print('添加以前的列表为：', list)
list.extend(list2)
print('添加以后的列表为：', list)
----------------------------------------
添加以前的列表为： ['hello', 'world', 23]
添加以后的列表为： ['hello', 'world', 23, 'yang', 'yu', 'bo']
```

##### `insert`在列表的任意位置添加一个元素

```python
list = ['hello', 'world', 23]
list2 = ['yang', 'yu', 'bo']
print('添加以前的列表为：', list)
list.insert(2,list2)
print('添加以后的列表为：', list)
-----------------------------
添加以前的列表为： ['hello', 'world', 23]
添加以后的列表为： ['hello', 'world', ['yang', 'yu', 'bo'], 23]
```

#### 给列表中删除元素

##### `remove`删除一个元素

```python
list = ['hello', 'world', 23]
list.remove('hello')
print(list)
---------------------
['world', '23']
```

##### `pop`删除指定索引上的元素，不指定索引删除最后一个元素

```python
list = ['hello', 'world', 23]
list.pop(2)
print(list)
----------------------
['hello', 'world']
```

##### `clera()`清空列表

```python
list = ['hello', 'world', 23]
list.clear()
print(list)
```

##### `del`删除列表

```python
list = ['hello', 'world', 23]
del list
print(list)
```

#### 给列表中修改元素

##### 指定索引

```python
list = ['hello', 'world', 23]
list[2] = 'Python'
print(list)
---------------------------
['hello', 'world', 'Python']

```

##### 指定切片

```python
list = ['hello', 'world', 23]
list[1:3] = ['Python',6]
print(list)
-------------------------------------
['hello', 'Python', 6]
```

### 列表元素的排序操作

`sort()`方法 ，从大到小排序

```python

list = [1, 50, 14, 8, 59, 18]
list.sort()
print(list)
-----------------------------------
[1, 8, 14, 18, 50, 59]
#不会产生新的对象
```

`reverse=True`降序排序

```python
list = [1, 50, 14, 8, 59, 18]
list.sort(reverse=True)

print(list)
-------------------------------

[59, 50, 18, 14, 8, 1]
```

`sorted()`方法，产生新的列表对象，原列表没变化

```python
list = [1, 50, 14, 8, 59, 18]
new_list = sorted(list)
print(list, id(list))
print(new_list, id(new_list))
------------------------------
[1, 50, 14, 8, 59, 18] 1766675075592
[1, 8, 14, 18, 50, 59] 1766675076104
```

`reverse=True`降序排序

```python
list = [1, 50, 14, 8, 59, 18]
new_list = sorted(list, reverse=True)
print(list, id(list))

print(new_list, id(new_list))
-----------------------------

[1, 50, 14, 8, 59, 18] 2785407095304
[59, 50, 18, 14, 8, 1] 2785407095816
```

###  列表生成式

```python
list = [i for i in range(1, 10)]
print(list)
-------------------------------------
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

 ![image-20211106180754749](D:\桌面\笔记\Pricture\image-20211106180754749.png)

## 字典

- 可变序列--可以执行增删改的操作
- 以键值对的方式存储数据，是无序的序列----第一个放进来不一定处在第一个位置，通过`hash(key)`函数计算得到的位置
- 用{}表示
- 放在字典中的键必须为不可变序列-----（字符串 ）

#### 字典的创建

- 使用{}

- 使用内置函数`dict()`

查看字典中的元素

​	使用[]

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
print(scores['杨宇波'])
-----------------------
22
#查询不到键时报错

```

​	使用get

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
print(scores.get('詹姆斯'))
-------------------
None  #查询不到键时输出None
```

```python
#也可指定查询不到时输出的值
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
print(scores.get('詹姆斯', 'King'))
--------------------------------------
King

```

#### 字典的常用操作

##### 字典的删除

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
del scores['杨宇波']
print(scores)
---------------------
{'杨宇涛': 15, '蒋昊晟': 22}
```

##### 清空字典

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
scores.clear()
print(scores)
-------------------------
{}
```

##### 新增元素

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
scores['詹姆斯'] = 23
print(scores)
-----------------------------------
{'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22, '詹姆斯': 23}
```

#### 	获取字典视图的三个方法

​	`keys()`----------获取字典中的所有key

​	`values()`------------获取字典中的所有values

​	`items()`------------获取所有键值对   ----- 转换后的列表元素是由元组组成的

#### 字典的遍历

​	

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
for i in scores:
    print(i)   #默认输出键
------------------------------
杨宇波
杨宇涛
蒋昊晟
```

```python
scores = {'杨宇波': 22, '杨宇涛': 15, '蒋昊晟': 22}
for i in scores:
    print(scores[i], scores.get(i))  #两种方法输出值对
------------------------------------
22 22
15 15
22 22
```

#### 字典的特点

- key不可重复
- value可重复
- 字典的元素是无序的
- key必须是不可变对象
- 查询速度快，但是会浪费空间

#### 字典的生成式

​		`zip()`

```python
items = ['詹姆斯', '戴维斯', '库兹马']
prices = [23, 3, 0]
d = {i: j for i, j in zip(items, prices)}
print(d)
-----------------------------------------
{'詹姆斯': 23, '戴维斯': 3, '库兹马': 0}
```

![image-20211107133310944](D:\桌面\笔记\Pricture\image-20211107133310944.png)

## 元组

### 	元组的创建

- 小括号
- 使用内置函数`tuple()`，（）可以省略，如果元组中只有一个元素，需要使用， 逗号不能省略 
- 只包含一个元组的元素需要使用逗号和小括号

### 为什么要将元组设计为不可变序列

- 在多任务的环境下，同时操作对象时不需要加锁
- 尽量使用不可变序列
- 如果元组中的对象本身是不可对象，则不能再引用其他对象
- 如果元组中的对象是可变对象，则可变对象的引用不允许改变，但数据可以改变

![image-20211107165240687](D:\桌面\笔记\Pricture\image-20211107165240687.png)

### 遍历元组

查看元组中的每一个元素

```python
y = ('詹姆斯', '霍华德', '库兹马')
for a in y:
    print(a)
--------------------------------------
詹姆斯
霍华德
库兹马
```

## 集合

- 属于可变序列
- 集合是没有value的字典 
- 集合中的元素是无序的

### 创建方式

- {}   不允许重复

- `set()`内置函数创建

  - ```python
    a = set(range(9))
    print(a)
    ------------------------------------
    {0, 1, 2, 3, 4, 5, 6, 7, 8}
    ```

    

### 集合元素的增加

- `add()`-----------一次添加一个元素
- `update()`-----------一次至少添加一个元素

### 集合元素的删除

`remove()`一次删除一个指定元素，不存在抛出keyError

`discard()`一次删除一个指定元素，不存在不会抛出异常

`pop()`，一次只删除一个任意元素，不能指定参数，只能是无参的

`clear()`，清空集合 

### 集合间的关系

#### 	两个集合是否相等

​			集合相等不取决于元素的位置

#### 	一个集合是否是另一个集合的子集

​			`issubset`

```python
a = {1, 2, 3, 4, 5, 8, 96, 3, 1, 18, 1}
b = {1, 2, 3}
c = {1, 9, 4}
print(b.issubset(a))  #判断b是否为a的子集
-----------------------
Ture
```

#### 一个集合是否是另一个集合的子集

`issuperset()`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.issuperset(b))  #判断a是否为b的超集
-------------------------------
True
```

#### 两个集合是否有交集

`isdisjoint`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.isdisjoint(b))  #有交集为False，无交集为True
-----------------------------
False
```

### 集合的数学操作

![image-20211108221409641](D:\桌面\笔记\Pricture\image-20211108221409641.png)

#### 交集`intersection()`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.intersection(b))
print(a & b)
--------------------------------------
{10, 20}
{10, 20}
```

#### 并集`union()`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.union(b))  #自动去重
print(a | b)   
-----------------------------------
{3, 6, 7, 40, 10, 50, 20}
{3, 6, 7, 40, 10, 50, 20}
```

#### 差集`difference()`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.difference(b))
print(a - b)
------------------------------------
{3, 6, 7, 40, 50}
{3, 6, 7, 40, 50}

```

#### 对称差集`symmetric_difference()`

```python
a = {10, 20, 3, 40, 50, 7, 6, }
b = {10, 20}
print(a.symmetric_difference(b))
print(a ^ b)
------------------------------
{3, 6, 7, 40, 50}
{3, 6, 7, 40, 50}
```

### 集合生成式

```python
a = {i for i in range(6)}
print(a)  #无序
---------------------
{0, 1, 2, 3, 4, 5}
```

|   数据结构    | 是否可变 | 是否重复                 | 是否有序 | 定义符号    |
| :-----------: | -------- | ------------------------ | -------- | ----------- |
| 列表（list）  | 可变     | 可重复                   | 有序     | []          |
| 元组（tuple） | 不可变   | 可重复                   | 有序     | ()          |
| 字典（dict）  | 可变     | key不可重复，value可重复 | 无序     | {key:value} |
|   集合(set)   | 可变     | 不可重复                 | 无序     | {}          |

![image-20211108224119180](D:\桌面\笔记\Pricture\image-20211108224119180.png)

## 字符串

### 	字符串的驻留机制

​			相同的值的id相同	

​	

```python
a = 'Yang'
b="Yang"
c='''Yang'''
print(id(a))
print(id(b))
print(id(c))
------------------------------------
1968966907248
1968966907248
1968966907248
```

#### 		驻留机制的几种情况

​	字符串的长度为0或1时

​	符合标识符的字符串

​	字符串只在编译时候进行驻留，而非运行时

```python
>>> a='qwe'
>>> b='qw'+'e'
>>> c=''.join(['qw','e'])          #运行时通过join方法对列表中的数据经行链接
>>> a is b
True
>>> a is c
False
>>>
```



#### 字符串驻留的优缺点

​	需要相同字符时可以直接拿出来使用，提升效率节约内存

​	拼接字符串建议使用str类型的`join`方法，而非+。

#### join()方法语法：

```python
str.join(sequence) 	#sequence -- 要连接的元素序列。
```

​       

```python
s = '-'.join('123')
print(s)
---------------------------------------
1-2-3
```

  

### 字符串的查询

|   作用   |           方法名称           |   不存在   |
| :------: | :--------------------------: | :--------: |
| index()  |  查询字符串第一次出现的位置  | ValueError |
| rindex() | 查询字符串最后一次出现的位置 | ValueError |
|  find()  |  查询字符串第一次出现的位置  |     -1     |
| rfinf()  | 查询字符串最后一次出现的位置 |     -1     |

```python
a = 'Yang gnaY'
print(a.index('Y'))
print(a.rindex('Y'))
print(a.find('Y'))
print(a.rfind('Y'))
----------------------------------
0
8
0
8
```

###  字符串的大小写转换

| 方法名称     | 作用                               |
| ------------ | ---------------------------------- |
| upper()      | 所有转换为大写                     |
| lower()      | 所有转换为小写                     |
| swapcase()   | 大写转小写，小写转大写             |
| capitalize() | 第一个字符大写，其余小写           |
| title()      | 每个单词的第一个字符大写，其余小写 |

都会产生新的对象，无论是否改变

### 字符串的对齐操作

| 方法名称 | 作用                                |
| -------- | ----------------------------------- |
| center() | 居中对齐                            |
| ljust()  | 左对齐                              |
| rjust()  | 右对齐                              |
| zfill()  | 右对齐，左边用0填充，只接受一个参数 |

```python
a = 'Yang'
print(a.center(10,'@'))   #一共十位，左右平分，用@填充
print(a.center(10))     #不写第二个参数默认为空格
print(a.center(2))      #小于实际宽度，默认原样输出
--------------------------------------
@@@Yang@@@
   Yang   
Yang
```

```python
a = 'Yang'
print(a.zfill(10))
print(a.rjust(10, '$'))
print(a.ljust(10, '$'))
-------------------------------------
000000Yang
$$$$$$Yang
Yang$$$$$$

```

### 字符串劈分操作

​	`split()`

​			从左边开始劈分，默认劈分字符为空格，返回值为一个列表

​			通过参数`sep()`	可以指定劈分字符

​			通过参数`maxsplit`指定最大劈分次数

`rsplit()`

 			区别在与参数`maxsplit`

```python
a = 'James Davis Howard'
b = 'Curry|Thompson|Wiggins'
print(a.split())            #默认空格
print(b.split(sep='|'))		#指定|
print(a.split(maxsplit=1))	#左侧最大分割一个
print(a.rsplit(maxsplit=1))  #右侧最大分割一个
------------------------------------
['James', 'Davis', 'Howard']
['Curry', 'Thompson', 'Wiggins']
['James', 'Davis Howard']
['James Davis', 'Howard']
```

### 判断字符串操作

| 方法名称       | 作用                                         |
| -------------- | -------------------------------------------- |
| isidentifier() | 判断字符串是否为合法的标识符                 |
| isspace()      | 是否全部由空白字符组成（回车，换行，制表符） |
| isalpha()      | 判断是否全部由字母组成                       |
| isdecimal()    | 判断是否全部由十进制数字组成                 |
| isnumeric()    | 判断是否全部由数字组成   包含罗马数字        |
| isalnum()      | 判断是否全部由字母和数字组成                 |

###  字符串操作的其他方法

| 功能       | 方法名称       | 作用                                                    |
| ---------- | -------------- | ------------------------------------------------------- |
| 字符串替换 | replace(a,b,c) | a：被替换的字符<br />b：替换的字符<br />c：最大替换次数 |
| 字符串合并 | join()         | 将列表或元组中的字符串合并为一个字符串                  |

```python
a = 'James,Davis,Howard,Davis,Davis'
print(a.replace('Howard', 'Yang'))
print(a.replace('Davis', 'Curry', 2))
----------------------------
James,Davis,Yang,Davis,Davis
James,Curry,Howard,Curry,Davis
```

 

```python
a=['James','Davis','Curry']
print(' '.join(a))   #用空格连接
-------------------------------
James Davis Curry  
```

```python
print('$'.join('James'))   #作为字符串序列分别输出连接
----------------------------
J$a$m$e$s
```

`ord('a')`=97

`chr(97)`=a

### 格式化字符串

​		按一定格式输出的字符串

#### 格式化字符串的两种方式

`%`作占位符

```python
name = '杨宇波'
age = 22
print('我叫%s，今年%10d岁' % (name, age))  #10表示宽度，%.3f----保留三位小数
--------------------------
我叫杨宇波，今年        22岁
```

`{}作占位符`

```python
name = '杨宇波'
age = 22
print('我叫{0}，今年{1},我真的叫{0}'.format(name, age))    #用索引表示{0}代表name，{1}代表age，使用.format方法
print('我叫{0：.3}，今年{1}')       #.3代表一共三位数
print('我叫{0:.3f}，今年{1}') 		#.3f代表3位小数   .f后为四舍五入
print('我叫{0:10.3f}，今年{1}')    #宽度为10，保留3位小数
---------------------------------
我叫杨宇波，今年22,我真的叫杨宇波
```

`f-string` 作占位符

```python
name = '杨宇波'
age = 22
print(f'我叫{name}，今年{age}')
-----------------------------------
我叫杨宇波，今年22
```

### 字符串的编码转换

#### 编码与解码的方式

- 编码：将字符串转换为二进制数据
- 解码：将bytes类型的数据转换为字符串类型

```python
s = '煎蛋杨粑粑'
print(s.encode(encoding='GBK'))  # 在GBK中一个中文占两个字符
print(s.encode(encoding='UTF-8'))  # 在UTF-8中一个中文占三个字符
b = s.encode(encoding='GBK')
c = s.encode(encoding='UTF-8')
print(b.decode(encoding='GBK'))  # 解码
print(c.decode(encoding='UTF-8'))
------------------------------------------------------------
b'\xbc\xe5\xb5\xb0\xd1\xee\xf4\xce\xf4\xce'
b'\xe7\x85\x8e\xe8\x9b\x8b\xe6\x9d\xa8\xe7\xb2\x91\xe7\xb2\x91'
煎蛋杨粑粑
煎蛋杨粑粑

```

![image-20211113134745907](D:\桌面\笔记\Pricture\image-20211113134745907.png)

## 函数

### 函数的创建

```python
def 函数名（[输入参数]）：
	函数体
	[return xxx]
```

```python
def a(x, y):  #x,y为形参
    c = x + y
    return c
b = a(10, 20)	#10，20为实参 
print(b)
----------------------
30
```

```python
def a(x, y):
    c = x + y
    return c
b = a(y=10, x=20)   #x、y为关键字参数  
print(b)
---------------------------
30
```

在函数调用的过程中，进行参数的传递

如果是不可变对象，在函数体的修改不会影响实参的值

如果是可变对象，在函数体的修改会影响实参的值

### 函数的返回值

```python
def fun (num):
    odd=[]
    even=[]
    for i in num:
        if i % 2 :
            odd.append(i)
        else:
            even.append(i)
    return odd,even

lis=[10,29,34,23,44,53,55]
print(fun(lis))
-----------------------------------
([29, 23, 53, 55], [10, 34, 44])


'''
	（1）如果函数没有返回值【函数执行完毕后，不需要给调用处提供数据】 return可以省略
	（2）函数的返回值，如果是一个，返回原类型
	（3）函数的返回值，如果是多个，返回结果为元组


'''
```

### 可变的形参  

#### 个数可变的位置参数（只能定义一个 ）

​	当不确定参数个数时，可以在形参前面添加*

​	结果为一个元组

```python
def fun(*a):
    print(a)
fun(10)
fun(20, 50)    
--------------------------
(10,)  			#输出的为元组
(20, 50)
```

#### 个数可变的关键字形参（只能定义一个 ）

​	无法确定关键字实参个数时，使用**定义个数可变的关键字形参

​	结果为一个字典

```python
def fun(**age):
    print(age)
fun(a=10)
fun(b=20, c=50)
------------------------------------
{'a': 10}			#结果为一个字典
{'b': 20, 'c': 50}

```

在一个函数的定义过程中，既有个数可变的关键字形参，也有个数可变的位置形参，要求个数可变的位置形参放到个数可变的关键字形参之前

`**`  将列表中的每一个元素都转为位置实参传入

```python
def fun(a, b, c):
    print('a=', a)
    print('b=', b)
    print('c=', c)
list = [13, 23, 45]
fun(*list)              #将列表中的每一个元素都转为位置实参传入
------------------------------------------
a= 13
b= 23
c= 45
```

`**d	` #将字典中的每一个元素都转为关键字实参传入

```python
def fun(a, b, c):
    print('a=', a)
    print('b=', b)
    print('c=', c)
d={'a':10,'c':800,'b':234}

fun(**d)              #将字典中的每一个元素都转为关键字实参传入
--------------------------------------------

a= 10
b= 234
c= 800 
```

需求：c，d只能采用关键字形参

```python
def fun(a, b, *, c, d):   #*以后的参数，在函数调用时，只能采用关键字参数
    print('a=', a)
    print('b=', b)
    print('c=', c)
    print('d=', d)
fun(10, 51, d=15, c=45) 
---------------------------------------
a= 10
b= 51
c= 45
d= 15
```

### global--------把局部变量变化为全局变量

```python
def fun3():
    global a
    a=20
    print(a)
fun3()
print(a)
-----------------------------------
20
20
```

## 异常

### 多个except结构

​	按照先子类后父类的方法顺序，为了避免遗漏的异常可在最后增加BaseException（父类）

```python
try：		
	pass	#可能会出现异常的代码
except xxx:		#xxx为异常的类型
	pass		#异常处理代码
except Exception2:		
	pass	
except BaseException:		
	pass	
```

```python
try:
    a = int(input('请输入第一个数字'))
    b = int(input('请输入第二个数字'))
    c = a / b
    print(c)
except  ZeroDivisionError:
    print('除数不能为0')
except  ValueError:
    print('请输入整数')
print('程序结束')
-----------------------------------
请输入第一个数字20
请输入第二个数字0
除数不能为0
程序结束
----------------------------
请输入第一个数字20
请输入第二个数字
请输入整数
程序结束
```

### try...excpet...else结构

​	如果try块中没有抛出异常，则执行else块，如果抛出异常，则执行except快

```python
try:
    a = int(input('请输入第一个数字'))
    b = int(input('请输入第二个数字'))
    c = a / b

except  ZeroDivisionError:
    print('除数不能为0')
except  BaseException:
    print('请输入整数')
else:
    print('结果为', c)
-----------------------------------
请输入第一个数字45
请输入第二个数字435
结果为 0.10344827586206896

Process finished with exit code 0

```

### try...excpet...else...finally结构

​	finally块无论是否发生异常都会执行，常用来释放try块中申请的资源

![image-20211117191729312](D:\桌面\笔记\Pricture\image-20211117191729312.png)

```python
try:
    a = int(input('请输入第一个数字'))
    b = int(input('请输入第二个数字'))
    c = a / b

except  ZeroDivisionError:
    print('除数不能为0')
except  BaseException:
    print('请输入整数')
else:
    print('结果为', c)
finally:
    print('谢谢您的使用')
    --------------------------------
    请输入第一个数字34
请输入第二个数字34
结果为 1.0
谢谢您的使用
```

## 类和对象

### 创建类的语法

```python
class Students：
	pass
```

类的组成

- 类属性
- 实例方法
- 静态方法
- 类方法

```python
class Student:  #student  类对象
    native_pace='山西'  #直接写在类里的变量，称为类属性
    #实例方法
    def __init__(self,name,age):
        self.name=name  #self.name为实体属性，将局部变量name 的值赋给实体属性
        self.age=age
    def eat(self):  #在类之外定义的称为函数，在类之内定义的叫做方法
        print('学生在吃饭')
    #静态方法
    @staticmethod
    def method():   #静态方法不需要写self
        print('我使用了staticmethod进行修饰，所以我是静态方法')
    #类方法
    @classmethod
    def cm(cls):
        print('我是类方法，我使用了calssmethod修饰')
def drink():    #在类之外定义的称为函数，在类之内定义的叫做方法
    print('喝水')

stu1 = Student('杨宇波',22)  #创建对象
stu1.eat()   #对象名.方法名
print(stu1.name)
print(stu1.age)
print('---------------------- -------------------------')
Student.eat(stu1)   #与stu1.eat()作用相同    #类名.方法名(类的对象)---------->方法定义处的stu1



```

### 类的使用方式

```python
print(Student.native_place)  #访问类属性
Student.cm()	#调用类方法
Student.sm()	#调用静态方法
```

