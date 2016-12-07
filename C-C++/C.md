#C
##目录
- [输入输出](#输入输出)
- [标识符和保留字](#标识符和保留字)
- [定义常量](#定义常量)
- [输入输出多个变量](#输入输出多个变量)
- [switch语句](#switch语句)
- [生成随机数](#生成随机数)
- [循环的选择](#循环的选择)
- [跳出多层循环](#跳出多层循环)
- [语法和技巧相关](#语法和技巧相关)

##输入输出
```C
scanf("%d", i) ;
```
`keyboard`-->`variable(store the data in the memory)`
以某种格式输入数据至内存中的变量
```C
printf("%d", i) ;
```
`variable`-->`monitor(get the data out of the memory)`
将内存中变量所存放的数据以某种格式输出

[Back to Top](#c)
##标识符和保留字
标识符（identifier）是指用来标识某个实体的一个符号。在不同的应用环境下有不同的含义。在编程语言中，标识符是用户编程时使用的名字，对于变量、常量、函数、语句块也有名字；我们统统称之为标识符。C语言中，标识符由字母（A-Z,a-z）、数字（0-9）、下划线“_”组成，并且首字符不能是数字，但可以是字母或者下划线。例如，正确的标识符：abc，a1，prog_to。不能把C语言关键字作为用户标识符，例如if ,for, while等.标识符对大小写敏感，即严格区分大小写。一般对变量名用小写，符号常量命名用大写。标识符命名应做到“见名知意”，例如，长度（外语：length），求和、总计（外语：sum），圆周率（外语：pi）……

保留字(Reserved Words)一般是等同于关键字(Keywords)的。从字面含义上理解，保留字是语言中已经定义过的字，使用者不能再将这些字作为变量名或过程名使用。而关键字则指在语言中有特定含义，成为语法中一部分的那些字。在一些语言中，一些保留字可能并没有应用于当前的语法中，这就成了保留字与关键字的区别。一般出现这种情况可能是由于考虑扩展性。例如，Javascript有一些未来保留字，如abstract、double、goto等等。它可能未来要增加直接跳转的功能，那么为了使当前版本的程序代码能向后兼容，所以不允许使用goto作为变量名，但当前版本的语言并不支持goto的直接跳转功能，它目前就不是关键字。

[Back to Top](#c)
##定义常量
定义常量，这个const的属性表示这个变量的值一旦初始化，就不能再修改了：
```c
const int AMOUNT = 100;
```

[Back to Top](#c)
##输入输出多个变量
```c
#include <stdio.h>

int main()
{
	int a = 0;
	int b = 0;

	printf("请输入两个整数：");
	scanf("%d %d", &a, &b);
	printf("%d + %d = %d\n", a, b, a + b);

	return 0;
}
```

[Back to Top](#c)
##switch语句
```c
switch(控制表达式){  //控制表达式只能是整数型的结果
case 常量:  //常量可以是常数，也可以是常数计算的表达式，比如1 + 1 或者 const int
  语句
  ……
case 常量:
  语句
  ……
case 常量:
  语句
  ……
default:
  语句
  ……
}
```
switch语句可以看作是一种基于计算的跳转，计算控制表达式的值后，程序会跳转到相匹配的case（分支标号）处。分支标号只是说明switch内部位置的路标，所以case并不能阻止程序往下执行，如果遇不到break或者switch结束，就会顺序执行下去。
```c
#include <stdio.h>

int main()
{
	printf("请输入月份：");
	int month;
	scanf("%d", &month);
	switch ( month )
	{
		case 1: printf("January\n"); break;
		case 2: printf("February\n"); break;
		case 3: printf("March\n"); break;
		case 4: printf("April\n"); break;
		case 5: printf("May\n"); break;
		case 6: printf("June\n"); break;
		case 7: printf("July\n"); break;
		case 8: printf("August\n"); break;
		case 9: printf("September\n"); break;
		case 10:printf("October\n"); break;
		case 11:printf("November\n"); break;
		case 12:printf("December\n"); break;
	}

	return 0;
}
```
```c
#include <stdio.h>

int main()
{
	printf("输入成绩（0-100）");
	int grade;
	scanf("%d", &grade);
	grade /=10;
	switch ( grade ) {
	case 10:
	case 9:
		printf("A\n");
		break;
	case 8:
		printf("B\n");
		break;
	case 7:
		printf("C\n");
		break;
	case 6:
		printf("D\n");
		break;
	default:
		printf("F\n");
	}

	return 0;
}
```

[Back to Top](#c)
##生成随机数
生成100以内的随机数：
```c
#include <stdio.h>


int main()
{
	srand(time(0));
	int a = rand();
	
	printf("%d\n", a%100);

	return 0;
}
```

[Back to Top](#c)
##循环的选择
- 如果有固定次数，用for
- 如果必须执行一次，用do_while
- 其他情况用while

##跳出多层循环
- 使用多个break语句跳出多层循环
```c
int main()
{
	for(){
		for{
			for{
				if{
					exit = 1;
					break;
				}
			}
		if(exit) break;
		}
	if(exit) break;
	}
	return 0;
}
```
- 使用goto语句跳出多层循环，从多重循环的内层跳到外层的时候，可以使用goto，其他地方建议尽量不要使用goto。

```c
#include <stdio.h>

int main()
{
	for(){
		for{
			for{
				if{
					goto out;
				}
			}
		if(exit) break;
		}
	if(exit) break;
	}
out:
	return 0;
}
```

[Back to Top](#c)

##语法和技巧相关
- 虽然C语言没有强制要求所有的变量都在定义的地方做初始化，但是所有的变量在第一次被使用之前应该被赋值一次。
- 语句是实现了某一种行为的，以分号结尾，当然有些复合语句是以右花括号结尾。
- 一个表达式是一系列运算符和算子的组合，用来计算一个值。表达式是由数字、算符、数字分组符号（括号）、自由变量和约束变量等以能求得数值的有意义排列方法所得的组合。（约束变量在表达式中已被指定数值，而自由变量则可以在表达式之外另行指定数值。）它的整体具有一个值，它不能独立存在，必须存在于某个语句中。
- 两个整数运算的结果只能是整数。
- %f和%lf分别是float类型和double类型用于格式化输入输出时对应的格式符号。
- 赋值顾名思义，做的是值传递。
- 正号`+`和负号`-`作为单目运算符，优先级高于`*`、`/`、`%`。
- `total *= sum + 12;`等价于`total = total * (sum + 12);`
- `++`和`--`对应的算子必须是变量。
- 运算符的结果为整数1或者0，关系判断为真时为1，假时为0。
- if, else if, else`进入各分支的判断条件是互不相容的。
- 在调试时可以考虑在代码中的某些位置临时加入`printf()`函数来帮助调试。
- 在循环语句中，循环条件的判断通常设置为对边界情况的判断，然后再以此来推导出其他参数，比如自增变量或者自减变量的初始值。
- break跳出循环，break语句只能跳出它所在的一层循环；continue跳出此轮循环剩下的语句进入下一轮循环

[Back to Top](#c)
