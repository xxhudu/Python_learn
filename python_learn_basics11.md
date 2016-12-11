# Python 学习: 面向对象编程(概念)

### 面向对象的概念

`python` 是一门面向对象的语言, 掌握了面向对象, 能写出更加优雅、抽象的程序.

**面向对象有以下几个概念**

* **多态**: 意味着可以对不同类的对象使用相同的操作.
* **封装**: 对外部隐藏对象的工作细节, 意味着对象中的特性只对自己的方法可用.
* **继承**: 一个类可以是多个类的子类, 子类从超类继承所有的方法。
* **类**: 类是一组对象的集合,类主要定义实例所会用到的方法.
* **方法**: 绑定到对象特性上的函数称为方法 `method`
* **对象**: 对象包括特性和方法, 特性是作为对象的一部分变量, 方法则是存储在对象中的函数.

#### 多态

我们之前已经接触过支持多态的函数, 例如 `len`, `add`, `repr` 等.

他们都可以对不同类型的对象进行相同的操作

```python
# len 函数可以拥有长度的对象进行操作.
In [1]: str = 'ABCDEFG'

In [2]: len(str)
Out[2]: 7

In [3]: lst = ['1', '2', '3']

In [4]: len(lst)
Out[4]: 3
```

```python
# add 模块可以对任意支持加法的对象进行操作.
In [7]: from operator import add

In [8]: add(7, 8)
Out[8]: 15

In [9]: add('ABC', 'fejifej')
Out[9]: 'ABCfejifej'

In [10]: add(['a', 'b', 'c'], ['z'])
Out[10]: ['a', 'b', 'c', 'z']
```

```python
# 最有代表性的应该属 repr 函数, 可以对任意对象使用.
In [11]: repr(287982493)
Out[11]: '287982493'

In [13]: repr(['fjeijefi', 'efjfejief', 'efkefife'])
Out[13]: "['fjeijefi', 'efjfejief', 'efkefife']"

In [14]: repr({'a': 2, 'f': 3})
Out[14]: "{'f': 3, 'a': 2}"
```

#### 封装

封装是对全局作用域中其他的区域隐藏多余信息的原则, 使用对象而不用知道其内部细节, 和多态的概念类似, 但是封装不同于多态. 多态可以让用户对于不知道是什么类、对象类型的对象进行方法调用, 而封装可以不用关心对象如何构建而直接进行使用.

听起来很玄乎, 其实和函数差不多, 函数的是最小作用域, 函数的内部变量不影响全局变量. 而对象中的变量也是如此, 只不过在对象的变量叫做特性 `attribute`

#### 继承

如果我们定义了一个 `Bird` 的类, `Bird` 类中有 `eat`, `fly` 等方法, 但是我们知道并不是所有的鸟都会飞, 如果我们想定义一个 `penguin` 的类, 因为企鹅不会飞, 所以我们需要重新定义一个类? 将所有方法再写一遍? 不需要这样做, 只需要用到继承既可以, 我们可以定义一个 `penguin` 的类, `penguin` 是 `Bird` 的子类, 继承 `Bird` 的所有方法, 然后我们只需专门对 `fly` 方法进行重写即可.