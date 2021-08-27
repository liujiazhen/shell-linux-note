# Shell 流程控制
和 Java、PHP 等语言不一样，sh 的流程控制不可为空，如(以下为 PHP 流程控制写法)：
```php
<?php
if (isset($_GET["q"])) {
    search(q);
}
else {
    // 不做任何事情
}
```
在 sh/bash 里可不能这么写，如果 else 分支没有语句执行，就不要写这个 else。
## if else
### if
if 语句语法格式：
```shell
if condition
then
    command1 
    command2
    ...
    commandN 
fi
```
写成一行（适用于终端命令提示符）：
```shell
if [ $(ps -ef | grep -c "ssh") -gt 1 ]; then echo "true"; fi
```
末尾的 fi 就是 if 倒过来拼写，后面还会遇到类似的。
### if else
if else 语法格式：
```shell
if condition
then
    command1 
    command2
    ...
    commandN
else
    command
fi
```
### if else-if else
if else-if else 语法格式：
```shell
if condition1
then
    command1
elif condition2 
then 
    command2
else
    commandN
fi
```
以下实例判断两个变量是否相等：
```shell
a=10
b=20
if [ $a == $b ]
then
   echo "a 等于 b"
elif [ $a -gt $b ]
then
   echo "a 大于 b"
elif [ $a -lt $b ]
then
   echo "a 小于 b"
else
   echo "没有符合的条件"
fi
```
输出结果：
```
a 小于 b
```
if else 语句经常与 test 命令结合使用，如下所示：
```shell
num1=$[2*3]
num2=$[1+5]
if test $[num1] -eq $[num2]
then
    echo '两个数字相等!'
else
    echo '两个数字不相等!'
fi
```
输出结果:
```
两个数字相等!
```
