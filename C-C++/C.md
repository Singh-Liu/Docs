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
- [浮点数和正负数的应用](#浮点数和正负数的应用)
- [整数分解](#整数分解)
- [最大公约数](#最大公约数)
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
##浮点数和正负数的应用

```c
#include <stdio.h>

int main()
{
	int n;
	int i;
	double sum = 0.0;
	double sign = 1.0;
	
	scanf("%d", &n);
	for(i = 1; i <= n; i++){
		sum += sign/i;
		sign = -sign;
	}

	printf("f(%f)=%f\n", n, sum);

	return 0;
}
```  
[Back to Top](#c)
##整数分解
```c
#include <stdio.h>

int main()
{
	int x;
	scanf("%d", &x);

	x = 0;
	int mask = 1;
	int t = x;  

	while(t > 9){
		t /= 10;
		mask *= 10;
	}  

	printf("x=%d, mask=%d\n", x, mask);  

	do{
		int d = x / mask;
		printf("%d", d);
		if(mask > 9){
			printf(" ");
		}
		x %= mask;
		mask /= 10;
	}while(mask > 0);
	printf("\n");
	return 0;
}
```  
[Back to Top](#c)


##最大公约数
```c
#include <stdio.h>

int main()
{
	int a, b;
	int t;
	scanf("%d %d", &a, &b);
	int origa = a;
	int origb = b;  

	while(b != 0){
		t = a % b;
		a = b;
		b = t;
	}
	
	printf("%d和%d的最大公约数是%d。\n", origa, origb, a);	
	
	return 0;
}
```  

[Back to Top](#c)

##C语言的类型
粗体为C99的类型
- 整数
`char`、`short`、`int`、`long`、**`long long`**
- 浮点数
`float`、`double`、**`long double`**
- 逻辑
**`bool`**
- 指针
- 自定义类型  

###类型有何不同
- 类型名称：int、long、double
- 输入输出时的格式变化：%d、%ld、%lf
- 所表达的数的范围：char < short < int < float < double
- 内存中所占据的大小：1个字节到16个字节
- 内存中表达形式：二进制数（补码）[整型]、编码[浮点]  

###sizeof
一个运算符，给出某个类型或变量在内存中所占据的字节数。它是一个静态运算符，它的结果在编译时刻就决定了，所以不要在sizeof的括号里做运算，这些运算是不会执行的。
- sizeof(int)
- sizeof(i)

```c
int a = 6;
printf("sizeof(a)=%ld\n", sizeof(a++));//输出sizeof(a)=4
printf("a=%d\n", a);//输出a=6
```  

```c
int a = 6;
printf("sizeof(a)=%ld\n", sizeof(a+1.0));//输出sizeof(a)=8
printf("a=%d\n", a);//输出a=6
```  

###整数
- char：1字节
- short：2字节
- int：取决于编译器（CPU），通常的意义是“1个字”（字长为CPU寄存器的数据宽度，也是CPU和内存做数据交换时总线的数据宽度）
  - 64位系统下，编译器为了向前兼容，将int类型自动编译为4个字节的了，不同的编译器将int类型编译成不同长度的，因此使用什么编译器会决定int的长度，比如32位系统，tc下的int就是16位长度的，VC就是32位长度的。
- long：取决于编译器（CPU），通常的意义是“1或2个字”
- long long：8字节 

###补码
对于正整数a，-a的补码为a的二进制码取反之后再加1，符号位变化为1。-a
对于-a，其补码就是0-a，实际是2^n-a，n是这种类型的位数。补码的意义就是拿补码和原码可以加出一个溢出的“零”。正数a减负数b，运算时相当于，2^n+a再减去b的补码。如果是正负数相加，溢出位忽略，就是运算所得的结果。

在计算机系统中，数值一律用补码来表示和存储。原因在于，使用补码，可以将符号位和数值域统一处理；同时，加法和减法也可以统一处理。此外，补码与原码相互转换，其运算过程是相同的，不需要额外的硬件电路。

- 正整数的补码是其二进制表示，与原码相同。求负整数的补码，将其对应正数二进制表示所有位取反（包括符号位，0变1，1变0）后加1。负整数补码的补码就是该负整数的原码。例如，-1的原码为10000001，补码为11111111，补码的补码为10000001。
- 一个负整数（或原码）与其补数（或补码）相加，和为模。（“模”是指一个计量系统的计数范围。如时钟等。计算机也可以看成一个计量机器，它也有一个计量范围，即都存在一个“模”。例如，时钟的计量范围是0～11，模=12。表示n位的计算机计量范围是0～2^(n)-1，模=2^(n)。）
- 对一个整数的补码再求补码，等于该整数自身。
- 补码的正零与负零表示方法相同。
- 求负整数的绝对值并非对其补码再求补码，而是将其补码全部取反之后加1。  
- 8位整数的范围是(-2^7)  - (2^7-1)
- 整数做计算时是用补码来表达的。    

###unsigned
- 如果一个字面量常数想要表达自己是unsigned，可以在后面加u或者U，比如255U。
- 用l或者L表示long。
- unsigned的初衷并非扩展数能表达的范围，而是为了做纯二进制运算，主要是为了移位。    

###整数的输入输出
- 只有两种形式：int或long long
- %d：int
- %u：unsigned
- %ld：long long
- %lu：unsigned long long  

###8进制和16进制
- 一个以0开始的数字字面量是8进制
- 一个以0x开始的数字字面量是16进制
- %o用于8进制，%x用于16进制（小写x输出小写的16进制字母a, b, c, d, e, f，大写的X则输出大写的16进制字母）
- 16进制很适合表达二进制数据，因为4位⼆进制正好是⼀个16进制位；8进制的⼀位数字正好表达3位⼆进制  

###选择整数类型
- 为什么整数要有那么多种？
  - 为了准确表达内存，做底层程序的需要
- 没有特殊需要，就选择int
  - 现在的CPU的字长普遍是32位或64位，⼀次内存读写就是⼀个int，⼀次计算也是⼀个int，选择更短的类型不会更快，甚至可能更慢
  - 现代的编译器⼀般会设计内存对齐，所以更短的类型实际在内存中有可能也占据⼀个int的⼤⼩（虽然sizeof告诉你更小）
- unsigned与否只是输出的不同，内部计算是⼀样的  

###浮点数
- float 
  - 4字节 
  - 有效数字7 
  - scanf("%f", &a); 
  - printf("%f", a); printf("%e", a);//用科学技术法表达，e可以大写
- double 
  - 8字节 
  - 有效数字15 
  - scanf("%lf", &a); 
  - printf("%f", a); printf("%e", a);
  - double ff = 1E - 10;//可以用科学技术法赋值
- 靠近0的非常小的数字，在正负两端无法表达。
- 在%和f之间加上.n可以指定输出小数点后几位有效数字，这样的输出是做4舍5入的（测试结果显示并非完全按照四舍五入进行处理的，应该是近似四舍五入的方式处理，估计计算机运作方式的原因，无法精确作四舍五入）
  - printf("%.3f\n", -0.0049);//输出-0.005
  - printf("%.30f\n", -0.0049);//输出-0.004899999……18991
  - printf("%.3f\n", -0.00049);//输出-0.000
- 浮点数是不能作精确运算的，比如1.23元最好换算成123分，通过整数进行运算。
```c
//输出为“不相等！c=2.4679999352，或2.468000”，编程时，两浮点数判断是否相等，一般采用`fabs(f1-f2)<1e-8;`
int main()
{
	float a, b, c;
	a = 1.345f;
	b = 1.123f;
	c = a + b;
	if(c == 2.468)
		printf("相等\n");
	else
		printf("不相等！c=%.10f, 或%f\n",c ,c);
}

```

- 带小数点的字面量是double而非float，float需要用f或F后缀来表明身份
- 如果没有特殊需要，只使用double
- 现代CPU能直接对double做硬件运算，性能不会比float差，在64位的机器上，数据存储的速度也不比float慢

###字符类型
- char是一种整数，也是一种特殊的类型：字符。这是因为：
  - 用单引号表示的字符字面量： 'a', '1'
  - ''也是一个字符
  - printf和scanf里用%c来输入输出字符

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
- 编程时，在循环体内部对于边界条件要考虑设置诸如cnt、mask、finish等标志变量，用来控制循环内部语句的执行以及循环是否结束。

[Back to Top](#c)
