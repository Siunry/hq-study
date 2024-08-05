# 计算机体系

![img](https://note.youdao.com/yws/public/resource/fcaf003cf95f3c16d1e971c8bc89356b/xmlnote/WEB739157f260f25ccada53fcbba4ebc5d2/WEBRESOURCE43d5ae248bc5265d646eeba8f6075c01/64545)



# C语言概述



###### ![image-20240723134620268](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240723134620268.png)

![image-20240723141348875](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240723141348875.png)

![image-20240723141407758](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240723141407758.png)

# 进制

## 十进制

方便人们识别

无前缀

数字:1,2,3,4,5,6,7,8,9.

特点:逢十进一

## 二进制

方便计算机识别  0 低电平  1 高电平

前缀: 0b

数字: 0,1.



# C语言语法

​	C语言的本质就是对内存的操作

## 数据类型



### 基础类型

- char :一般用来存放字符.在内存中占一个字节的大小.==8位==      
  - char是有符号类型,最高位为1表示的是负数.
  - `signed char`: 有符号char    范围:0~127 (==-128~=127==)
  - `unsigned char`:无符号char 范围: -128~0 (==0~255==)

- short:用来存放一些小型的数据.在内存中占两个字节的大小.==16位==

​			signed short:有符号short 范围: (==-32768!32767==)

​			unsigned short:无符号short范围:(==0~65535==)

- int    :一般用来存放数字.在内存中占四个字节大小,32位

​		 signed int :有符号int 范围:(==-2^31 ~ 2^31^ -1==)

​		unsigned int :无符号int范围()

- long:在内存中占用4/8个字节的大小

32位机

64位机

- float:浮点数类型:占4个字节;单精度浮点类型
- double:浮点数类型:占8个字节;双精度浮点类型

 	0	    		0000 0000 						0000 0000 0000 0000 0000 000

符号位	指数位(默认为127,根据数字的指数加减)					存储小数内容

### 构造类型

数组[]		构造体struct		共用体union		枚举enum



### 指针类型

占4(32位机)/8(64位机)个字节

### 空类型

void :占用0字节.

## 隐式类型转换

在计算机中只有相同类型的数据才能进行计算

转换:==小范围 -->大范围==

double > float > unsigned long > long > usigned int > int 



##  变量

概念:程序运行中可以发生改变的量.

定义:	<存储类型><数据类型>标识符 = value;

- int number = 10;

- int number;

  number = 10;



### 标识符

![image-20240723163034614](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240723163034614.png)

### 关键字

![image-20240723164751122](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240723164751122.png)

## 常量

程序运行中不能发生改变的量称之为常量

类型:字符常量,整数常量,字符串常量,宏常量.

![image-20240724094825411](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724094825411.png)



### 整数常量

![image-20240724130411425](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130411425.png)



### 字符常量

![image-20240724130521952](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130521952.png)

![image-20240724130508775](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130508775.png)

### 浮点类型常量

![image-20240724130600470](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130600470.png)

![image-20240724130612124](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130612124.png)

### 字符串常量

![image-20240724130648016](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130648016.png)

![image-20240724130659491](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130659491.png)

### 宏常量

![image-20240724130728643](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130728643.png)

![image-20240724130752225](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130752225.png)

![image-20240724130801413](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724130801413.png)

### 输出函数 printf

printf: 格式化输出函数

使用方式:

`printf("格式控制串",需要输出的内容);`

功能:将需要输出的内容替换到对应的格式控制串中.

格式控制串:

​		%s : 输出的内容是个字符串

​		%c : 输出的内容是个字符

​		%ld:输出的类型是个long类型

​		%d :输出的类型是个int类型

​		%f :输出的内容是一个float类型

​		

## 数据存储

在内存中,数据都是以==补码==的形式存在的.

- 源码 
- 反码 
- 补码

## 运算符

### 单目运算符

![image-20240724154510625](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240724154510625.png)

### 算术运算符

- +
- -
- *
- /

- % 余法操作不能有小数和0

### 左/右移运算符

- 右移运算符 `>>`  二进制运算符,统一使用无符号数字运算.
  - 右移缩小数据 相当于将数据除以2 

- 左移运算符 `<<`  二进制运算符,统一使用无符号数字运算.
  - 左移缩小数据 相当于将数据乘以2 

​                                                                                                    

## 运算符

### 异或运算符



二进制运算符 需要按位进行计算

==相异为真,相同为假==

1. 两个相同的数字进行异或计算结果为0
2. 0异或任何数都等于任何数
3. 异或与顺序无关

### 或运算符

二进制运算符 需要按位进行计算

==有真为真,全假为假==



### 逻辑运算符

当某个操作数的值已经能够确定整个表达式的结果时，后续的操作数将不再进行计算。这种原则主要应用于逻辑与（&&）和逻辑或（||）运算符。

- 逻辑与 &&

  表达式1 && 表达式2

  ==同真即真,有假则假==

- 逻辑或 ||

  表达式1 || 表达式2

  ==有真即真,同假则假==

​		

### 条件运算符(三目运算符)

表达式1 ? code1 : code2;

判断表达式是否为真 为真则执行code1,为假则执行code2

### 赋值运算符

+=;

-=;

*=;

/=;

### 逗号运算符

result = (表达式1 ,表达式2,表达式3, ... , 表达式n);

- 使用 逗号运算符时必须使用括号.
- ()中每个表达式都会被运算.逗号运算符的结果是最后一个表达式的结果



运算符优先级



从高到低:==单算移关与 异或逻条赋==.

单 条 赋 从右向左计算.

## 输入输出

输入输出操作需要使用头文件`include <stdio.h>`

1. putchar()  ;   getchar()
2. puts()  ;  gets()
3. printf()  ;  scanf()

### putchar() getchar()

函数原型:

- int putchar(int c);

​	函数功能:

- 像终端(stdout)中输出一个字符     

​	函数参数:

- @c :需要输出的字符

​	函数返回值:

​			成功:返回输出字符的ASCII

​			失败: EOF

### puts()

 函数原型:

- int puts(const char *s); 

函数功能:    

- 输出一个字符串到终端中(stdout) 

函数参数: 

- @s: 需要输出到终端中的字符串. 

 返回值: 

- 成功: 输出到终端中的字符的个数   
- 失败: EOF(-1)

注意:    

-  puts是自动进行换行的.可以不写 '\n'; 



### printf()

​	函数原型:

- int printf(const char *format, ...);

​	函数功能:

- 输出一个格式化的字符串到终端

​	函数参数:

- @format:格式化字符串

- ... :可变参数,需要输入到格式化字符串里面的内容.

  格式化字符:

  - ==%d 有符号的十进制数字.==
  - %u 无符号十进制数字.
  - %o 无符号八进制整数.
  - %x 无符号十六进制整数
  - ==%c 单一字符==
  - ==%s 字符串==
  - ==%f 浮点数类型(保留小数点后六位)==
  - %ld long类型的数据
  - %lf long float类型的数据
  - %LF long double类型的数据
  - %e 科学计数法 float/double 类型
  - ==%#x 输出带前缀的十六进制的数字==
  - %#o 输出带前缀的八进制数字
  - %.nf n 是保留小数位数.

### scanf()

​	函数原型:

- int scanf(const char *format, ...);

​	函数功能:

- 从终端中接收指定格式的内容

​	函数参数:

- format :格式化输入的内容
- ... : 从终端中存放地址的位置
- 格式控制串
  - ==%d  有符号的整形==
  - ==% c 单一字符==
  - ==%s 字符串==    (中间不能有空格)
- scanf会将 space/enter 作为结束的语句
- scanf :支持同时输入多个内容:
  - scanf("%d%d%d%d%d%d",...);

==scanf("%d\n",number); 添加\n会造成输入数据后回车无法结束需要按任意字符才可结束.==

## 判断函数

### 单分支结构if语句

语法结构:

​	

```
if(condition)

{

	code;

}
```

语法含义:

1. 判断condition条件是否为真,如果为真,则执行code语句的内容.
2. 如果为假,则不执行code;

### 双分支语句结构if...else结构

格式:

```
if(condition)

{

	code1;

}
else
{
	code2;
}
```

语法含义:

​		 判断condition条件是否为真, 如果为真则执行 code1代码, 如果为假,则执行code2的代码.  



### 多分支结构 **if...else if ... else** 

语法格式:

```
 if (condition1)
 {
     code1;    
 }
 else if (condition2)
 {
      code2;    
 }
    ...
 else if (conditionN)
{
    codeN;    
}
else 
{
    code;    
}
```

语法执行:   

1. 判断条件 condition1 是否成立, 成立则执行 code1;        

   如果condition1 不成立 则判断 condition2是否成立,

   如果成立则执行code2,        如果condition2 不成立 则判断 condition3是否成立,如果成立则执行code3,       

    ....        

   如果conditionN 不成立 则判断 conditionN是否成立,如果成立则执行codeN, 如果所有的条件全部不成立,则会去执行else 语句.

### switch...case语句

语法格式:

```
switch (表达式)  // 表达式的结果必须是一个整形, 或者 字符常量. 
{
    case 常量1:
        code1;  // 执行语句
        break;
    ...
    case 常量N:
        codeN; // 执行语句
        break 
    default: 
        code; 
        break;
}
```

语法执行:    

1. 首先执行switch 后面的表达式,获取表达式的结果.    
2. 依次从上往下,向case 后面的常量进行比较, 比较成功则执行code语句.遇到break会退出      ==(case : 执行代码的入口, break 是出口.)==
3. 如果里面的case都不匹配的话则去执行default里面的内容.

注意:      

1. case击穿: 在switch case 语句中,case是入口, break是出口, 如果没有break, 只有 入口的话,那么switch case程序会一直执行到遇到break, 或者switch case这个语句结束.     
2. 无论default书写到switch case 当中的那一个位置,都是最后进行判断的. default 也是支持case击穿原则的, 遇到break才会退出. 如果default写在前面,则需要添加break. 
3.   switch   case  后面的表达式 都是常量.  

## 循环语句

### while循环

```
while(condition)  // 后面是不能有 ;    
    {
        code;    
    }
    //判断条件condition是否成立,成立则循环执行code语句,直到condition不满足为止.
```

### for循环

格式:

```
   for (表达式1; 表达式2; 表达式3)
    {
        code;  // 循环体    
    }
```

注意:    

- 表达式1:  一般情况下是赋值语句;   类似: int i = 0;         
- 表达式2:  判断条件;     类似:  i  < 101;    
- 表达式3:  改变循环的条件;  类似: i++; 

执行顺序:    

1. 首先执行表达式1;     
2. 判断表达式2 是否成立        
   1. i. 不成立: 直接退出循环.        
   2. ii. 成立: 则执行code循环体. 执行完循环体,在执行表达式3    
3. 重复b步骤,直到不满足条件退出循环为止. 

### 特殊的for循环

```
for 循环的格式: 
for (表达式1; 表达式2; 表达式3)
{
    code;
}

省略表达式1;
for(; 表达式2; 表达式3)  // right. 表达式1是空语句,所以表达式1不会被执行.
{    
    code;
}
eg: 
int i = 0;
for (; i< 5; i++)
{
    printf("hello world\n");
}

省略表达式2;
for(表达式1; ; 表达式3)  // right : 语法上这个是right,但是相当于没有判断条件这个是死循环.
{
    code;
}

省略表达式3;
for (表达式1;表达式2;)  // right : 没有控制循环的条件. 可以在循环体里面添加条件
{
    code;
}

省略表达式1, 表达式2, 表达式3
for(;;)   // right 死循环.
{
    code;
}
```

### do...while循环

语法格式:

```
  do 
    {
        code; //循环体语句;
    }while(condition);   // while(); 一定要有分号. 
语法含义:
    do..while 循环比较特殊: 第一次循环,无论条件是否成立,都会执行一次.如果条件成立,则继续执行,
    否则就不执行了.
    
```

### 关键字:break  &&   continue

- break: 在循环中使用,表示的含义是:跳出本循环.注意: break跳出的是最近的循环.
- break: 在循环中使用,表示的含义是:跳出本循环.注意: break跳出的是最近的循环.

### goto语法

语法含义:跳转到指定的标签操作

语法格式:

​			```goto 标签名;```

注意:     

1. goto 语句只能在本函数中使用. 不能跨函数函数跳转    
2.  goto 会破坏语法结果,尽量不去使用.

## 数组

1. 数组是一个构造类型. 数组是由多个相同类型的数据,组合生成一个全新的数组类型.

2. 数组在内存当中是一块连续的空间. 

3. 数组名: 是数组的首元素地址.  数组名是数字的首元素地址. scanf("%s", 数组名) 

4. 数组名: 是一个地址常量.  数组名是不可以 arr++ ; error   

5. 数组的类型:   int arr[5]; 这个数组的类型是 int[5]                

   ​                          int arr1[10];

### 数组定义



![image-20240801203250683](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203250683.png)

### 数组赋值与访问

![image-20240801203325700](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203325700.png)

### 数组初始化

![image-20240801203410978](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203410978.png)

![image-20240801203445321](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203445321.png)

### 字符串

![image-20240801203937669](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203937669.png)

![image-20240801203946905](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203946905.png)

![image-20240801203956118](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801203956118.png)

### 字符串相关函数

![image-20240801204012002](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801204012002.png)

![image-20240801204038239](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801204038239.png)

![image-20240801204046756](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801204046756.png)

![image-20240801204055294](C:\Users\Somnium\AppData\Roaming\Typora\typora-user-images\image-20240801204055294.png)

### 二维数组

定义二维数组的时候,是需要定义 行与列. 

二维数组的定义格式:    

​		`int arr[行][列];    `

#### 二维数组赋值和访问

```
1.初始化
    int arr[3][2] = {1, 2, 3, 4, 5, 6}; // 当成一维数组的方式进行赋值 
    int arr[3][2] = {0}; // 将二维数组当中每一个元素都初始化为 0 
    int arr[3][2] = {{1, 2}, {3, 4}, {5, 6}}; // 当成二维数组的方式进行赋值
    int arr[3][2] = {{1, 2, 3}, {4, 5, 6}};  // error 每一行有2个元素,不能插入3个值
    int arr[3][2] = { {1,}, {2,}, {3,}}; // 当成二维数组进行赋值,如果没有赋值的空间则默认赋值为 0
    // 特殊初始化: 二维数组的特殊初始化: 只能省略行, 不能省略列
    int arr[][2] = {{1, 2},{3, 4}};
    
2. 二维数组同样是支持下标进行赋值的. 
    int arr[3][4]; 
    arr[0][0] = 10; // 根据下标进行赋值,下标有2个,一个是行, 一个是列.
    arr[1][1] = 20;    
    
    
    二维数组同样支持下标进行访问: 
    数组名[行下标][列下标];
eg:
    定义一个二维数组: int arr[3][2] = {1, 2, 3, 4, 5, 6};
要求: 遍历一下二维数组arr;    
```



