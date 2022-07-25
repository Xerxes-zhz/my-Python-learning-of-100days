# What is OOP
`object`: a set of data structures and method for processing them

``class``: objects which have same behavior

`encapsulation`: bundle data and methods to warp details of class(internal representation)(information hiding)

`inheritance`: to specialization and generalization

`polumorphism`: dynamic dispatch based on objec type

类是对象的蓝图和模板，而对象是类的实例

### 访问可见性
`private` or `protected` attribute   

-----#`__func` means private but `_class__func` is accessible

`public`  method

## 装饰器
`@property` getter method

`@a.setter` setter method` 'a' means attribute which is private`

```python
@property
def age(self):
    return self._age
@age.setter
def age(self,age):
    self._age = age    
```
## __slots__
```pyhton
 __slots__ = ('attr1','attr2','attr3')    #对象只能绑定某些属性, 不对子类生效
```

## 静态和类方法
`@staticmethod` 没有`self`

`@classmethod` `cls`表示类对象

## Relationship between Class
`is-a` means Inheritance or Generalization

`has-a` means 关联relevancy，（整体和部分）聚合关系Aggregate relationships，（整体和部分不可分割）合成关系Synthetic relationships

`use-a` means Dependency

### 父类和子类
`Superclass` and `Subclass`

子类在继承了父类的方法后，可以对父类已有的方法给出新的实现版本，这个动作称之为方法重写（override）。通过方法重写我们可以让父类的同一个行为在子类中拥有不同的实现版本，当我们调用这个经过子类重写的方法时，不同的子类对象会表现出不同的行为，这个就是多态（poly-morphism）。
#### 里氏替代原则
“派生类（子类）对象可以在程序中代替其基类（超类）对象。”
#### 抽象类
python没有抽象类`class which can't create object`

The existence of abstract classes is inherited by other class
```python
from abc import ABCMeta, abstractmethod


class Pet(object, metaclass=ABCMeta):
    """宠物"""

    def __init__(self, nickname):
        self._nickname = nickname

    @abstractmethod
    def make_voice(self):       #就是给子类继承的，继承之后override才用   => poly-morphism
        """发出声音"""
        pass
```

