<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>
if语句——选择判断
======

🌟你已经到到第三章啦，继续加油吧~

如果…否则如果…否则…
------
if语句，是Python逻辑中最简单和最常用的一种。它的意义是，当某个条件成立时，执行某个操作；当这个条件不成立时，执行另外一个操作。具体的代码如下：
```python
if (条件1):
···
#如果条件1为真，则执行，执行完跳出if
elif(条件2):  #条件1为假才判断
#如果条件2为真，则执行，执行完跳出if
else:  # 前面的条件都不对才判断
···
#如果条件为假，则执行
```
**注意**：我们只能在一个`if`语句里面有一个`else`，但却可以有很多个`elif`语句。请不要忘记在`if`,`elif`,`else`后面加上英文冒号。

`if...elif...else`语句的功能很大，比如我们成绩的分数段可以这么判断：
```python
grade = 100 #是一个0-100之间的数值
if(grade >= 90):
	print("90-100")
elif(grade >= 80):
	print("80-90")
elif(grade >= 70):
	print("70-80")
elif(grade >= 60):
	print("60-70")
else:
	print("<60")
```
上方就是一个最简单的判断语句的使用方式，如果`grade`大于等于`90`，那么输出`90-100`，如果不是再判断是不是大于等于`80`，有则输出`80-90`，以此类推，如果直到最后发现没有大于等于`60`，那么输出`<60`。

且、或和非
-----
且、或和非统称为逻辑运算符，和上一章介绍的关系运算符一样，都是一种运算符。“且”要求两个陈述同时成立，“或”要求两个陈述至少成立一个，而“非”就是将布尔值转换，把真的变成假的，假的变成真的。在Python语言中它们如下表所示：

|运算符|含义|范例|
|-|-|-|
|and|且|if(3>2 and 9<10):|
|or|或|if(3<2 or 8==8):|
|not|非|if(not True==False)|

非 e.g.

```python
if(not a):
  ...
```
这段代码等效于下面的代码中的`else`代码块：
```python
if(a):
	...
else：
	...
```
且 e.g.

```python
if(a and b)：
	...
```
这段代码等效于下面的代码：

```python
if(a):
	if(b):
    	...
```
或 e.g.

```python
if(a or b):
	...
```
这段代码等效于下面的代码（例外是，如果`a`和`b`都是`true`这个代码不会执行两次，只会执行一次）：

```python
if(a):
	...
if(b):
	...
```
有趣的是，`1`和`0`在if语句里也能作为`True`和`False`进行判断。由于计算机语言的实质是二进制语言，`0`在计算机语言中即代表`False`,`1`即代表`True`。

大家也可以在下面的lab中尝试一下，修改其中的逻辑运算符，来感受一下其中的差别。
<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>
a = True
b = False
if(a or b):
	print("aaa")
else:
	print("bbb")

</lab>

最小化求值原理
-----
使用电脑的人总是希望电脑可以很快完成任务，设计电脑的工程师当然也是这样想的。因此计算机程序再运行的时候会自动排除一些不可能发生的情况，从而让电脑少算一些值来加快电脑运行的速度。

比如我们的程序需要判断100是不是等于200`and`200是不是等于200，计算机在运算的时候，首先判断100是否等于200，当它发现100已经不等于200的时候，无论后面200是不是等于200，这整个判断都不可能是正确的。因此计算机就跳过了后面的判断，直接以这个判断的结果为不正确来处理。

同样，当我们的程序需要判断100是不是等于100`or`200是不是等于300，计算机在运算的时候，首先看100是不是等于100，发现是的，那么无论后面200是不是等于300，整个判断都是对的，因此计算机也跳过了后面的判断，直接以这个判断的结果为正确来处理。

这就是最小化求值原理或者短路求值（short-circuit evaluation）看起来是计算机内部的一个小把戏，可有的时候也会影响到我们程序的运行。

比如当我们程序是这样的时候，无论第二个条件“200 == 200”怎么改变，是不是正确的，都不会改变程序最后输出“No”的事实：
```Python
a = 100;
if(a == 200 and 200 == 200)：
	print("Yes")
else：
	print("No")
```
请在lab中试一下这个神奇的功能吧！
<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>
#python3
a = 100
if(a == 200 and 200 == 200):
	print("a")
else:
	print("b")
if(a == 200 or 200 == 200):
	print("c")
else:
	print("d")

</lab>

德摩根定律
-----
在计算机里，德摩根定律表示的是两种等价关系：
* `(not a) and (not b) <=> not(a or b)`
* `(not a) or (not b) <=> not(a and b)`
其中，`<=>`意味着等价，`a`和`b`都是布尔值。

例如，当`a`和`b`都是`True`时，我们看定律中的第一条：

`(not a) and (not b) = (not True) and (not True) = False and False = False`

`not(a or b) = not(True or True) = not True = False`

两者的值是一样的。

当`a`和`b`都是`True`时，我们看定律中的第二条：

`(not a) or (not b) = (not True) or (not True) = False or False = False`

`not(a and b) = not(true and true) = not true = False`

两者的值是也一样的。

小练习
-----
1. What will be output by the following statement?
```python
age = 1
if(age > 10):
	print(age)
```
(A)1

(B)10

(C)no output

(D)unknown

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>C</cr>

2. What will be output by the following statement?
```python
i = 7
if(i>0):
	if(i%2 == 0):
		print(i)
	else:
		print(str(i)+" is not divisible by 2")
```
(A)7

(B)1

(C)no output

(D)7 is not divisible by 2

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至[程谱 coderecipe.cn](https://coderecipe.cn/learn/2)查看。</notice>D</cr>
