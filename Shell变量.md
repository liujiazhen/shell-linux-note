## Shell 变量
定义变量时，变量名不加美元符号（$，PHP语言中变量需要），如：
```
your_name="runoob.com"
```
注意，变量名和等号之间**不能有空格**，这可能和你熟悉的所有编程语言都不一样。同时，变量名的命名须遵循如下规则：
- 命名只能使用英文字母，数字和下划线，首个字符不能以数字开头。
- 中间不能有空格，可以使用下划线 _。
- 不能使用标点符号。
- 不能使用bash里的关键字（可用help命令查看保留关键字）。
有效的 Shell 变量名示例如下：
```
RUNOOB
LD_LIBRARY_PATH
_var
var2
```
无效的变量命名：
```
?var=123
user*name=runoob
```
除了显式地直接赋值，还可以用语句给变量赋值，如：
```
for file in `ls /etc`
或
for file in $(ls /etc)
```
以上语句将 /etc 下目录的文件名循环出来。
### 使用变量
使用一个定义过的变量，只要在变量名前面加美元符号即可，如：
```
your_name="qinjx"
echo $your_name
echo ${your_name}
```
变量名外面的花括号是可选的，加不加都行，加花括号是为了帮助解释器识别变量的边界，比如下面这种情况：
```
for skill in Ada Coffe Action Java; do
    echo "I am good at ${skill}Script"
done
```
如果不给skill变量加花括号，写成echo "I am good at $skillScript"，解释器就会把$skillScript当成一个变量（其值为空），代码执行结果就不是我们期望的样子了。
推荐给所有变量加上花括号，这是个好的编程习惯。
已定义的变量，可以被重新定义，如：
```
your_name="tom"
echo $your_name
your_name="alibaba"
echo $your_name
```
