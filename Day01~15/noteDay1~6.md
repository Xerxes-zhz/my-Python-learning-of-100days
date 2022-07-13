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
