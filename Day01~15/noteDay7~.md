# day7
## 字符串
`str` 非标量类型（结构化的）
`int` `float` 标量类型（没有内部结构）

3引号也可写字符串，可以换行
``\``表示转义
`\141`8进制的a `x61`十六进制的a
`\`也可跟Unicode编码表示字符
运算：`+`拼接, `*`重复, 成员运算`in``not in`, 切片     
  
格式化：
```python
a, b = 5, 10
print('{0} * {1} = {2}'.format(a, b, a * b))

a, b = 5, 10
print(f'{a} * {b} = {a * b}')

```
## list
```python
for index, elem in enumerate(list1):
    print(index, elem)
```
方法：
```python
.append(a)              #添加最后
.insert(i, a)           #在下标i插入a
.extend([list])
+= [list]               #尾部合并一个list
.remove(a)              #a如果在列表存在就删除
.pop(i)                 #删除i
.pop(len(list) - 1)     #删除最后一个
.clear()                #清空列表
```
切片：
```python
[:]             #全元素,直接[]会报错
[a:b:t]         #[a,b)步长t
t = -1          #倒转列表
a < b       
a < 0           #反向切片[-a:-1] ==[a-1:a]
                #[-a,0]会报错，所以反向切片不能切到最后一个元素

[a,a]           #中间是空的，可以用来插入
 a  b  c  d 
 0  1  2  3
-4 -3 -2 -1
```
排序：
```python
list2 = sorted(list1)   #默认字母表顺序 
list1.sort()            #会改变原list
参数：
    reverse = True      #反向，即降序
    key = len           #按字符串长度排len(a)
                        #可以用lambda
                        #实际排的是函数的返回值,可以自定义
```
生成(器)/ 生成[式]：
```python
式:                                              #生成式是个列表，一开始就被算出来了
f = [x for x in range(1, 10)]
f = [x + y for x in 'ABCDE' for y in '1234567']

器:                                              #生成器被调用的时候会事实运算内部
f = (x ** 2 for x in range(1, 1000))             #[式]和(器)

for val in f:
    print(val)
    
函数形式：
def fib(n):
a, b = 0, 1
for _ in range(n):
    a, b = b, a + b
    yield a             #yield 和 return 不同 next（fib）一次，返回一个

```
数字运算：斐波那契a, b = b, a + b

## 集合
```python
set0 = {1,1,2,2,3}             #重复元素自动只取一个  数字的话会被自动排序
len(set0)  # 3

set1 = set(range(1,100))      #构造器语法
     = set((1,2,3))
                              #推导式语法
set2 = {num for num in range(1,100) if num % 3 == 0 or num % 5 == 0}

.add()              #添加元素
.discard            #The discard() method removes the specified item from the set
set.pop()           #随机移除一个元素，可以print出来这个元素
                    #pop()删除的数字一定是序列第一（排序原理未知）的数字，但也可能随机到其他元素
                    #经测试，pop移除的是第一个元素，但集合每次的排序随机，所以是随机移除
```
## 集合交并差
```python
# 集合的交集、并集、差集、对称差运算
print(set1 & set2)
# print(set1.intersection(set2))
print(set1 | set2)
# print(set1.union(set2))
print(set1 - set2)                          # a-b 即 a中不是b集合的元素
# print(set1.difference(set2))
print(set1 ^ set2)                          #对称差，并减交， 即a，b集合中不同时属于a，b的元素
# print(set1.symmetric_difference(set2))    

# 判断子集和超集 返回True\False
print(set2 <= set1)
# print(set2.issubset(set1))
print(set3 <= set1)
# print(set3.issubset(set1))
print(set1 >= set2)
# print(set1.issuperset(set2))
print(set1 >= set3)
# print(set1.issuperset(set3))

```

## 字典
```python
#字面量语法
dict = {'a':1, 'b':2}
#构造器语法
item1 = dict(one=1, two=2, three=3, four=4)
#

```
