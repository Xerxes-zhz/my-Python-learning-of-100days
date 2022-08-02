## 通过字符串调用函数
```python
eval(func)()   #eval is evil 少用

locals()[func]()
globals()[func]()

getattr(object, name)()   #name could be variety
```
## 找不到key

所有的映射类型在找不到键的时候，就会调用`__missing__`方法。
