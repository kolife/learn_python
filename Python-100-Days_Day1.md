# 基础学习
- turtle模块
import turtle

turtle.pensize(5)
turtle.pencolor('red')
turtle.forward(100)
turtle.left(180)
turtle.forward(50)
turtle.right(90)
turtle.forward(50)
turtle.right(180)
turtle.forward(100)
'''

turtle.right(90)
turtle.forward(50)
turtle.right(180)
turtle.forward(50)
'''
turtle.mainloop()


- 数据类型
• 整型：Python中可以处理任意大小的整数（Python 2.x中有int和long两种类型的整数，但这种区分对Python来说意义不大，因此在Python 3.x中整数只有int这一种了），而且支持二进制（如0b100，换算成十进制是4）、八进制（如0o100，换算成十进制是64）、十进制（100）和十六进制（0x100，换算成十进制是256）的表示法。
• 浮点型：浮点数也就是小数，之所以称为浮点数，是因为按照科学记数法表示时，一个浮点数的小数点位置是可变的，浮点数除了数学写法（如123.456）之外还支持科学计数法（如1.23456e2）。
• 字符串型：字符串是以单引号或双引号括起来的任意文本，比如'hello'和"hello",字符串还有原始字符串表示法、字节字符串表示法、Unicode字符串表示法，而且可以书写成多行的形式（用三个单引号或三个双引号开头，三个单引号或三个双引号结尾）。
• 布尔型：布尔值只有True、False两种值，要么是True，要么是False，在Python中，可以直接用True、False表示布尔值（请注意大小写），也可以通过布尔运算计算出来（例如3 < 5会产生布尔值True，而2 == 1会产生布尔值False）。
• 复数型：形如3+5j，跟数学上的复数表示一样，唯一不同的是虚部的i换成了j。实际上，这个类型并不能算作常用类型，大家了解下就可以了


- 变量（要求见名知意）
硬性规则：
变量名由字母（广义的Unicode字符，不包括特殊字符）、数字和下划线构成，数字不能开头。
大小写敏感（大写的a和小写的A是两个不同的变量）。
不要跟关键字（有特殊含义的单词，后面会讲到）和系统保留字（如函数、模块等的名字）冲突。
PEP 8要求：
用小写字母拼写，多个单词用下划线连接。
受保护的实例属性用单个下划线开头（后面会讲到）。
私有的实例属性用两个下划线开头（后面会讲到）。


-- 变量赋值及算数运算
a = 321
b = 123
print(a + b)
print(a - b)
print(a * b)
print(a / b)
print(a // b)
print(a % b)
print(a ** b)

-- type函数对变量的类型进行检查
a = 100
b = 12.345
c = 1 + 5j
d = 'hello, world'
e = True
print(type(a)) # <class 'int'>
print(type(b)) # <class 'float'>
print(type(c)) # <class 'complex'>
print(type(d)) # <class 'str'>
print(type(e)) # <class 'bool'>

-- 变量类型转换
int()：将一个数值或字符串转换成整数，可以指定进制。
float()：将一个字符串转换成浮点数。
str()：将指定的对象转换成字符串形式，可以指定编码。
chr()：将整数转换成ASCII编码对应的字符串（一个字符）。
ord()：将字符串（一个字符）转换成对应的ASCII编码（整数）

-- 用户输入变量

a = int(input('a = '))
b = int(input('b = '))
print('%d + %d = %d' % (a, b, a + b))
print('%d - %d = %d' % (a, b, a - b))
print('%d * %d = %d' % (a, b, a * b))
print('%d / %d = %f' % (a, b, a / b))
print('%d // %d = %d' % (a, b, a // b))
print('%d %% %d = %d' % (a, b, a % b))
print('%d ** %d = %d' % (a, b, a ** b))
说明：上面的print函数中输出的字符串使用了占位符语法，其中%d是整数的占位符，%f是小数的占位符，
%%表示百分号（因为百分号代表了占位符，所以带占位符的字符串中要表示百分号必须写成%%），字符串之
后的%后面跟的变量值会替换掉占位符然后输出到终端中，运行上面的程序，看看程序执行结果就明白啦。
{0}.format()格式，可参考[format介绍](https://www.runoob.com/python/att-string-format.html)
>>>"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
'hello world'
 
>>> "{0} {1}".format("hello", "world")  # 设置指定位置
'hello world'
 
>>> "{1} {0} {1}".format("hello", "world")  # 设置指定位置
'world hello world'

- 运算符
由高到低为优先级由高到低
运算符	描述
[] [:]	下标，切片
**	指数
~ + -	按位取反, 正负号
* / % //	乘，除，模，整除
+ -	加，减
>> <<	右移，左移
&	按位与
^ |	按位异或，按位或
<= < > >=	小于等于，小于，大于，大于等于
== !=	等于，不等于
is is not	身份运算符
in not in	成员运算符
not or and	逻辑运算符
= += -= *= /= %= //= **= &= `	= ^= >>= <<=`
说明： 在实际开发中，如果搞不清楚运算符的优先级，可以使用括号来确保运算的执行顺序

- 练习：
练习1：华氏温度转换为摄氏温度
# coding=utf-8
F = float(input('Please input F degree:'))
C = (F -32)/1.8
print("F {0} equal to C {1}:".format(F,C))

================ RESTART: C:/Users/ykf7020/Desktop/py3_try.py ================
Please input F degree:56
F 56.0 equal to C 13.333333333333332

练习2：输入圆的半径计算计算周长和面积
# coding=utf-8
import math
r = float(input('Please input r :'))
cycle_long = 2*r*math.pi
size = r**2*math.pi
print("cycle_long is {0}; 面积 is {1}:".format(cycle_long,size))
================ RESTART: C:/Users/ykf7020/Desktop/py3_try.py ================
Please input r :12
cycle_long is 75.39822368615503; 面积 is 452.3893421169302:

练习3：输入年份判断是不是闰年
# coding=utf-8
year = int(input('请输入年份: '))
# 如果代码太长写成一行不便于阅读 可以使用\对代码进行折行
is_leap = (year % 4 == 0 and year % 100 != 0) or \
           year % 400 == 0
print("{0}年是闰年：{1}".format(year,is_leap))


#day 1 学习内容如上。
