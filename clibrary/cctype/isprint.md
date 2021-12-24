函数

# isprint

&lt;cctype&gt;

`int isprint ( int c );`

#### 检查字符是否可打印(printable)

检查 _c_ 是否是一个可打印字符。


可打印字符会占据显示的打印位置（这和在函数 [iscntrl](iscntrl.md) 中返回 _true_ 的控制字符相反）。

对于标准 ASCII 字符集（在 "C" 环境中），可打印字符是 ASCII 值大于 0x1f (US)，但除了 0x7f (DEL) 的字符。


[isgraph](isgraph.md) 返回 _true_ 的情况和 [isprint](isprint.md) 一样，除了空格字符 (' ') 外，空格字符 (' ') 在 [isprint](isprint.md) 中返回 _true_，但在 [isgraph](isgraph.md) 中返回 _false_。

头文件 [&lt;cctype&gt;](README.md) 的参考中，有标准 ASCII 字符集的各个字符在不同 _ctype_ 函数的返回值的详细图表。

在 C++ 中，这个函数的 locale-specific 模板版本 [isprint](../../Other/locale/isprint.md) 在头文件 [&lt;locale&gt;](../../Other/locale/README.md)中。


## 参数

`c`

被检查的字符，被转化为 _int_ 型或 _EOF_。


## 返回值

如果 _c_ 的确是一个数字或字母，则返回一个非0值 (也就是 _true_ )，否则返回0 (也就是 _false_)。

## 例子

```cpp
/* isprint example */
#include <stdio.h>
#include <ctype.h>

int main()
{
	int i = 0;
	char str[] = "first line \n second line \n";
	while(isprint(str[i]))
	{
		putchar(str[i]);
		i++;
	}
	return 0;
}
```

这段代码追个字符输出一个字符串，直到遇到一个控制字符才跳出 while 循环。在这个例子中，只有第一行被输出，因为第一行以控制字符 '\n' (ASCII 值是 0x0a) 结尾，它不是一个可打印字符。


## 另请参阅

函数名                | 描述
--------------------- | ---------------
[iscntrl](iscntrl.md) | 检查字符是否是控制字符(control character) (_函数_)
[isspace](isspace.md) | 检查字符是否是空格符(white-space) (_函数_)
[isalnum](isalnum.md) | 检查字符是否是字母或数字(alphanumeric) (_函数_)
