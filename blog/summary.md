# Summary
## I/O流
`import os`导入os包

`os.path`
- 相对路径和绝对路径 ·`os.getcwd()   os.chdir()`
- .\\当前目录（文件夹） ..\\上一级目录（文件夹）
- `os.remove` 删除文件

`open(file, mode, buffering, encoding)` 创建或打开文件 mode包括r, b, a
- open属性， name, mode, encoding, closed
- read(), write(), seek(), tell()
- 注意关闭文件 file.close()

`with .. as ` 上下文管理器
执行完后自动关闭文件

pickle模块

## 异常处理
```
try:
except [(Error1,Error2)] [as e]:
else
```

`raise`用法

1. 单独一个 raise。该语句引发当前上下文中捕获的异常（比如在 except 块中），或默认引发 RuntimeError 异常。
2. 异常类名称：raise 后带一个异常类名称，表示引发执行类型的异常。
3. 异常类名称(描述信息)：在引发指定类型的异常的同时，附带异常的描述信息。

获取异常信息方法：
sys.exc_info()
返回一个元组，包括以下三个元素
type：异常类型的名称，它是 BaseException 的子类（有关 Python 异常类，可阅读《Python常见异常类型》一节）
value：捕获到的异常实例。
traceback：是一个 traceback 对象。

使用`traceback.print_tb(sys.exc_info()[2])`查看traceback中的内容

## 函数
- 值传递：数字，字符串，元组等无法改变的类型
- 引用传递：列表，字典等可变类型

**关于参数**
1. 关键字传参放在所有参数最后面
2. 默认参数放在所有没有默认值参数最后
3. `*args`表示创建一个名为 args 的*空元组*，该元组可接受任意多个外界传入的非关键字实参。 
4. `**kwargs`表示创建一个名为 kwargs 的*空字典*，该字典可以接收任意多个以关键字参数赋值的实际参数。
5. 若可变参数位于第一个位置，则位置参数必须用关键字传入

**逆向参数收集**
传入元组或列表带\*号，传入字典带\*\*号

*偏函数partial*
`from functools import partial`
`偏函数名 = partial(func, *args, **kwargs)`

***变量作用域***
局部变量（Local Variable），作用域仅限于函数内部，*函数的参数*也属于局部变量

全局变量（Global Variable），作用域为整个程序，两种方式
1. 在函数体外定义变量
2. 函数体内定义全局变量 `global a`，用global关键字修饰变量名不能直接赋初值
3. globals()查看全局变量，locals()查看局部变量

`vars()`查看object对象范围内所有的变量组成的字典

局部变量遮蔽全局变量

***局部函数***
通过返回值为函数的形式，可以扩大函数的作用域

***闭包***
提高程序运行效率，使代码简洁易读，外部函数的参数定义为自由变量

***lambda匿名函数***
`name = lambda [list] : 表达式`

## 迭代器
迭代器是支持迭代的容器类对象，例如list，tuple等
要实现迭代器，类中必须实现两个方法
1. `__next__(self)`返回容器中的下一个元素
2. `__iter__(self)`返回一个迭代器iterator

`iter()`返回一个迭代器
