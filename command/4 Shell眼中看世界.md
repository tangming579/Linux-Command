# Shell眼中看世界

**echo**：显示一行文本

```
[me@linuxbox ~]$ echo this is a test
this is a test
```

```
[me@linuxbox ~]$ echo D*
Desktop Documents
```

```
[me@linuxbox ~]$ echo [[:upper:]]*
Desktop Documents Music Pictures Public Templates Videos
```

```
[me@linuxbox ~]$ echo /usr/*/share
/usr/kerberos/share /usr/local/share
```

算术表达式展开：

```
[me@linuxbox ~]$ echo $((2 + 2))
4
```

花括号展开：

```
[me@linuxbox ~]$ echo Front-{A,B,C}-Back
Front-A-Back Front-B-Back Front-C-Back
```

```
[me@linuxbox ~]$ echo Number_{1..5}
Number_1 Number_2 Number_3 Number_4 Number_5
```

命令替换：

```
[me@linuxbox ~]$ echo $(ls)
Desktop Documents ls-output.txt Music Pictures Public Templates
Videos
```

双引号：比方说我们是不幸的名为 two words.txt 文件的受害者。如果我们试图在命令行中使用这个文件，单词
分割机制会导致这个文件名被看作两个独自的参数，而不是所期望的单个参数 

使用双引号，我们可以阻止单词分割，得到期望的结果；进一步，我们甚至可以修复破损的文件名 

记住，在双引号中，参数展开，算术表达式展开，和命令替换仍然有效 

单引号：如果需要禁止所有的展开，我们使用单引号 

# 键盘高级操作技巧

**命令行编辑**

| 按键   | 行为                                                 |
| ------ | ---------------------------------------------------- |
| Ctrl-a | 移动光标到行首                                       |
| Ctrl-e | 移动光标到行尾                                       |
| Ctrl-f | 光标前移一个字符；和右箭头作用一样                   |
| Ctrl-b | 光标后移一个字符；和左箭头作用一样                   |
| Alt-f  | 光标前移一个字                                       |
| Alt-b  | 光标后移一个字                                       |
| Ctrl-l | 清空屏幕，移动光标到左上角。clear 命令完成同样的工作 |

**修改文本**

| 按键   | 行为                                   |
| ------ | -------------------------------------- |
| Ctrl-d | 删除光标位置的字符                     |
| Ctrl-t | 光标位置的字符和光标前面的字符互换位置 |
| Alt-t  | 光标位置的字和其前面的字互换位置       |
| Alt-l  | 把从光标位置到字尾的字符转换成小写字母 |
| Alt-u  | 把从光标位置到字尾的字符转换成大写字母 |

**剪切与粘贴文本**

| 按键          | 行为                                                         |
| ------------- | ------------------------------------------------------------ |
| Ctrl-k        | 剪切从光标位置到行尾的文本                                   |
| Ctrl-u        | 剪切从光标位置到行首的文本                                   |
| Alt-d         | 剪切从光标位置到词尾的文本                                   |
| Alt-Backspace | 剪切从光标位置到词头的文本。如果光标在一个单词的开<br/>头，剪切前一个单词 |
| Ctrl-y        | 把剪切环中的文本粘贴到光标位置                               |

**自动补全**：敲入一个命令时，按下tab 键，自动补全就会发生 

**history**：搜索历史命令

```
[me@linuxbox ~]$ history | less
```

