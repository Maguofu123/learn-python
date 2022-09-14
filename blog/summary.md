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
