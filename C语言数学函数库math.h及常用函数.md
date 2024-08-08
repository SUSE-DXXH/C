# C语言数学函数库<math.h>及常用函数

## 一、math.h

C语言中常用的一个数学函数库，里面涵盖了常用的数学运算，包括对实数及虚数的运算，如求绝对值、三角函数、两数中最大数等。使用时在程序开始处加入：

```c
#include <math.h>
```

库中的函数用法都很简单，传入的参数一般都是实数或虚数，包括整型、double、long double、float型等。

简单记忆前五即可

## 二、常用函数举例

#### 1、对数

##### （1）log(a)

用于求以e为底的自然对数

```c
double log( double arg );
float logf( float arg );
long double logl( long double arg );
```

##### （2）log10(a)

计算以10为底的对数

```c
double log10( double arg );
```

##### （3）logb/loga

计算以a为底b的对数

C语言中没有对任意底数求对数的函数，必须用换底公式转化

例如：表示log2^8如下：

log2^8=log8/log2    //转化为以e为底，也可化为以10为底

~~~c
#include <stdio.h>
#include <math.h>
int main()
{
    printf("%.6lf\n", log(8.0)/log(2.0));
    return 0;
}
~~~

#### 2、指数

```c
double pow（double base，double exponent）;
```

第一个参数是底数，第二个参数是指数，即返回值为  base^exponent

**exp(x)**： 返回基e的指数值，e^x

```c
double exp (double x);
```

#### 3、计算平方根

**sqrt()**： 计算平方根 

```c
double sqrt(double x);
```

#### 4、四舍五入成整数

**round()**： 四舍五入成整数

```c
round(2.3)=2, round(-2.5)=-3
```

#### 5、三角函数

x的正弦值

```c
double sin (double x);
```

 x的余弦值

```c
double cos (double x);  
```

x的正切值

```c
double tan (double x);  
```

#### 6、反三角函数

```c
double asin (double x); 
double acos (double x);
double atan (double x); 
```

#### 7、取整

取上整

```c
double ceil (double x); 
```

取下整

```c
double floor (double x); 
```

#### 8、求两者中最大/小值

##### 1、fmax(a, b)

两数中求最大值。

```c
double fmax( double x, double y );
```

传入参数可以是整型或double型，有变体函数，fmaxl、fmaxf，用法如下：

```c
float fmaxf( float x, float y );
long double fmaxl( long double x, long double y );
```

##### 2、fmin(a, b)

两数中求最小值，用法和fmax一样。

```c
double fmin( double x, double y );
float fminf( float x, float y );
long double fminl( long double x, long double y );
```

#### 9、求绝对值

##### 1、abs(a)

```c
#include <stdlib.h>
int  abs( int n );
```

这个函数可以求绝对值，但是它包含在<stdlib.h>头文件中，不要搞混了~

##### 2、fabs(a)

```c
#include <math.h>
double fabs （double arg）;
```

这个函数在math.h头文件中，传入参数可以是整型或double型，输出是double的。
