<notice>教程读者请不要直接阅读本文件，因为诸多功能在此无法正常使用，请移步至程谱 coderecipe.cn学习完整教程。如果您喜欢我们的教程，请在右上角给我们一个“Star”，谢谢您的支持！</notice>

循环
======

🌟你已经到到第四章啦，继续加油吧~

在很多时候，只执行代码一次是没有办法达到目的的。而要多次执行代码，一次次的复制粘贴无疑是最傻的一件事情。于是，我们还需要循环结构来帮我们快速地重复执行代码。

for循环
------

for循环的用法如下：
```python
for 变量名 in range(下限，上限，步长):
    #循环内容
```
for的运行方式是：

a)先给变量名赋值为下限，然后执行循环内容；

b)执行过一遍后，变量+=步长，再检测变量是否达到上限（大于等于上限则循环结束）;

c)重复执行b)直到循环结束。

说了for循环的代码格式和运行原理，我们就来用一个实例试一下吧！

e.g.
```python
for i in range(1,5):
    print(i)
```
上面的代码会输出"1 2 3 4 "。

while循环
------

while循环的运行原理和for循环大抵相同，但在写法上有一定差异。while循环的写法如下：
```python
while(测试条件)：
    //循环内容 
```
while循环会先判断条件，如果符合（True）就会继续执行循环内容，不符合就会跳出循环执行下面的内容，执行完循环内容后会返回来判断条件，如果符合的话接着执行循环内容，一直重复知道条件不符合（False）为止。所以说，我们如果想要像上例一样输出"1 2 3 4 "，可以这么写代码：
```python
i = 1
while(i < 5):
    print(i, end =' ')
    i = i + 1
```

continue下一循环和break停止循环
------

在循环中，我们有两种操作可以停止当前的循环。这就需要用到关键字continue和break。这两者的区别是，break的作用是跳出当前循环块（for、while、do while）或程序块（switch）并执行循环块或程序块外的代码，而continue用于结束循环体中其后语句的执行，并跳回循环程序块的开头执行下一次循环，而不是立刻循环体。

我们可以配合实例来看一下：
```python
for i in range(1,6):
    if (i == 3): 
        continue
    print(i, end=' ')
print("\n")
for n in range(1,6):
    if (n == 3): 
        break
    print(n, end = ' ')
```
输出结果会是“1 2 4 5  \n  1 2”。怎么样，是不是和你想的一样呢？

同样的，我们也会把这节课学到的内容放进lab。大家可以运行来试试，修改其中的内容，探究循环的奥秘。

<lab lang="python" parameters="filename=Hello.py">
<notice>练习环境在此无法显示，请移步至程谱 coderecipe.cn查看。</notice>
#python3
a=int(input())
isPrime=True
for i in range(2,a):
    if(a%i==0):
        isPrime=False
        break
if(isPrime or a==2):
    print("%d is a prime number" %a)
else:
    print("%d is not a prime number" %a)
</lab>

小练习

1. 尝试输出1-100中所有3的倍数
2. 
```python
a=10
sum=0
while(a!=1):
    sum += a
    a -= 1
print(sum)
```
What is the result of the code above?

(A) 10

(B) 0

(C) 55

(D) 1

(E) 54

下面的内容要按一下才会显示：
<cr type="hidden"><notice>隐藏内容功能在此无法正常显示，请移步至程谱 coderecipe.cn查看。</notice>E</cr>
