# Shell脚本-流程控制

**if else**

和Java、PHP等语言不一样，sh的流程控制不可为空，如果else分支没有语句执行，就不要写else

```
x=5
if [ $x = 5 ]; then
echo "x equals 5."
else
echo "x does not equal 5."
fi
```

写成一行：

```
if [ $(ps -ef | grep -c "ssh") -gt 1 ]; then echo "true"; fi
```

末尾的fi就是if倒过来拼写

**for循环**

当变量值在列表里，for循环即执行一次所有命令，使用变量名获取列表中的当前取值。命令可为任何有效的shell命令和语句。in列表可以包含替换、字符串和文件名。

in列表是可选的，如果不用它，for循环使用命令行的位置参数。

```
for loop in 1 2 3 4 5
do
    echo "The value is: $loop"
done
```

**While语句**

```
#!/bin/sh
int=1
while(( $int<=5 )) do         echo $int         let "int++" done
```

运行脚本，输出：

```
1
2
3
4
5
```

while循环可用于读取键盘信息。下面的例子中，输入信息被设置为变量FILM，按<Ctrl-D>结束循环。

```
echo '按下 <CTRL-D> 退出'
echo -n '输入你最喜欢的电影名: '
while read FILM
do
    echo "是的！$FILM 是一部好电影"
done
```

**until 循环**

until循环执行一系列命令直至条件为真时停止。

until循环与while循环在处理方式上刚好相反。

一般while循环优于until循环，但在某些时候—也只是极少数情况下，until循环更加有用。

until 语法格式:

```
until condition
do
    command
done
```

条件可为任意测试条件，测试发生在循环末尾，因此循环至少执行一次—请注意这一点。

**case**

```
echo '输入 1 到 4 之间的数字:'
echo '你输入的数字为:'
read aNum
case $aNum in
    1)  echo '你选择了 1'
    ;;
    2)  echo '你选择了 2'
    ;;
    3)  echo '你选择了 3'
    ;;
    4)  echo '你选择了 4'
    ;;
    *)  echo '你没有输入 1 到 4 之间的数字'
    ;;
esac
```

**break与continue**

```
#!/bin/bash
while :
do
    echo -n "输入 1 到 5 之间的数字:"
    read aNum
    case $aNum in
        1|2|3|4|5) echo "你输入的数字为 $aNum!"
        ;;
        *) echo "你输入的数字不是 1 到 5 之间的! 游戏结束"
            break
        ;;
    esac
done
```