# day2
复数型：1+2j

PEP：Python Enhancement Proposals  
代码规范：PEP 8  

type() 类型检查 '''<class 'type'>'''  
chr() int => char  
ord() char => int (编码 e.t.ascii character codes）

[:]切片  
**指数  
//整除  
~按位取反  
^按位异或 |按位或 &按位与  

in， not in 成员运算符  
is， is not 身份运算符  
%a.bf 占位符,保留b位小数,''外面也要%, 算小数点，少于a位补齐空格  
***
# day3~5
分支结构  
if elif else

循环结构  
while…break  
for…in…
continue  
range(start, end, step)
***
# day6
## 函数
def……return  

python不支持函数的重载
    即后续定义会覆盖先前的定义
函数预设默认值，则未传参数时使用默认值

```
    def a(b=0)
        return b*b
    print(a()) # 0
    print(a(1))  # 1
```
*args 可变参数，可以0个或多个参数

使用不同模块同名函数（module）from module import function 模块导入的时候会覆盖
模块中可执行文件一定要放__main__里，否则调用时会自动执行

## 作用域
函数内部可以再定义函数
内置作用域>>全局作用域>>局部作用域>>嵌套作用域
下层作用域修改参数时相当于重新定义了一个，所以global才能修改

nonlocal 可以改嵌套作用域

减少全局变量，降低代码耦合度
迪米特法则

用完后还用=>闭包
***
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
生成器/式：
