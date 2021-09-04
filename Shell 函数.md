# Shell 函数
linux shell 可以用户定义函数，然后在shell脚本中可以随便调用。
shell中函数的定义格式如下：
```shell
[ function ] funname [()]

{

    action;

    [return int;]

}
```
说明：
- 1、可以带function fun() 定义，也可以直接fun() 定义,不带任何参数。
- 2、参数返回，可以显示加：return 返回，如果不加，将以最后一条命令运行结果，作为返回值。 return后跟数值n(0-255
