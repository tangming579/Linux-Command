# 编写第一个Shell脚本

**什么是Shell脚本**

一个shell 脚本就是一个包含一系列命令的文件。shell 读取这个文件，然后执行文件中的所有命令，就好像这些命令已经直接被输入到了命令行中一样。

**第一个脚本**

启动文本编辑器，输入以下脚本

```
#!/bin/bash
# This is our first script.
echo 'Hello World!'
```

| 符号 | 说明                                                         |
| ---- | ------------------------------------------------------------ |
| #    | 注释，之后的所有字符都会被忽略                               |
| #!   | 一种特殊的结构叫做shebang。这个shebang 被用来告诉操作系统将执行此脚本所用的解释器的名字。每个shell 脚本都应该把这一文本行作为它的第一行。 |
| echo | 输出                                                         |

让我们把此脚本文件保存为hello world。

```
[me@linuxbox ~]$ ls -l hello_world
-rw-r--r-- 1 me me 63 2009-03-07 10:10 hello_world
[me@linuxbox ~]$ chmod 755 hello_world
[me@linuxbox ~]$ ls -l hello_world
-rwxr-xr-x 1 me me 63 2009-03-07 10:10 hello_world
```

对于脚本文件，有两个常见的权限设置；权限为755 的脚本，则每个人都能执行，和权限为700 的脚本，只有文件所有者能够执行。注意为了能够执行脚本，脚本必须是可读的。

执行脚本：

```
[me@linuxbox ~]$ ./hello_world
Hello World!
```

