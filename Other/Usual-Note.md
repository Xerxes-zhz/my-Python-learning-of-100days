## 通过字符串调用函数
```python
eval(func)()   #eval is evil 少用

locals()[func]()
globals()[func]()

getattr(object, name)()   #name could be variety
```
