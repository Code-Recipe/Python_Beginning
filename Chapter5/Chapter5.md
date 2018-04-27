<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
数学计算
======
🌟你已经到到第五章啦，继续加油吧~

数学函数和常量的使用
-----
函数（方法）在数学上的概念是数的一一对应。在计算机科学上，我们可以把函数的调用过程理解成传入一个或者多个参数，执行某些指令，再返回一个值（这个值可以是Object）的过程。

因此，在计算机科学中，函数其实和方法是一样的东西。比如我们经常使用的输出函数"print()"就是一个函数。它的作用在于输出指定的内容，然后换行。

不止这些内置的函数，我们也可以自己定义一些函数，用于未来的调用执行。函数的定义方法如下：
```python
def 函数名():
  #代码
```

函数的结果可以直接用`print()`函数打印出来。但是当我们不想直接打印出来，而是想将这个函数的结果储存到一个变量的时候，我们可以用`return`来帮助我们完成这个任务,`return`可以理解为把计算结果从函数部分传出去。
<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>
def func(a):
  square= a*a
  return square #这个函数计算传入参数a的平方
print(func(10)) #我们把10当作参数a传进了函数func里，result会被赋值为func的计算结果
</lab>

当一个函数没有`return`语句时，也就意味着这个函数不会返回任何值，比如下面的`func1`没有返回值，而`func2`有：

<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>
def func1():
  #代码
  print("func1")
def func2(a,b):
  #代码
  return a+b
func1() #调用的是第一个函数，输出func1
func2()
print(func2(1,2)); #调用的是有参数的第二个函数，使用了返回值，会输出3
</lab>

为了方便我们在Python中使用数学方法和常量，python专门开发了`math`类。如果我们需要，需要在程序的最开头调取。常数主要有e和圆周率PI两个，调用方法如下：
```python
import math #import方法会在后面讲到
print(math.pi)
print(math.e)
```
至于数学方法，math类中有非常多，我们摘录一些常用的在这里：
```python
sin(x) #求x的正弦
cos(x) #求x的余弦
asin(x) #求x的反正弦
acos(x)#求x的反余弦
tan(x)#求x的正切
atan(x)#求x的反正切
hypot(x,y)#求直角三角形的斜边长度
fmod(x,y)#求x/y的余数
ceil(x)#取不小于x的最小整数
floor(x)#求不大于x的正大整数
fabs(x)#求绝对值
exp(x)#求e的x次幂
pow(x,y)#求x的y次幂
log10(x)#求x的以10位底的对数
sqrt(x)#求x的平方根
pi#π的值
```

随机数的产生
-----
通过`random`类，我们也可以生成随机数，我们首先还是要在程序的开头引入`random`库。生成随机数的方法如下：
```python
import random
random.random()#指random模块里的random函数，可以产生0-1.0之间的随机小数
```
这样可以随机生成一个a到b之间的整数类型的数。比如这样：
```python
math.randint(1,10) #随机生成大于等于1，小于等于10的整数
math.random(a,b) + 1; #随机生成大于等于a，小于等于b的整数
```

`random`模块中还有一个很强大的函数是`choice`。`random.choice()`函数可以从字符串，列表，元组等`sequence`里随机抽取函数。比如说：

```python
import random
print(random.choice("I love python")) #python会从这个字符串中随机抽取一个字符（包括空格）
print(random.choice["MY""name""is""John""."]) #python会从这个列表中随机抽取一个元素
```

import
-----
之所以python时下非常火热，就是因为python给开发者提供了大量的函数模块，比如著名的`numpy`。`random`和`math`只是python官方提供的两个基本函数库。
开发者可以通过调用已有的函数库，从而减少自己写的代码。如果你以后要用python进行机器学习，人工智能等方面的研究，`import`函数更是你必不可少的利器。
`import`函数的标准用法是：
```python
import 函数模块(.函数名) as 名称
```
有时候如果你只想用某个函数模块中的一个函数，你就可以在函数模块后加上你要的函数名，就像`import math.pi`。而`as`则是用来简写函数模块的名称。
比如你要使用`random`函数来进行数据的分析，你又觉得`random`打起来很麻烦，你可以这样写：
```python
import random as rd
a=rd.random() #调用random()函数
```

小练习
-----
1. 请定义一个函数使其有1个返回值，并调用这个函数。
2. 请生成一个范围为6-21的float型随机值。
3. 请定义一个可以调用`math.fabs()`的函数来计算绝对值
<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>
#python3
#请在此输入你的代码
</lab>
