# The self-study of C programming

## 2 C语言概述

## 2.1 &2.2 示例与其解释

示例：

```c
#include <stdio.h>
int main(void)
{
    int num;
    num=1;

    printf("I am a simple ");
    printf("computer.\n");
    printf("My favorite number is %d because it is first.\n",num);

    return 0;
}
```

### 预处理器指令

```c
include
```

即在编译前C编译器会对代码做一些准备工作----preprocessing

### 编译器软件包的标准部分

```c
#include<stdio.h>
```

告诉编译器把后面文件中是内容包含在当前程序中。相当于把该文件的所有内容都输入到该行所在位置。相当于是复制粘贴的过程。stdio.h提供了键盘输入和屏幕输出的支持。其中包括printf()。

通常C程序顶部的信息集合被称为头文件----header。头文件帮助编译器将程序正确组合在一起



### 第一个被调用的函数

```c
main()
```

圆括号可以帮助识别是一个函数

```c
int main(void)
```

表示main()函数返回一个整数，void表示mian()不带任何参数。反正int和void的是ANSI C定义main()的一部分

void：因为一般函数名后面包含一些传入函数的信息。如果没有传递任何信息，里面的单词就会是void。

有些旧的C代码会写成main()。这个在C90勉强接受，但是在C99和C11标准不允许这样写

还有小部分编译器支持void main()写法，但不是所有。

只要坚持使用标准形式，可以将编译器移至到另一个编译器。可见C语言的可移植性



### 注释

```c
/*
123
*/

//123 or 123//
```

前者可以一行或者多行。主要缺陷在于，如果不小心删除中间一个注释符，将会导致第一个和最后一个匹配，导致注释内容错误。

后者仅限于单行，这种注释方法也普遍适用于C++和java



### 花括号、函数体和块

```c
{
    ...
}
```

所有C函数都使用花括号标记函数体的开始和结束。花括号还可以用于把函数中的多条语句合并为一个单元或块。相当于Pascal等语言中begin和end



### 声明

```c
int num;
```

声明---declaration

声明了两件事。1是有一个叫做num的变量。2是int表明num是一个整数，int是一种数据类型

num是一个标识符（identifier），也就是一个变量、函数或者其他实体的名称。

使用某个变量时候一定要提前声明它。



### 数据类型

简单说，就是将变量声明成整型或字符类型，计算机才能正确的储存、读取和解释数据。



### 命名

编译器只能识别前63个字符。对于外部标识符，只允许31个字符。反正，如果超过了字符长度，那么编译器可能将不同的两个名称视为一个，有可能不会



命名可以使用大小写字母、数字和下划线来命名。第一个字符必须是字符或者下划线，不能是数字。



但是操作系统和C库中经常使用以1个或2个的下划线字符开始的标识符。因此最好避免在自己的程序中使用这种名称。标准标签都已1-2个下划线字符开始，如库标识符。虽然使用它们不会有语法错误，但是会导致名称冲突。



C语言名称区分大小写。

补充：拓展字符集



### 赋值

Ex：

```c
num=1;
```

在执行int num的时候编译器在计算机内存中给变量num预留了空间。

然后执行改行代码的时候，把值存储到之前预留的位置。

这种语句是赋值表达式语句。实际上没有赋值语句，这种只能算是表达式语句



### 6种语句

- 标号语句
- 复合语句
- 表达式语句
- 选择语句
- 迭代语句
- 跳转语句



### printf()函数

```c
printf("I am a simple ");
printf("computer.\n");
printf("My favorite number is %d because it is first.\n",num);
```

圆括号中的内容是从main()函数传递给printf()函数的信息

第一行括号中的是函数的实际参数（是传递给函数的特定值）

而形式参数是函数中用于存储值的变量

当程序运行到这一行时候，控制权被转给已命名的函数，函数执行结束后，控制权被返回至主调函数（calling function）该例中是main()



### 转义字符（escape sequence）

转义序列用于表示难以表示或者无法输入的字符。比如用\n表示enter键、用\t表示tab键、用\b表示backspace键。

形式：\\+...



### return 0

有返回值的C函数要有return语句。如int main(void)就是要求返回一个整数。return 0这个语句以return关键词开始，后面是待返回的值。如果遗漏，程序在花括号体后面会自动返回0，但是不建议省略main函数末尾的return函数。并且不要在有其他返回值的函数中遗漏它。所以要养成习惯，将其看作统一代码的风格。

return语句是一种跳转语句



## 2.3 简单程序结构

程序是由一个或多个函数组成的，函数由函数头和函数体组成。函数头中包括传入该函数的信息类型和函数的返回类型。函数体被花括号括起来，由一系列语句、声明组成。

函数头

```c
int main(void)
```

函数体

```c
{
    int g;
    g=1;
    printf("%d is neat. \n",g);
    return 0;
}
```



## 2.4 提高程序的可读性技巧

1.选择有意义的函数名

2.写注释



## 2.5 进一步使用C

示例

```c
//fathm_ft.c---把2英寻转换成英尺
#include <stdio.h>
int main(void)
{
    int feet, fathoms;
    fathoms=2;
    feet=6*fathoms;
    printf("there are %d feet in %d fathoms!\n",feet, fathoms);
    printf("YEs, I said %d feet!\n",6*fathoms);

    return 0;
}
```

### 程序说明

开始处的一条注释给出文件名和程序目的。对以后浏览和打印程序有帮助



### 多条声明

可在声明中用逗号隔开两个变量。与将两个分开写，各自末尾加上分号的效果等价。



### 打印多个值

逗号，以及可以通过以计算形式输出



==1英寻=6英尺=1.8米==



## 2.6 多个函数

示例

```c
#include <stdio.h>
void butler(void);
int main(void)
{
    printf("I will summon the butler function.\n");
    butler();
    printf("Yes. Bring me some tea and writeable DVDs.\n");

    return 0;
}
void butler(void)
{
    printf("You rang, sir?\n");
}
```

三次出现函数butler()

第一次是函数原型（prototype），告知编译器在程序中要使用该函数

第二次以函数调用(function call)的形式出现在main()中

最后一次出现在函数定义(function defining)中，函数定义即函数本身的源代码



下面具体分析：

C90标准增加了函数原型。这是一种声明形式，告诉编译器正在使用某函数，因此函数原型也叫做函数声明(function declaration)。并且声明还指明了函数的属性，上例中第一个void表示butler函数没有返回值（但是通常情况下，被调用的函数会像主调函数返回一个值，butler()函数没有）

第二部分调用函数很简单，只要写出函数名和圆括号就可以了。

最后一部分是对butler函数的定义，和main函数形同。都包括了函数头和函数体。如果使用老式编译器这个示例中的括号中的所有void都要删掉，即void butler()。

并且执行函数与函数在程序中的位置有关，而不是定义的位置。所以把butler()函数定义放在main()函数定义之前，不会改变函数执行顺序，butler()函数仍然在两次printf()函数调用中间被调用。

C标准建议要为程序中用到的所有函数提供函数原型。标准include文件（包括文件）为标准库函数提供了函数原型。例如，在C标准中，stdio.h文件包含了printf()函数的原型



## 2.7 调试程序

一般编译器报错总是显示在下一行，所以如果报错某行缺少分数，请检查上一行。

错误一般有语法错误和语义错误。其中语法错误可以通过编译器的提示找出和修改，而语义错误只有在编译完后从程序的行为中表现出来。检查程序是否有语义错误要跟踪程序的状态，即检查程序每执行一步所有变量的值。

主要有三种方法来追踪程序状态--用来检查语义错误：

- 自己模拟计算机逐步执行程序
- 可以在程序中的关键点插入printf()语句监视制定变量值的变化。通过变化了解程序的执行情况。最后达到效果，可删除额外的printf()
- 使用调试器（debugger）。这是一种程序，让你一般般运行另一个程序，并检查程序的变量的值。



## 2.8 关键字和保留标识符

下表是C语言的关键字。粗体是C90新增，斜体是C99新增，粗斜是C11新增

| 1         | 2        | 3            | 4                    |
| --------- | -------- | ------------ | -------------------- |
| auto      | extern   | short        | while                |
| break     | float    | **signed**   | ***_Alignas***       |
| case      | for      | sizeof       | ***_Alignof***       |
| char      | goto     | static       | ***_Atomic***        |
| **const** | if       | struct       | ***_Bool***          |
| continues | *inline* | swicth       | ***_Complex***       |
| default   | int      | typedef      | ***_Generic***       |
| do        | long     | union        | ***_Imaginary***     |
| double    | register | unsigned     | ***_Noreturn***      |
| else      | restrict | void         | ***_Static_assert*** |
| **enum**  | return   | **volatile** | ***_Thread_local***  |

除了关键字不能充当标识符。还有一些保留标识符(reserved indentifier)---C语言已经注定它们的用途或保留它们的使用权，也不能随便使用。这些包括那些下划线字符开头的标识符和标准库函数名，如printf()。



## 3 数据与C

### 3.1 示例

```C
#include <stdio.h>
int main(void)
{
    float weight;
    float value;

    printf("Are you worth your weight in platinum?\n");
    printf("Let's check it out.\n");
    printf("Please enter your weight in pounds: ");

    scanf("%f",&weight);

    value=1700.0*weight*14.5833;
    printf("Your weight in platinum is worth $%.2f.\n",value);
    printf("You are easily worth that! If platinum price drops,\n");
    printf("eat more to maintain your value.\n");

    return 0;
}
```



### 3.2变量和常量数据

常量（constant）就是在整个程序的运行过程中没有变化

其他数据类型在程序运行期间可能会改变或者赋值，这些是变量（variable）。

上述程序中weight就是一个变量，而1700.00就是常量



### 3.3数据：数据类型关键字

见下表

| 最初K&R给出的关键字· | C90标准添加的关键字 | C99标准添加的关键字 |
| -------------------- | ------------------- | ------------------- |
| int                  | signed              | _Bool               |
| long                 | void                | _Complex            |
| short                |                     | _Imaginary          |
| unsigned             |                     |                     |
| char                 |                     |                     |
| float                |                     |                     |
| double               |                     |                     |

- int关键字主要用来表示基本的整数类型

long、short、unsigned、signed主要提供基本整数类型变式。

例如unsigned short int和long long int。

- char关键字主要用于指定字母和其他字符（如#、$、%和*）。除此之外，char也可以表示较小的整数。

- float double和long double表示带小数点的数

- _Bool类型表示布尔值（ture或false）

- _Complex和__Imaginary表示复数和虚数

按计算机的储存方式，主要包括两种基本类型：整形类型和浮点数类型



#### 3.3.1 整数和浮点数

对于计算机而言，两者的存储方式不同

#### 3.3.2 整数

计算机以二进制数存储整数

#### 3.3.3 浮点数

浮点数就是相当于在一个值后面加上一个小数点，所以8是整数，8.00是浮点数。书写浮点数的方式有很多



- 总的来说，计算机将浮点数分成小数部分和指数部分来表示并分开保存。虽然8和8.00在数值上是相同的，但是它们的储存方式不同。比如8.00就是0.8E1，0.8是小数部分，而1是指数部分。当然计算机是用二进制和2的幂来进行储存 的。
- 整数没有小数部分，浮点数有
- 浮点数表示范围比整数要大（
- 对于一些算术运算（如两个很大的数相减），浮点数损失的精度更多
- 浮点数无法表示任何区间上所有的点，通常上只是实际值的近似值，如8.0可能被储存为7.99999.
- 相比整数，浮点数运算速度更慢



### 3.4 C语言基本数据类型

#### int

```c
int hogs, cows, goats;
```

上述为声明int类型的变量，关于程序获取值，前面主要有2种方法。1是通过赋值`cows=2`。而是通过函数，如scanf()

下面是第三种方法：

##### 初始化变量

初始化（initialize）。

```c
int cows=32, goats=14;
```

所谓初始化就是给变量一个初始值。可以在声明中直接完成

<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220602191932092.png" alt="image-20220602191932092" style="zoom:67%;" />



简而言之，声明为变量创建和标记存储空间，并为其指定初始值

C语言把不含小数点和指数的指数都作为整数

##### 打印int值

在printf中使用%d。若遗漏，将会打印出内存中的任意值



##### 八进制和十六进制

这两个进制系统在表达与计算机相关的值时很方便。比如16进制的35的位组合(bit pattern)是00110101。这种对应关系使得16进制和二进制的转换非常方便。

- 0x或0X前缀表示十六进制值

- 0前缀表示八进制值



##### 显示八进制和十六进制（Octal and Hexadecimal）

```c
#include <stdio.h>
int main(void)
{
    int x=100;

    printf("dec=%d; octal=%o; hex=%x\n",x,x,x);
    printf("dec=%#d; octal=%#o; hex=%#x\n",x,x,x);

    return 0;
}
```



可见，十进制显示数字，使用%d；以八进制显示数字，使用%o；以十六进制显示数字，使用%x。

并且，如果想要显示各进制的前缀，必须加上#





##### 其他整数类型

C语言提供的3个附属关键字修饰基本整数类型：short、long和unsigned

- short int类型（或者简写成short）
  - 占用储存空间比int类型少，常用于较小数值的场合，以节省空间。short是有符号类型（signed）
- long int或者long
  - 占用储存空间比int类型多，适用于较大数值的场合。也是有符号的。
- long long int或者long long
  - C99标准加入，占用空间比long多，适用于更大数值场合。也是有符号
- unsigned int或者unsigned
  - 只用于非负值场合。这种类型和有符号类类型表示的范围不同。如，16位的unsigned int允许的取值范围是0~65535，而不是-32768-32767。
- 在C90标准中，添加了unsigned long int 和unsigned long 和unsigned short int 或 unsigned short。在C99标准中，又添加了unsigned long long int 或 unsigned long long
- 前面几个有符号的可以加或者不加signed



##### long常量和long long常量

八进制和十六进制常量常被视为int类型。如果值太大，编译器会尝试使用unsigned int。如果还不够大，编译器会依次使用long long或unsigned long long类型。

有些情况下，编译器以long类型储存一个小数字。C标准函数要求当把较小常量当作long类型对待的时候，可以在值的末尾田间l或者L后缀。

类似的，long long表示较小常量的时候要在末尾加上ll后缀LL。而ull、LLU、ULL表示unsigned long long。



关于整数溢出

首先%d是有符号的，而%u是没有符号的

然后unsigned int当出现溢出行为的时候，将会从0开始，而signed int则会从最小负数开始



##### 打印short、long、long long、和unsigned类型

打印unsigned int用%u转换，打印long类型，用%ld转换。如果系统中int和long大小相同就用%d就行。

%lx是16进制的long类型整数，%lo是8进制的long类型整数

对于short类型的整数，分别是%hd、%ho表示10和8进制。

并且l和h作为前缀可以和u一起使用

对于支持long long类型的系统，%lld和%llu分别表示有无符号的ll



#### char

##### 3.4.3

用于储存字符（如字母或标点符号）。从技术层面，由于char类型使用数字编码处理的处理储存的字符，所以实际上char储存的是整数而不是字符，即使用特定的整数表示特定的字符。

ASCII码：0~127——只需要7位。而char类型一般是8位。

![image-20220603133702403](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220603133702403.png)

C语言将1字节定义为char类型占用的bit

##### 3.4.3.1 声明char类型变量

```c
char response, latan;
```



##### 3.4.3.2 字符常量和初始化

```c
char grade='A';
```

其他情形

- char broiled；
  - 声明一个char类型的变量
- broiled=‘T’
  - 与上面加在一起，正确
- broiled=T；
  - 错误，T是一个变量
- broiled=“T”
  - 错误，“T”是一个字符串

##### 3.4.3.3 非打印字符

单引号只适用于字符、数字和标点符号。浏览ASCII表会发现，优先字符打印不出来，比如一些代表行为的字符（如，退格、换行、终端响铃或蜂鸣）。以下有三种方式表示这些字符：

- 使用ASCII码

  - ```c
    char beep=7;
    \\用来表示蜂鸣
    ```

- 使用符号序列（用来表示一些特殊符号的），称为转义序列（escape sequence）

  - <img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220602213333751.png" alt="image-20220602213333751" style="zoom:50%;" />

  当然，可以把转义序列赋给字符变量时，必须用单引号把转义序列括起来，如：

  ```c
  char nerf='\n';
  ```

  这样nerf的效果就是在打印机或者屏幕上另起一行

  - \a表示打印警报字符，蜂鸣是最常见的警报
  - \b表示退格
  - \f表示将活跃位置移至下一页开始处
  - \n表示将活跃位置移至下一行开始处
  - \r表示将活跃位置移至当前行开始处
  - \t表示将活跃位置移至下一个水平制表点（通常是第1、9、17、25个字符位置）
  - \v表示将活跃位置移至下一个垂直制表点
  - \\\表示反斜杠
  - \\'表示单引号
  - \\"表示双引号
  - \\?表示问号
  - \0oo表示8进制
  - \xhh表示16进制

上面的活跃位置指的是屏幕光标位置

并且关于最后两个它的作用，例如

如果编译器不识别报警字符(\a),就可以用八进制的ASCII码代替，如`beep='\007'`

- 第三种：（加上前面的八进制我觉得）并且从C90开始，我们还能使用16进制，具体是通过在反斜杠后面加上x或者X，然后跟着1~3位16进制数字

| 十进制 | 八进制 | 十六进制 | Ctrl符 | ASCII | Msg       |
| ------ | ------ | -------- | ------ | ----- | --------- |
| 0      | 000    | 00       | CTRL-@ | NUL   | —         |
| 1      | 001    | 01       | CTRL-A | SOH   | GTL       |
| 2      | 002    | 02       | CTRL-B | STX   | —         |
| 3      | 003    | 03       | CTRL-C | ETX   | —         |
| 4      | 004    | 04       | CTRL-D | EOT   | SDC       |
| 5      | 005    | 05       | CTRL-E | ENQ   | PPC       |
| 6      | 006    | 06       | CTRL-F | ACK   | —         |
| 7      | 007    | 07       | CTRL-G | BEL   | —         |
| 8      | 010    | 08       | CTRL-H | BS    | GET       |
| 9      | 011    | 09       | CTRL-I | HT    | TCT       |
| 10     | 012    | 0A       | CTRL-J | LF    | —         |
| 11     | 013    | 0B       | CTRL-K | VT    | —         |
| 12     | 014    | 0C       | CTRL-L | FF    | —         |
| 13     | 015    | 0D       | CTRL-M | CR    | —         |
| 14     | 016    | 0E       | CTRL-N | SO    | —         |
| 15     | 017    | 0F       | CTRL-O | SI    | —         |
| 16     | 020    | 10       | CTRL-P | DLE   | —         |
| 17     | 021    | 11       | CTRL-Q | DC1   | LLO       |
| 18     | 022    | 12       | CTRL-R | DC2   | —         |
| 19     | 023    | 13       | CTRL-S | DC3   | —         |
| 20     | 024    | 14       | CTRL-T | DC4   | DCL       |
| 21     | 025    | 15       | CTRL-U | NAK   | PPU       |
| 22     | 026    | 16       | CTRL-V | SYN   | —         |
| 23     | 027    | 17       | CTRL-W | ETB   | —         |
| 24     | 030    | 18       | CTRL-X | CAN   | SPE       |
| 25     | 031    | 19       | CTRL-Y | EM    | SPD       |
| 26     | 032    | 1A       | CTRL-Z | SUB   | —         |
| 27     | 033    | 1B       | CTRL-[ | ESC   | —         |
| 28     | 034    | 1C       | CTRL-\ | FS    | —         |
| 29     | 035    | 1D       | CTRL-] | GS    | —         |
| 30     | 036    | 1E       | CTRL-^ | RS    | —         |
| 31     | 037    | 1F       | CTRL-_ | US    | —         |
| 32     | 040    | 20       | —      | SP    | MLA0      |
| 33     | 041    | 21       | —      | !     | MLA1      |
| 34     | 042    | 22       | —      | "     | MLA2      |
| 35     | 043    | 23       | —      | 编号  | MLA3      |
| 36     | 044    | 24       | —      | $     | MLA4      |
| 37     | 045    | 25       | —      | %     | MLA5      |
| 38     | 046    | 26       | —      | &     | MLA6      |
| 39     | 047    | 27       | —      | '     | MLA7      |
| 40     | 050    | 28       | —      | (     | MLA8      |
| 41     | 051    | 29       | —      | )     | MLA9      |
| 42     | 052    | 2A       | —      | *     | MLA10     |
| 43     | 053    | 2B       | —      | +     | MLA11     |
| 44     | 054    | 2C       | —      | ,     | MLA12     |
| 45     | 055    | 2D       | —      | –     | MLA13     |
| 46     | 056    | 2E       | —      | 。    | MLA14     |
| 47     | 057    | 2F       | —      | /     | MLA15     |
| 48     | 060    | 30       | —      | 0     | MLA16     |
| 49     | 061    | 31       | —      | 1     | MLA17     |
| 50     | 062    | 32       | —      | 2     | MLA18     |
| 51     | 063    | 33       | —      | 3     | MLA19     |
| 52     | 064    | 34       | —      | 4     | MLA20     |
| 53     | 065    | 35       | —      | 5     | MLA21     |
| 54     | 066    | 36       | —      | 6     | MLA22     |
| 55     | 067    | 37       | —      | 7     | MLA23     |
| 56     | 070    | 38       | —      | 8     | MLA24     |
| 57     | 071    | 39       | —      | 9     | MLA25     |
| 58     | 072    | 3A       | —      | :     | MLA26     |
| 59     | 073    | 3B       | —      | ;     | MLA27     |
| 60     | 074    | 3C       | —      | <     | MLA28     |
| 61     | 075    | 3D       | —      | =     | MLA29     |
| 62     | 076    | 3E       | —      | >     | MLA30     |
| 63     | 077    | 3F       | —      | ?     | UNL       |
| 64     | 100    | 40       | —      | @     | MTA0      |
| 65     | 101    | 41       | —      | A     | MTA1      |
| 66     | 102    | 42       | —      | B     | MTA2      |
| 67     | 103    | 43       | —      | C     | MTA3      |
| 68     | 104    | 44       | —      | D     | MTA4      |
| 69     | 105    | 45       | —      | E     | MTA5      |
| 70     | 106    | 46       | —      | F     | MTA6      |
| 71     | 107    | 47       | —      | G     | MTA7      |
| 72     | 110    | 48       | —      | H     | MTA8      |
| 73     | 111    | 49       | —      | I     | MTA9      |
| 74     | 112    | 4A       | —      | J     | MTA10     |
| 75     | 113    | 4B       | —      | k     | MTA11     |
| 76     | 114    | 4C       | —      | L     | MTA12     |
| 77     | 115    | 4D       | —      | M     | MTA13     |
| 78     | 116    | 4E       | —      | N     | MTA14     |
| 79     | 117    | 4F       | —      | O     | MTA15     |
| 80     | 120    | 50       | —      | P     | MTA16     |
| 81     | 121    | 51       | —      | Q     | MTA17     |
| 82     | 122    | 52       | —      | R     | MTA18     |
| 83     | 123    | 53       | —      | S     | MTA19     |
| 84     | 124    | 54       | —      | T     | MTA20     |
| 85     | 125    | 55       | —      | U     | MTA21     |
| 86     | 126    | 56       | —      | V     | MTA22     |
| 87     | 127    | 57       | —      | W     | MTA23     |
| 88     | 130    | 58       | —      | X     | MTA24     |
| 89     | 131    | 59       | —      | Y     | MTA25     |
| 90     | 132    | 5A       | —      | Z     | MTA26     |
| 91     | 133    | 5B       | —      | [     | MTA27     |
| 92     | 134    | 5C       | —      | \     | MTA28     |
| 93     | 135    | 5D       | —      | ]     | MTA29     |
| 94     | 136    | 5E       | —      | ^     | MTA30     |
| 95     | 137    | 5F       | —      | _     | UNT       |
| 96     | 140    | 60       | —      | `     | MSA0,PPE  |
| 97     | 141    | 61       | —      | a     | MSA1,PPE  |
| 98     | 142    | 62       | —      | b     | MSA2,PPE  |
| 99     | 143    | 63       | —      | c     | MSA3,PPE  |
| 100    | 144    | 64       | —      | d     | MSA4,PPE  |
| 101    | 145    | 65       | —      | e     | MSA5,PPE  |
| 102    | 146    | 66       | —      | f     | MSA6,PPE  |
| 103    | 147    | 67       | —      | g     | MSA7,PPE  |
| 104    | 150    | 68       | —      | h     | MSA8,PPE  |
| 105    | 151    | 69       | —      | i     | MSA9,PPE  |
| 106    | 152    | 6A       | —      | j     | MSA10,PPE |
| 107    | 153    | 6B       | —      | k     | MSA11,PPE |
| 108    | 154    | 6C       | —      | l     | MSA12,PPE |
| 109    | 155    | 6D       | —      | m     | MSA13,PPE |
| 110    | 156    | 6E       | —      | n     | MSA14,PPE |
| 111    | 157    | 6F       | —      | o     | MSA15,PPE |
| 112    | 160    | 70       | —      | p     | MSA16,PPD |
| 113    | 161    | 71       | —      | q     | MSA17,PPD |
| 114    | 162    | 72       | —      | r     | MSA18,PPD |
| 115    | 163    | 73       | —      | s     | MSA19,PPD |
| 116    | 164    | 74       | —      | t     | MSA20,PPD |
| 117    | 165    | 75       | —      | u     | MSA21,PPD |
| 118    | 166    | 76       | —      | v     | MSA22,PPD |
| 119    | 167    | 77       | —      | w     | MSA23,PPD |
| 120    | 170    | 78       | —      | x     | MSA24,PPD |
| 121    | 171    | 79       | —      | y     | MSA25,PPD |
| 122    | 172    | 7A       | —      | z     | MSA26,PPD |
| 123    | 173    | 7B       | —      | {     | MSA27,PPD |
| 124    | 174    | 7C       | —      | \|    | MSA28,PPD |
| 125    | 175    | 7D       | —      | }     | MSA29,PPD |
| 126    | 176    | 7E       | —      | ~     | MSA30,PPD |
| 127    | 177    | 7F       | —      | DEL   | —         |

所以，例如'\x010'或'\x10'可以表示Ctrl+P



NB：

- 如果是用双引号括起来的字符集合，就无需用单引号将转义序列括起来，如“Hello！\007”
- 要注意数字和数字字符的区别如，4和‘4’，‘\007’和‘7’
- 能使用转义序列的时候用转义序列而不是ASCII码，如‘\f’和‘\014’。这样能提供较高的可移植性
- 关于为什么ASCII码前面要加\：主要是因为这样能显示程序员使用字符编码的意图，其次这样的转义序列还可以嵌入C的字符串中，就像`printf("Hello!\007\n")`



##### 3.4.3.4打印字符

使用%c指明待打印的字符。如果使用%d打印char，打印出的将会是整数，因为一个字符变量实际上是被储存为1字节的整数值。而%c则会告诉程序应该打印的是该整数值对应的字符。

可以用下面代码验证：

```C\
#include <stdio.h>
int main(void)
{
    char ch;

    printf("Please enter a character.\n");
    scanf("%c",&ch);
    printf("The code for the %c is %d\n",ch,ch);

    return 0;
}
```



<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220603144457579.png" alt="image-20220603144457579" style="zoom:67%;" />



##### 3.4.3.5 有符号还是没有符号

根据C90标准，C语言允许在关键字char前面使用signed或unsigned



#### _Bool

##### 3.4.4

用于表示布尔值，即逻辑值true和false。其中1为ture，0为false。所以_Bool类型实际上也是一种整数类型，但是原则上它只需要占用1为储存空间就够了

##### 3.4.5 可移植类型：stdint.h和inttypes.h

C99增加了上述两个文件。来确保C语言的类型在各系统中的功能相同

完整见附录参考资料VI



#### float、 double和long double

##### 3.4.6

#### <img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220603155036344.png" alt="image-20220603155036344" style="zoom:67%;" /> 

第一列是一般计数法，第二列是科学计数法，第三列是指数计数法（或称为e计数法），第三种是科学计数法在计算机中的写法

C标准规定：float类型必须包括至少前六位有效数字，且取值范围至少是10^-37^~10^37^

这里的有效数字指的是，比如33.333333的前六位数。

通常系统储存一个浮点数要占用32位，其中8位用于表示指数的值和符号，剩下24位用于表示非指数部分（也叫做尾数或有效数）及其符号

float是另一种浮点类型（双精度）。与float的最小取值范相同，但至少必须表示10位有效数字。一般情况下，它占用64位。一些系统将多出来的32位用来表示非指数部分，这样能增加有效数字的位数（即提高了精度），并且还减少了舍入误差。另一些系统把其中的一些位分配给指数部分以容纳更大的指数，从而增加可表示数的范围。

第三种类型是long double。可以满足比double类型更高的要求。不过，C只保证long double类型至少与double类型的精度相同

##### 3.4.6.1 声明浮点型变量

```c
float noah, jonah;
double trouble;
float planck=6.63e-34;
long double gnp;
```

##### 3.4.6.2 浮点型常量

`-1.56E+12`或者`2.87e-3`

当然正号可以忽略。

可以没有小数点或者整数部分如`2E5``19.28`，但是两者不能同时省略

可以省略小数部分和整数部分`3.E16``.45E-6`,但是不能同时省略两者

E或者e前面不要加空格

一般来说，赋值的时候`some=4.0*2.0`如果没有声明类型，就会默认为double类型，虽然这样系统能提高精度，但是运行速度也会被减慢

只要在后面加上f或者F，可以使之变成float类型；加上l或者L，可以使之成为long double类型



C99标准添加了新的浮点型常量格式--用十六进制表示浮点型常量。将p或者P（即p计数法）代替e或者E，用2的幂代替10的幂

`0xa.lfp10`表示（10+1/16+15/256)*1024

##### 3.4.6.3 打印浮点值

采用%f打印十进制计数法的float和double类型；采用%e打印指数计数法的浮点数，如果系统支持16进制格式的浮点数，可用a和A代替e和E；打印long double的时候要使用%Lf、%Le或%La转换说明

```c
#include <stdio.h>
int main(void)
{
    float aboat=3200.0;
    double abet=2.14e9;
    long double dip=5.32e-5;

    printf("%f can be written %e\n",aboat, aboat);
    printf("And it is %a in hexadecimal, powers of 2 notation\n.",aboat);
    printf("%f can be written %e\n.",abet, abet);
    printf("%Lf can nbe written %Le\n",dip,dip);

    return 0;
}
```



##### 3.4.6.4 浮点值的上溢和下溢

当出现上溢的时候，C语言规定给变量赋一个表示无穷大的特定值，而且在printf()显示该值为inf或infinity

如果是下溢，将会把它除以2.通常会减小指数部分。

NaN表示not a number



#### 3.4.7 复数和虚数类型

简而言之，C语言有三种虚数类型：float_Complex、double_Complex和long double_Complex

例如float_Complex,将会包含两个float类型的值，分别表示复数的实部和虚部。

三种虚数类型是float_Imaginary、double_Imaginary和long double_Imaginary

如果包含了complex.h头文件，就可以用complex代替__Complex，用imaginary代替__Imaginary



#### 3.4.8 其他类型

包括数组、指针、结构和联合



#### 3.4.9 类型大小

```c
printf("Type int has a size of %zd bytes.\n",sizeof(int))
```

程序与上行代码类似。一些不支持C99和C11的编译器可用%u和%lu代替%zd

具体我也不知道我的系统各个数据类型的位，懒得打了



### 3.5 使用数据类型

主要记住两点：

- 使用有意义的变量名
- 初始化变量应使用与变量类型相匹配的常数类型



```c
int cost=12.99;
float pi=3.1415926536
```

第一个将会丢弃（截断）小数部分

第二个会损失一些精度



部分公司和程序员有系统化的命名约定。例如，i_前缀表示int类型，us__前缀表示unsigned short类型



### 3.6 参数和陷阱

所谓参数就是传递给函数的信息。

例如，printf("Hello, pal"),就是调用了一个参数（字符串）

scanf("%d",&weight)调用两个参数

这两个函数与一般函数不同，参数的个数是可以变的

```c
#include <stdio.h>
int main(void)
{
    int n=4;
    int m=5;
    float f=7.0f;
    float g=8.0f;

    printf("%d\n",n,m);
    printf("%d %d %d\n",n);
    printf("%d %d \n",f,g);

    return 0;
}
```

<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604002057320.png" alt="image-20220604002057320" style="zoom:50%;" />



在vscode打入上面三种参数错误情况，命令行的输出图如上

- 第一个是参数太多
- 第二个是参数太少
- 第三个是值的类型不匹配

- 程序员要负责确保转换说明的数量和类型和后面参数的数量类型匹配



### 3.7 转义序列示例

```c
#include <stdio.h>
int main(void)
{
    float salary;

    printf("\aEnter your desired monthly salary:");
    printf("$________\b\b\b\b\b\b\b");
    scanf("%f",&salary);
    printf("\n\t$%.2f a month is $%.2f a year.",salary,salary*12.0);
    printf("\rGee!\n");

    

    return 0;
}
```



##### 3.7.1 程序运行情况

![image-20220604005027371](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604005027371.png)



##### 3.7.2 刷新输出

关于printf()函数何时把输出发送到屏幕？

最初，该语句把输出发送到一个叫做缓冲区(buffer)的中间储存区域。

然后缓冲区中的内容再不断被发送到屏幕。

C标准规定当缓冲区遇到换行字符或需要输入的时候，缓冲区的内容将会被发送到屏幕

例如scanf()

如果旧式编译器遇到scanf也不会强行刷新新缓冲区，遇到这种情况可以使用换行字符刷新新的缓冲区

```c
printf("Enter your desired monthly salary:\n")
%后面不变
```

当然还有一种刷新缓冲区的方法是使用fflush()函数



## 4 字符串和格式化输出

### 4.1 先导程序

```c
#include <stdio.h>
#include <string.h>
#define DENSITY 62.4
int main()
{
    float weight, volumn;
    int size, letters;
    char name[40];

    printf("Hi! What's your first name?\n");
    scanf("%s",name);
    printf("%s, what's your weight in pounds?\n",name);
    scanf("%f",&weight);
    size= sizeof name;
    letters=strlen(name);
    volumn=weight/DENSITY;
    printf("Well, %s, your volumn is %2.2f cubic feet.\n",name,volumn);
    printf("Also, your fisrt name has %d letters,\n",letters);
    printf("and we have %d bytes to store it.\n",size);

    return 0;
}

```



- 用数组（array）储存字符串（character string）。该程序中，用户输入的名被储存在数组中，该数组占用内存中40个连续的字节，每一个字节存储一个字符值
- %s来处理字符串的输入和输出。scanf()中一个有&一个没有
- C预处理器把字符常量DENSITY定义为62.4
- 用strlen()获取字符串的长度



### 4.2 字符串简介

定义：是一个或多个字符的序列

注意：双引号不是字符串的一部分；仅对编译器起到告知作用，与单引号在标识单个字符作用类似

#### 4.2.1 char类型数组和null字符

C语言没有专门用于储存字符串的变量类型，字符串被储存在char类型的数组中。数组由连续的储存单元组成，每一个单元储存一个字符

![image-20220604221049221](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604221049221.png)

数组末尾位置的字符是\0。这是空字符(null character)。用它来标记字符串的结束，空字符不是数字0，它是非打印字符。它的ASCII码值是（或等价于）0。所以，意味着数组容量必须至少比带储存字符串的字符数多1。留剩下的字节给空字符



数组可以看做一行连续的多个储存单元。更加正式的说，数组是同类型数据元素的有序序列。比如`char name[40]`。表示为char数据类型有40个连续的元素数量。

<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604221653020.png" alt="image-20220604221653020" style="zoom:50%;" />

#### 4.2.2 使用字符串

```c
#include <stdio.h>
#define PRAISE "You are an extraordinary being."
int main(void)
{
    char name[40];
    // name 是可以容纳40字符的数组

    printf("What's your name? ");
    scanf("%s", name);
    printf("Hello, %s. %s\n", name, PRAISE);

    return 0;
}
```

%s告诉printf()要打印字符串，它出现了两次。一个是来自储存的数组中，还有一个来自PRAISE

![image-20220604222800493](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604222800493.png)

关于上述输入两个单词后，只读取了Cheng。因为scanf()当遇到第一个空白(空格、制表符或换行符)时就不在读取输入

一般而言，根据%s转换说明，scanf()只会读取字符串中的一个单词而不是一整句。



###### 字符串和字符

字符串常量"x"和字符常量'x'是不同的。区别之一在于‘x’是基本类型(char),而"x"是派生类型(char数组)。区别之二是"x"实际上是由两个字符组成，'x'和空字符

<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220604224642148.png" alt="image-20220604224642148" style="zoom: 50%;" />

#### 4.2.3 strlen()函数

这个函数给出字符串中的字符长度。使用该函数需要加上`#inculde <string.h>`这个头文件,这个头文件中包含了多个和字符串有关的函数原型（一些ANSI之前的UNIX系统使用strings.h代替这个函数）

一般而言，C把函数库中相关的函数归为一类，并为每类函数提供一个头文件。例如，printf()和scanf()函数都隶属于标准输入和输出函数，使用stdio.h头文件。

strlen()函数知道哪里停止，不计入最后的空字符，且字符串中的字符数包括空格和标点符号。

然而sizeof运算符给出的数会更大，因为它把字符串末尾的空字符也计算在内了

关于sizeof后面是否使用圆括号，主要看类型还是特定值，如果是类型就要加圆括号，否则可有可无。尽管如此，还是建议所有情况下都使用圆括号。



### 4.3 常量和C预处理器

符号常量(symbolic constant)

- 常量名比数字表达的信息更多
- 当出现修改的时候，只需要改变符号常量的定义，不用在程序中查找使用常量的地方，逐一修改



创建符号常量的方法：

- 声明一个变量，然后将该变量设置为所需的常量
  - 这样做提供了符号名，但是由于是一个变量，程序可能无意间改变它的值

```c
float taxrate;
taxtate=0.015;
```

- 在预处理器定义常量

  - 编译程序的时候，所有的TAXRATE都会替换成0.015，这一过程被成为编译时替换(compile-time substitution)。所有在运行程序的时候，所有的替换已经完成，这样的常量也被称为明示常量(manifest constant)

  ![image-20220605092759017](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220605092759017.png)

```c
#define TAXRATE 0.015;
```

格式：

```c
#define Name value 
```

末尾不加分号；大写表示符号常量是C语言一贯的传统，可以增加程序的可读性。

还有一个不常用的命名约定：即在名称前带c_或者k__前缀来表示常量

符号常量的命名规则和变量相同

符号常量还能定义字符和字符串常量，前者用单引号，后者用双引号

```c
#define BEEP '\a'
#define TEE 'T'
#define ESC '\033'
#deine  OOPS "Now you have done it!"
```

注意不要写成：

`#define TOES = 20`

这样替换TOES的是=20，而不是20。



#### 4.3.1 const限定符

C90标准新增了const关键词，用于限定一个变量为只读，

```c
const int MONTHS=12;
```

这使得MONTHS成为一个只读值。是一个变量



#### 4.3.2 明示常量

头文件limit.h和float.h分别提供了于整数和浮点类型大小限制相关的详细信息。每一个头文件都定义了一系列供实现使用的明示常量。例如：

`#define INT_MAX +32767`

这些明示常量代表int类型可表示的最大值和最小值，如果系统使用4字节的int，下表为limit.h头文件给出的一些明示常量：

![image-20220605094609920](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220605094609920.png)



类似地，float.h头文件也定义了一些明示常量。把明示常量名中的FLT分别替换成DBL和LDBL两种，分别表示double和long double类型所对应的明示常量（假设系统使用2的幂来表示浮点数）：

![image-20220605094927164](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220605094927164.png)

例：

```c
#include <stdio.h>
#include <limits.h>
#include <float.h>
int main(void)
{
    printf("Some number limits for this system:\n");
    printf("Biggest int: %d\n",INT_MAX);
    printf("Smallest long long: %lld\n",LLONG_MIN);
    printf("One byte=%d bits on this system.\n",CHAR_BIT);
    printf("Largest double: %e\n",DBL_MAX);
    printf("Smallest normal float: %e\n",FLT_MIN);
    printf("float precision= %d digits\n",FLT_DIG);
    printf("float epsilon= %e\n",FLT_EPSILON);

    return 0;
}
```

<img src="C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606102036841.png" alt="image-20220606102036841" style="zoom:80%;" />



### 4.4 printf()和scanf()

它们能让用户与程序交流，它们是输入/输出函数，或简称I/O函数。printf()是输出函数，scanf()是输入函数。它们工作原理几乎相同，两个函数都使用格式字符串和参数列表。

#### 4.4.1 printf()函数

%d等这类符号叫做转换说明(conversion specification)。它们指定了如何把数据转换成可显示的形式。下面是ANSI C标准为printf()提供的转换说明:

![image-20220606103225743](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606103225743.png)

![image-20220606103239705](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606103239705.png)

#### 4.4.2 使用printf()

函数后面要打印的是几个待打印项。它们可以是常量、变量和在打印之前要计算的表达式。格式字符串也就是第一部分，包含了两种形式不同的信息：

- 实际要打印的字符
- 转换说明

关于如何在格式字符串中打印%，直接通过%%来实现。

#### 4.4.3 printf()的转换说明修饰符

![image-20220606103844937](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606103844937.png)

![image-20220606103854854](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606103854854.png)

注意：类型可移植性

sizeof运算符以字节为单位返回类型或值的大小。这应该是是某种形式的整数，但是标准指只规定该值是无符号整数。在不同现实中，它可以是unsigned int、unsigned long甚至是unsigned long long。因此，如果要用printf()函数显示sizeof表达式。根据不同系统，可能使用%u、%lu或%llu。这意味着要查找你当前系统的用法。如果把程序移植到不同的系统还要进行修改。鉴于此，C提供了可移植性更好的类型。首先，stddef.h头文件（包含在stdio.h头文件），把size_t定义成系统使用sizeof返回的类型。这被称为底层类型。其次，printf()使用z修饰符表示打印相应的类型。同样，C还定义了ptrdiff_t类型和t修饰符来表示系统使用的两个地址差值的底层有符号整数类型。



float类型的转换：

在K&R C中，表达式或参数中的float类型会被自动转换成double类型。一般而言，ANSI C不会这样做。然而，为了保护大量假设float类型的参数被自动转换成double的现有程序，printf()函数中所有float类型的参数(对未使用显式原型的所有C函数有效)仍自动转换成double类型。因此无论是K&R C还是ANSI C，都没有显示float类型值专用的转换说明。



![image-20220606105008009](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606105008009.png)

![image-20220606105018385](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606105018385.png)

##### 4.4.3.1 使用修饰符和标记的示例

先来看看字段宽度在打印整数时的效果。

```c
#include <stdio.h>
#define PAGES 959
int main(void)
{
    printf("*%d*\n",PAGES);
    printf("*%2d*\n",PAGES);
    printf("*%10d*\n",PAGES);
    printf("*%-10d*\n",PAGES);
    printf("*%010d*\n",PAGES);

    return 0;
}
```

![image-20220606105622782](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606105622782.png)

- 第一个：略
- 第二个由于待打印的整数有三位数字，所以字段宽度自动扩大以符合整数的长度。
- 第三个：由于有十个字段宽度，所以对应7个空格和3个整数，数字靠右
- 第四个，加了符号，靠左显示
- 第五个，由0来替换空格的字段宽度



再来看看浮点型格式

```c
#include <stdio.h>
int main(void)
{
    const double RENT=3852.99;
    
    printf("*%f*\n",RENT);
    printf("*%e*\n",RENT);
    printf("*%4.2f*\n",RENT);
    printf("*%7.2f*\n",RENT);
    printf("*%8.2f*\n",RENT);
    printf("*%3.1f*\n",RENT);
    printf("*%10.3f*\n",RENT);
    printf("*%10.3E*\n",RENT);
    printf("*%+4.2f*\n",RENT);
    printf("*%010.2f*\n",RENT);

    return 0;
}
```

![image-20220606105527413](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606105527413.png)

该程序使用了conse关键词，限定变量为只读。

- 第一个：系统默认字段宽度和小数点后面的系数均为系统默认设置，字段宽度是容纳待打印数字所需的位数和小数点后打印6位数字。
- 第二个，%e。默认情况下小数点左侧打印1个数字，在右侧打印6个数字，但是这样打印的数字太多了！
- 解决方法是指定小数点右侧显示的位数，程序后面五个例子就是这样做的
- 第八个：略
- 第九个，转换说明中包含了+号，这使得打印值前面多了一个代数符号。
- 最后一个，0填充来满足字段要求。

看看编译器如何打印不同大小的值

```c
#include <stdio.h>
int main(void)
{
    printf("%x %X %#x\n", 31, 31, 31);
    printf("**%d**% d**% d**%#4d\n", 42, 42, -42, 42);
    printf("**%5d**%5.3d**%05d**%05.3d**\n", 6, 6, 6, 6);

    return 0;
}
```

![image-20220606110511099](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606110511099.png)

- 第一行：略
- 第二行中，可见负号前面不产生前导空格。这样输出结果比较美观，因为打印出来的正值和负值在相同字段宽度下的有效数字位数相同。当然，符号至少占了一个空格如果扩大转换说明中字段宽度的大小，那么符号前面还是会有空格的。
- 第三行，第二个，使用前导空格0来满足最小位数要求，最后一个，如果0标记和精度一起出现，0标记会被忽略。



下面来看看字符串格式的示例：

```c
#include <stdio.h>
#define BLURB "Authentic imitation"
int main(void)
{
    printf("[%2s]\n",BLURB);
    printf("[%24s]\n",BLURB);
    printf("[%24.5s]\n",BLURB);
    printf("[%-24.5s]\n",BLURB);


    return 0;       
}
```

![image-20220606111023110](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606111023110.png)

- 第一个，字段宽度自动扩大
- 第二个默认靠右显示
- 第三个：只打印五个字符
- 第二个默认靠左显示

#### 4.4.4 转换说明的意义

转换说明把二进制格式储存在计算机中的值转换成一系列字符（字符串）以便于显示。

例如：数字76在计算机内部储存格式是二进制01001100.%d转换说明将它转换成字符7和6。%x转换说明把相同的值转换成十六进制计数法4c；%c转换说明把01001100转换成字符L、

转换（conversion）并不会把原始值（比如上面的例子就是01001100）改变，转换说明就是翻译说明。



##### 4.4.4.1 转换不匹配

```c
#include <stdio.h>
#define PAGES 336
#define WORDS 65618
int main(void)
{
    short num = PAGES;
    short mnum = -PAGES;

    printf("num as short and unsigned short: %hd %hu\n", num, num);
    printf("-num as short and unsigned short: %hd %hu\n", mnum, mnum);
    printf("num as int and char: %d %c\n", num, num);
    printf("WORDS as int, shortm and char: %d %hd %c\n", WORDS, WORDS, WORDS);

    return 0;
}
```



![image-20220606112417311](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606112417311.png)

- 第一行没问题，因为两个范围都没超出
- 第二行出现了，65200并非期望的336，这是由于有符号short int类型的值在我们的参考系统中的表达方式所致。首先，short int的大小是2字节；其次，系统使用二进制补码来表示有符号整数。这种方法0-32767代表它们本身，而数字32768-65535则表示负数，如果65535表示-1，那么65200正好表示-336。
- 第三行演示了把大于255的值转换成字符会发生什么情况。我们系统中，char是1字节，当printf()使用%c打印336，他只会查看336的两个字节中后，相当于用一个整数除以256，保留余数--即80.对应的ASCII值为字符P。用专业术语来说，该数字被解释成“以256为模（modulo 256）”，即该数字除以256取其余数。
- ![image-20220606113405630](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606113405630.png)

最后我们打印比short int类型最大整数（32767）更大的整数（65618）。这次计算机也进行了求模运算。相当于把它储存在4字节的int类型值，用%hd转换说明打印时printf()只使用最后两个字节。这相当于65618处于65536的余数，就是82.



混淆整型和浮点型

```c
#include <stdio.h>
int main(void)
{
    float n1 = 3.0;
    double n2 = 3.0;
    long n3 = 2000000000;
    long n4 = 1234567890;

    printf("%.1e %.1e %.1e %.1e\n", n1, n2, n3, n4);
    printf("%ld %ld\n", n3, n4);
    printf("%ld %ld %ld %ld\n", n1, n2, n3, n4);
    printf("%zd\n",sizeof(double));
    printf("%zd",sizeof(float));

    return 0;
}
```



![image-20220606115511185](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606115511185.png)

![image-20220606135214068](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606135214068.png)

- 第一行:
  - 第一个float会被转换成double类型，即n1被扩成8字节
  - 第二个
  - 第三个和第四个，虽然printf()查看发现都是4字节，但是它还会查看相邻的4字节，共8字节单元。接着，它将8字节单元的位组合解释成浮点数（把一部分位组合解释成指数）。因此即使两个位数正确，更转换说明解释出来的值也不同，最终得到的结果是无意义的值。
- 第二行
- 第三行
  - 第一个是vscode编译出来的结果，第二个是Dev-c编译出来的结果
  - 可见第一个的话，%ld不能正常输出float和double，但是long并没有受到影响，是正常输出的
  - 但是第二个输出显示，如果printf()语句有其他不匹配的地方，即使用对了转换说明也会出现虚假的结果。用%ld转换说明打印浮点数就会失败，但是在这里，long类型的数也失败了。问题出于C如何把信息传递给函数。具体情况因编译器实现而异。“参数传递”下面这一栏针对一个有代表性的系统进行讨论

信息传递：

参数传递机制因实现而异

函数调用告诉计算机把四个变量的值传递给程序。这是一个常见的参数传递方式。程序把传入的值放在栈(stack)的内存区域。计算机根据变量类型（不是转换类型）把这些值存入。因此n1（自动转换成了double）和n2各占用8个字节，而后面两个占用4个字节。然后，控制转到printf()函数。该函数根据转换说明(不是根据变量类型)从栈中读取值。%ld表示函数应该读取4字节，同理后面一个%ld也告诉函数读取4字节，就这样n1被读入输出函数中，同理后面两个读取n2的内容。总共解释成4个long类型的整数。

![image-20220606141133332](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606141133332.png)



##### 4.4.4.2 printf()的返回值

大部分C函数都有一个返回值，这是函数计算并返回给主调程序(calling program)的值。printf()函数也有一个返回值，它返回打印字符的个数，如果有输出错误，printf()则返回一个负值（旧版本会返回不同的值）

printf()的返回值是其打印输出的附带用途，通常很少用到，但在检查输出错误可能会用到。下面程序演示了如何确定函数的返回值：

```c
#include <stdio.h>
int main(void)
{
    int bph2o=212;
    int rv;

    rv=printf("%d F is a water's boiling point.\n",bph2o);
    printf("The printf() function printed %d characters.\n",rv);

    return 0;
}
```

rv=printf()的形式把printf()的返回值赋给rv。并且该计算是针对所有字符数，包括空格和不可见的换行符(\n)



##### 4.4.4.3 打印较长的字符串

- 可以在格式字符串后面那些待打印对象之间的逗号进行换行
  - 不可以在双引号里面，这样C编译器会报错：字符串常量中有非法字符。
- 可以用多个printf()函数，末尾不加换行符即可
- 通过反斜杠(\)和Enter(或return)键组合来段行。这使得光标移至下一行，而且字符串中不会包含换行符。但是要注意下一行代码必须从最左边开始。不然缩进内容将会成为字符串的一部分。

```c
printf("The printf() function printed \
%d characters.\n",rv);
```

- ANSI C引入的字符串连接。在两个用双引号字符括起来的字符串之间用空白隔开，C编译器会把多个字符串看作是一个字符串。

  ```c
      printf("Hello, young lovers, wherever you are.\n");
      printf("Hello, young "       "lovers"  ", wherever you are.\n");
      printf("Hello, young lovers"
      ", wherever you are.");
  ```

  上面三个是等效的



#### 4.4.5 使用scanf()

scanf()要做的是把输入的字符串转换成整数、浮点数、字符或字符串。而printf()正好与它相反

scanf()和printf()类似，也使用格式字符串和参数列表。scanf中()的格式字符串表明字符输入流的目标数据类型。两个函数主要的区别在于参数列表中。printf()函数使用变量、常量和表达式，而scanf使用指向变量的指针。主要是两个规则：

- 如果使用scanf()读取基本变量类型的值，在变量名前加上一个&
- 如果用scanf()把字符串读入字符数组中不用使用&

```c
#include <stdio.h>
int main(void)
{
    int age;
    float assets;
    char pet[30];

    printf("Enter your age, assets, and favorite pet.\n");
    scanf("%d %f",&age,&assets);
    scanf("%s",pet);
    printf("%d $%.2f %s\n",age,assets,pet);

    return 0;
}
```

scanf()把%f、%e、%E、%g和%G转换说明用于float类型，对于double类型要使用l修饰符。

![image-20220606155714857](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606155714857.png)

![image-20220606155725452](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606155725452.png)![image-20220606155735213](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606155735213.png)![image-20220606155753494](C:\Users\浅夏 hello\AppData\Roaming\Typora\typora-user-images\image-20220606155753494.png)













































## 15 位操作

### 15.1 二进制数、位和字节

以2为基底表示的数字被称为二进制数(binary number)

原因：数字计算机通过关闭和打开状态的组合来表示信息，这两种状态分别用0和1表示。

#### 15.1.1 二进制整数

| 7    | 6    | 5    | 4    | 3    | 2    | 1    | 0    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 0    | 1    | 0    | 0    | 1    | 0    | 0    | 1    |
| 128  | 64   | 32   | 16   | 8    | 4    | 2    | 1    |

C语言用byte表示储存系统字符集所需的大小，1byte包含8bit，

















































