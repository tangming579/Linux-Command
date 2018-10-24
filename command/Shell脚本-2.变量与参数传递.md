# Shell变量

**定义与使用变量**

```
[me@linuxbox ~]$ my_name="tangming"
[me@linuxbox ~]$ echo ${my_name}
tangming
```

命名规则：

- 首个字符必须为字母（a-z，A-Z）。
- 中间不能有空格，可以使用下划线（_）。
- 不能使用标点符号。
- 不能使用bash里的关键字（可用help命令查看保留关键字）。

变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：

```
for skill in Ada Coffe Action Java do
    echo "I am good at ${skill}Script"
done
```

**Shell字符串**

字符串可以用单引号，也可以用双引号，也可以不用引号

单引号：

```
str='this is a string'
```

单引号字符串的限制：

- 单引号里的任何字符都会原样输出，单引号字符串中的变量是无效的；
- 单引号字串中不能出现单引号（对单引号使用转义符后也不行）。

双引号：

```
your_name='qinjx'
str="Hello, I know your are \"$your_name\"! \n"
```

双引号的优点：

- 双引号里可以有变量
- 双引号里可以出现转义字符

拼接字符串：

```
your_name="qinjx"
greeting="hello, "$your_name" !"
greeting_1="hello, ${your_name} !"
echo $greeting $greeting_1
```

获取字符串长度：

```
string="abcd"
echo ${#string} #输出 4
```

提取子字符串：

```
string="alibaba is a great company"
echo ${string:1:4} #输出liba
```

查找子字符串：

```
string="alibaba is a great company"
echo `expr index "$string" is`
```