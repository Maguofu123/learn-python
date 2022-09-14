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
```try:
except [(Error1,Error2)] [as e]:
else```

`raise`用法
