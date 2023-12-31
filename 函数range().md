range()可以用来打印一系列数字

```python
for value in range(1,5):
    print(value)

1
2
3
4
```
 range() 只是打印数字1~4， 这是你在编程语言中经常看到的差一行为的结果。 函数range() 让Python从你指定的第一个值开始数， 并在到达你指定的第二个值
后停止， 因此输出不包含第二个值（这里为5） 。

- 使用range() 创建数字列表
要创建数字列表， 可使用函数list() 将range() 的结果直接转换为列表。 如果将range() 作为list() 的参数， 输出将为一个数字列表。
在前一节的示例中， 我们打印了一系列数字。 要将这些数字转换为一个列表， 可使用list() ：

```python
numbers = list(range(1,6))
print(numbers)

[1,2,3,4,5]
```

使用函数range() 时， 还可指定步长。 例如， 下面的代码打印1~10内的偶数：

```python
even_numbers = list(range(2,11,2))
print(even_numbers)

```
在这个示例中， 函数range() 从2开始数， 然后不断地加2， 直到达到或超过终值（11） ， 因此输出如下：
[2, 4, 6, 8, 10]


使用函数range() 几乎能够创建任何需要的数字集， 例如， 如何创建一个列表， 其中包含前10个整数（即1~10） 的平方呢？ 在Python中， 两个星号（** ） 表示乘方运算。 下面
的代码演示了如何将前10个整数的平方加入到一个列表中：
```python

squares = []
for value in range(1,11):
    square = value**2
    squares.append(square)
print(squares)
```

首先， 我们创建了一个空列表； 接下来， 使用函数range() 让Python遍历1~10的值。 在循环中， 计算当前值的平方， 并将结果存储到变量square 中。 然后， 将新计算得到的平方值附加到列表squares 末尾 。 最后， 循环结束后， 打印列表squares 
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

为让这些代码更简洁， 可不使用临时变量square ， 而直接将每个计算得到的值附加到列表末尾：
```python
squares = []

for value in range(1,11):
❶ squares.append(value**2)
print(squares)
```
❶处的代码与squares.py中❸处和❹处的代码等效。 在循环中， 计算每个值的平方， 并立即将结果附加到列表squares 的末尾。

创建更复杂的列表时， 可使用上述两种方法中的任何一种。 有时候， 使用临时变量会让代码更易读； 而在其他情况下， 这样做只会让代码无谓地变长。 你首先应该考虑的是， 编写清晰易懂且能完成所需功能的代码； 等到审核代码时， 再考虑采用更高效的方法。

# 创建数值列表

对数字列表执行简单的统计计算
有几个专门用于处理数字列表的Python函数。 例如， 你可以轻松地找出数字列表的最大值、 最小值和总和：
```python
>>> digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
>>> min(digits)
0>
>> max(digits)
9>
>> sum(digits)
45
```

 列表解析
前面介绍的生成列表squares 的方式包含三四行代码， 而列表解析让你只需编写一行代码就能生成这样的列表。
 列表解析 将for 循环和创建新元素的代码合并成一行， 并自动附加新元素。 面向初学者的书籍并非都会介绍列表解析， 这里之所以介绍列表解析， 是因为等你开始阅读他人编写的代码时， 很可能会遇到它们。
下面的示例使用列表解析创建你在前面看到的平方数列表：
```python

squares = [value**2 for value in range(1,11)]
print(squares)
```
要使用这种语法， 首先指定一个描述性的列表名， 如squares ； 然后， 指定一个左方括号， 并定义一个表达式， 用于生成你要存储到列表中的值。 在这个示例中， 表达式
为value**2 ， 它计算平方值。 接下来， 编写一个for 循环， 用于给表达式提供值， 再加上右方括号。 在这个示例中， for 循环为for value in range(1,11) ， 它将值
1~10提供给表达式value**2 。 请注意， 这里的for 语句末尾没有冒号。
结果与你在前面看到的平方数列表相同：

[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

要创建自己的列表解析， 需要经过一定的练习， 但能够熟练地创建常规列表后， 你会发现这样做是完全值得的。 当你觉得编写三四行代码来生成列表有点繁复时， 就应考虑创建
列表解析了。

动手试一试
4-3 数到20 ： 使用一个for 循环打印数字1~20（含） 。
4-4 一百万 ： 创建一个列表， 其中包含数字1~1 000 000， 再使用一个for 循环将这些数字打印出来（如果输出的时间太长， 按Ctrl + C停止输出， 或关闭输出窗口） 。
4-5 计算1~1 000 000的总和 ： 创建一个列表， 其中包含数字1~1 000 000， 再使用min() 和max() 核实该列表确实是从1开始， 到1 000 000结束的。 另外， 对这个列表
调用函数sum() ， 看看Python将一百万个数字相加需要多长时间。
4-6 奇数 ： 通过给函数range() 指定第三个参数来创建一个列表， 其中包含1~20的奇数； 再使用一个for 循环将这些数字都打印出来。
4-7 3的倍数 ： 创建一个列表， 其中包含3~30内能被3整除的数字； 再使用一个for 循环将这个列表中的数字都打印出来。
4-8 立方 ： 将同一个数字乘三次称为立方。 例如， 在Python中， 2的立方用2**3 表示。 请创建一个列表， 其中包含前10个整数（即1~10） 的立方， 再使用一个for 循
环将这些立方数都打印出来。
4-9 立方解析 ： 使用列表解析生成一个列表， 其中包含前10个整数的立方。