## 通过字符串调用函数
```python
eval(func)()   #eval is evil 少用

locals()[func]()
globals()[func]()

getattr(object, name)()   #name could be variety
```
## 找不到key

所有的映射类型在找不到键的时候，就会调用`__missing__`方法。

## Mapping
`映射类型：Mapping`python中只有一种标准映射类型dict

dict中每个元素是`key: value`的键值对

key是无序的，且key必须是可哈希的不可变类型（str，float，bool，不包含可变类型的tuple）（反例：list和包含可变类型的tuple）

key最好不要数字
```python
#mapping
def fmap(a, b):
        return (a, b)
lik = range(1, 9)
liv = list("abcdefgh")
print map(fmap, lik, liv)

# mapping object can be used in dict(mapping)
lim = map(fmap, lik, liv)
d = dict(lim)
```

