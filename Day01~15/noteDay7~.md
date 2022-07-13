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
```
a, b = 5, 10
print('{0} * {1} = {2}'.format(a, b, a * b))

a, b = 5, 10
print(f'{a} * {b} = {a * b}')

```
## list
```
for index, elem in enumerate(list1):
    print(index, elem)
```
方法：
```
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
```
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
```
list2 = sorted(list1)   #默认字母表顺序 
list1.sort()            #会改变原list
参数：
    reverse = True      #反向，即降序
    key = len           #按字符串长度排len(a)
                        #可以用lambda
                        #实际排的是函数的返回值,可以自定义
```
生成(器)/ 生成[式]：
```
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
    yield a

```
数字运算：斐波那契a, b = b, a + b

