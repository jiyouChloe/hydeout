---
layout: post
categories:
  - Computer Science
tags:
  - Computer Science
  - C programming
---
## 3. 입출력함수와 연산자(1) (교재 3장)

3-1. 표준 입출력 함수

* 함수란?

특정한 작업을 수행하도록 설계된 독립적인 프로그램

* C언어에서의 함수

> 표준함수 : C언어 자체에서 제공되는 함수.

> 사용자 정의 함수 : 사용자가 정의하여 사용하는 함수. 

* 표준 입출력 함수의 종류

> 표준 출력함수

1) printf() : 화면에 여러 종류의 자료를 출력.

			  printf("출력양식", 변수1, 변수2, ...);
			  
		    ex) printf("This is an example\n");
			
{% highlight js %}

#include <stdio.h> 
	
void main()
{
	char c = 'A';
	int i = 10, j = 20, k = 30;
	printf("간단한 출력 프로그램\n");
	printf("c=%c, c의 아스키 코드값은 %d\n",c,c);
	printf("i=%d, j=%d, k=%d",i,j,k);
	
}

{% endhighlight %}

// 출력결과 

간단한 출력 프로그램

c=A, c의 아스키 코드값은 65

i=10, j=20, k=30

|출력양식 변환기호|
<table>
  <thead>
    <tr>
      <th>%문자</th>
      <th>변환형식</th>
      <th>인자의 자료형</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>%d</td>
      <td>부호있는 10진 정수로 변환하여 출력</td>
      <td>정수형, 문자형</td>
    </tr>
    <tr>
      <td>%u</td>
      <td>부호없는 10진 정수로 변환하여 출력</td>
      <td>정수형, 문자형</td>
    </tr>
	<tr>
      <td>%f</td>
      <td>부동소수점형식으로 변환하여 출력</td>
      <td>실수형</td>
    </tr>
	<tr>
      <td>%e</td>
      <td>지수형태로 변환하여 출력</td>
      <td>실수형</td>
    </tr>
	<tr>
      <td>%c</td>
      <td>한 문자로 변환하여 출력</td>
      <td>정수형, 문자형</td>
    </tr>
	<tr>
      <td>%s</td>
      <td>문자열로 변환하여 출력</td>
      <td>문자열 포인터</td>
    </tr>
	<tr>
      <td>%o</td>
      <td>부호없는 8진수로 변환하여 출력</td>
      <td>정수형, 문자형</td>
    </tr>
	<tr>
      <td>%x</td>
      <td>부호없는 16진수로 변환하여 출력</td>
      <td>정수형, 문자형</td>
    </tr>
  </tbody>
</table>

{% highlight js %}

#include <stdio.h> 
	
void main()
{
	
	printf("양식 변환기호의 사용 예\n");
	printf("%c\n",'a');
	printf("%d\n",-123);
	printf("%o\n",123);
	printf("%x\n",123);
	printf("%X\n",123);
	printf("%f\n",123.456789);
	printf("%e\n",123.456789);
	printf("%s\n", "abcdefg");
	
}

{% endhighlight %}

// 출력결과

양식 변환기호의 사용 예

a

-123

173

7b

7B

123.456789

1.234568e+02

abcdefg

{% highlight js %}

#include <stdio.h> 
	
void main()
{

	printf("출력양식의 편집 예\n");
	printf("|%d|\n", 123);
	printf("|%5d|\n", 123);
	printf("|%-5d|\n", 123);
	printf("|%05d|\n", 123);
	printf("|%6.1f|\n", 123.45);
	printf("|%07.2f|\n", 123.45);
	/*
	출력양식의 편집 예
		|123|
		|  123|
		|123  |
		|00123|
		| 123.5|
		|0123.45|
	*/
}

{% endhighlight %}

2) putchar() : 화면에 1개의 문자를 출력.

3) puts() : 화면에 문자열을 출력.


> 표준 입력함수
 
1) scanf() : 키보드를 통해 여러 종류의 자료를 입력 받음.
	      
	      공백을 인식해여 첫번째 단어만 받아들임. 
	      
	      일반 변수일 경우에만 변수 앞에 &를 붙임. BUT 배열 등 주소값을 가지고 있는 변수는 &를 붙이지 않는다.

			scanf("입력양식", &변수1, &변수2, ...);
			
			ex) scanf("%d",&a);
			
{% highlight js %}

#include <stdio.h> 
	
void main()
{
	int jsu1,jsu2;
	float ssu1,ssu2;

	printf("\n정수를 입력하시오");
	scanf("%d %d", &jsu1, &jsu2);
	printf("\n실수를 입력하시오");
	scanf("%f %f", &ssu1, &ssu2);
	printf("\n정수는 %d %d\n", jsu1, jsu2);
	printf("\n실수는 %f %f\n", ssu1, ssu2);

	//출력결과
	/*
		정수를 입력하시오33
		44

		실수를 입력하시오33
		44

		정수는 33 44

		실수는 33.000000 44.000000
	*/

}


{% endhighlight %}

			
2) getchar() : 키보드를 통해 1개의 문자를 입력 받음.

   putchar('문자') : 한문자를 화면에 출력한다.

{% highlight js %}

#include <stdio.h> 
	
void main()
{
	//getchar(); : 한 문자를 키보드를 통해 입력받는다.
	char a;
	a = getchar();
	printf("\n%c\n", a);
	
	//putchar('문자'); : 한문자를 화면에 출력한다.
	char var = 'A';
	putchar(var);
	putchar(var + 1);
	putchar('\n');
	putchar('K');
	putchar('K' + 2);
	putchar('\007');
	
	//출력결과
	/*
	AB
	KM(삐소리가남)계속하려면 아무 키나 누르십시오 . . .
	*/
}

{% endhighlight %}

3) gets() : 키보드를 통해 문자열을 입력 받음.

{% highlight js %}

#include <stdio.h> 
	
void main()
{
	// gets() : 키보드를 통해 문자열을 입력 받음.
	char s[50];
	printf("문자열 입력?");
	gets(s);
	printf("gets()로 문자열 입력= %s\n", s);
	printf("문자열 입력?");
	scanf("%s", s); // 일반 변수일 경우에만 변수 앞에 &를 붙임. BUT 배열 등 주소값을 가지고 있는 변수는 &를 붙이지 않는다.
	printf("scanf()로 문자열 입력= %s\n", s);
		
	//출력결과
	/*
	문자열 입력?Computer Science
	gets()로 문자열 입력= Computer Science
	문자열 입력?Computer Science
	scanf()로 문자열 입력= Computer
	*/
}

{% endhighlight %}

4) puts(변수) : 문자열을 화면에 출력한다.

char s[50]="seoul";

puts(s);

{% highlight js %}

#include <stdio.h> 
	
void main()
{	// puts(변수) : 문자열을 화면에 출력한다.
	char s1[] = "Computer";
	char s2[] = "Science";
	puts(s1);
	puts(s2);
	printf("%s", s1);
	printf("%s", s2);
	//출력결과
	/*
	Computer
	Science
	ComputerScience
	*/
}

{% endhighlight %}


## 4. 입출력함수와 연산자(2) (교재 3장)

1. 연산자(operator)
 
 : 임의의 자료에 대해 각종 연산을 수행하도록 하는 기호. 

1) 산술 연산자

 : 피 연산자에 대해 사칙연산을 포함한 각종 산술연산을 수행하는 연산자
 
 -이항 연산자 : +,-,*,/,%
 
 -단항 연산자 : -(부호의 반전),--,++
 
 {% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int x, y;
	x = 10;
	y = 3;
	printf("x+y=%d\n", x + y);
	printf("x/y=%d\n", x/y);
	printf("x%%y=%d\n", x%y);
	printf("y%%x=%d\n", y%x);
	
	// 출력결과
	/*
	x+y=13
	x/y=3
	x%y=1
	y%x=3
	*/
}

{% endhighlight %}
 
{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int x = 5, a, b;
	a = ++x*x--;
	b = x * 10;

	printf("a=%d b=%d x=%d", a, b, x);
	//출력결과
	/*
	a=36 b=50 x=5
	*/
}

{% endhighlight %}

2) 관계 연산자

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int a = 4, b, c, d;
	b = a > 2;
	printf("b=%d\n", b);
	c = a < 2;
	printf("c=%d\n", c);
	d = a == 4;
	printf("d=%d\n", d);
	//출력결과 1: 참, 0:거짓
	/*
	b=1
	c=0
	d=1
	*/
}

{% endhighlight %}


3) 논리 연산자

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int a = 4, b = 7, c, d, e;
	c = a > 2 && b <= 7;
	printf("c=%d\n", c);
	d = a < 2 || b <= 7;
	printf("d=%d\n", d);
	e = !a; // C언어에서는 0은 거짓, 0이외의 값은 참.
	printf("e=%d\n", e);
	
	// 출력결과
	/*
	c=1
	d=1
	e=0
	*/
}

{% endhighlight %}

4) 대입 연산자

: 연산자의 오른쪽을 왼쪽에 대입하는데 사용

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int a = 10, b = 3, c = 1;
	a *= (b - 1);
	b /= 2 + 3;
	c += 2;
	printf("a=%d b=%d c=%d", a, b, c);

	//출력결과
	// a=20 b=0 c=3
}

{% endhighlight %}


5) 조건 연산자

: 주어진 조건의 만족 여부에 따라 지정된 수식을 수행하는 연산자

조건 ? 수식1 : 수식2;

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int a = 10, b;
	b = (a > 15) ? (a + 1) : (a - 1);
	printf("b=%d", b);
	// 출력결과
	// b=9
}

{% endhighlight %}

6) 비트 연산자


7) 기타 연산자

sizeof(자료) : 지정한 자료형, 수식, 변수가 차지하는 기억공간의 크기(byte)를 구함.

	ex ) sizeof(int)
		
		
cast(형변환) : 지정한 자료형을 다른 자료형으로 강제적으로 바꿈.

	ex ) (float)i/j 

& : 주소 연산자로서 피 연산자의 주소를 나타냄.

* : 내용 연산자로서 피  연산자의 내용을 가져옴.


{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	float a = 3.14;
	int b;

	printf("int형의 크기는=%d바이트\n", sizeof(a));
	printf("float형 변수 a의 크기는=%d바이트\n", sizeof(a));
	b = (int)a / 4;
	printf("b=%d", b);
	// 출력결과 (사용하는 컴퓨터의 성능에 따라서 값이 달라질 수 있음)
	/*
	int형의 크기는 = 4바이트
	float형 변수 a의 크기는 = 4바이트
	b = 0
	*/
}

{% endhighlight %}

8) 연산자 우선순위

z = x + y * 2 - ++x + (y += 3)

(y += 3) 소괄호연산 -> ++x 단항연산자 -> y*2 곱셈 -> 덧셈



## 5강. 선택제어문과 반복제어문 (교재 4장)

1. 선택 제어문

1) 프로그램 언어의 제어 구조

- 순차적 제어

  : 특별한 지정이 없는 한 위에서 아래로 수행된는 제어구조.	

- 선택적 제어

  : 주어진 조건에 따라 특정부분으로 수행을 옮기는 분기 제어구조.

- 반복적 제어 

 : 특정 부분을 일정한 횟수만큼 반복 수행하는 반복 제어구조.


2) 선택 제어문

- if 문

- switch ~ case 문

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	enum syllable {Do, Re, Mi, Fa} tone;
	for (tone = Do; tone <= Fa; tone+=1) {
		switch (tone)
		{
		case Do: printf("도는 하얀 도라지 \n");
			break;
		case Re: printf("레는 둥근 레코드 \n");
			break;
		case Mi: printf("미는 파란 미나리 \n");
			break;
		case Fa: printf("파는 파 \n");
			break;
		default:
			break;
		}
	}
}

{% endhighlight %}

- goto 문(무조건 분기) : 프로그램 수행 도중에 원하는 곳으로 제어를 무조건적으로 옮긴다.

Label : 

	goto Label;

	...
	
// 주의할 점 : if문, for문의 밖에서 안으로 호출할 수 없음. for문의 안에서 다른 for문의 안으로 호출 할 수 없음. 단, 안에서 밖으로는 가능. 
	
{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int i, n, c = 'A';
	while (1) {
		printf("\n 횟수는 ?");
		scanf("%d", &n);
		for (i = 1; i <= n; i++) {
			printf("%c", c);
			if (c=='Q')
				goto end;
			
			c++;
		}
	}
	end:
	printf("\n\n 끝 ");
}

{% endhighlight %}


2. 반복 제어문

반복 제어문의 종류 : for문, while문, do ~ while문

for(초기식; 조건식; 증감식){
	
}

for문에 {}중괄호가 없으면 최초 한문장만 반복시키고 다음문장은 반복 시키지 않음.

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int a, b;
	for (a = 1; a <= 3; ++a)
	{
		printf("a=%d\n", a);
		for (b = 0; b <= 4; b++)
			printf("b=%d",b);
		putchar('\n');
		
	}
	//출력결과
	/*
	a=1
	b=0b=1b=2b=3b=4
	a=2
	b=0b=1b=2b=3b=4
	a=3
	b=0b=1b=2b=3b=4
	*/
}

{% endhighlight %}


while(조건식){
	
}

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int i = 2, j = 0;
	while (i < 10) {
		j = 1;
		while (j < 10) {
			printf("%dx%d=%d\n", i, j, i*j);
			j++;
		}
		printf("\n");
		i++;
	}

	//출력결과
	/*
	2x1=2
	2x2=4
	2x3=6
	2x4=8
	2x5=10
	2x6=12
	2x7=14
	2x8=16
	2x9=18

	3x1=3
	3x2=6
	3x3=9
	3x4=12
	3x5=15
	3x6=18
	3x7=21
	3x8=24
	3x9=27

	4x1=4
	4x2=8
	4x3=12
	4x4=16
	4x5=20
	4x6=24
	4x7=28
	4x8=32
	4x9=36

	5x1=5
	5x2=10
	5x3=15
	5x4=20
	5x5=25
	5x6=30
	5x7=35
	5x8=40
	5x9=45

	6x1=6
	6x2=12
	6x3=18
	6x4=24
	6x5=30
	6x6=36
	6x7=42
	6x8=48
	6x9=54

	7x1=7
	7x2=14
	7x3=21
	7x4=28
	7x5=35
	7x6=42
	7x7=49
	7x8=56
	7x9=63

	8x1=8
	8x2=16
	8x3=24
	8x4=32
	8x5=40
	8x6=48
	8x7=56
	8x8=64
	8x9=72

	9x1=9
	9x2=18
	9x3=27
	9x4=36
	9x5=45
	9x6=54
	9x7=63
	9x8=72
	9x9=81
	*/

}

{% endhighlight %}

do{ 

	반복실행될 문장;

  }while(조건식);
  
  
반복문 내의 명령문을 실행한 후, 주어진 조건을 검사하여 반복 수행 여부를 결정한다.
  
{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int i = 0, n;
	int sum = 0;
	printf("n=?");
	scanf("%d",&n);

	do {
		sum = sum + i;
		i++;
	} while (i <= n);

	printf("i=%d\n", i);
	printf("i ~ %d까지 합 =%d\n", n, sum);

	// 출력결과
	/*
	n=?9
	i=10
	i ~ 9까지 합 =45
	*/
}

{% endhighlight %}

3. 기타 제어문

기타 제어문의 종류 : break문(루프를 빠져나옴), continue문(루프 선두로 올려줌)

break문은 자신이 포함된 반복문만 빠져 나옴.

{% highlight js %}

#include <stdio.h> 
	
void main()
{	
	int num, sum = 0;
	while (1) {
		printf("num(끝 : 0)...?");
		scanf("%d", &num);
		if (num == 1)
			break;
		sum = sum + num;
	}
	printf("\nsum=%d", sum);

	//출력결과
	/*
	num(끝 : 0)...?7
	num(끝 : 0)...?8
	num(끝 : 0)...?5
	num(끝 : 0)...?1

	sum=20
	*/
}

{% endhighlight %}


continue 문은 루프 실행 중에 루프를 다시 실행하고자 할 때 사용. switch ~ case 문에서는 사용하지 않고, 반복구조에만 국한되어 사용.

continue문은 그 루프의 선두로 제어를 옮겨 다음 반복을 실행.

{% highlight js %}

#include <stdio.h> 
#include <math.h>
	
void main()
{	
	int num = 1;
	while (num != 0) {
		printf("\n num=?");
		scanf("%d", &num);
		if (num < 0) {
			printf("0 : Negative number !\n");
			continue;
		}
		printf("Square root of %d = %f\n", num, sqrt(num));
	}

	printf("\n\n The end");

	//출력결과
	/*
	 num=?3
	Square root of 3 = 1.732051

	 num=?-3
	0 : Negative number !

	 num=?-10
	0 : Negative number !

	 num=?0
	Square root of 0 = 0.000000


	 The end
	*/
}

{% endhighlight %}


## 6강. 함수와 기억클래스(1)

1. 함수의 개념


1) 함수 : 특정한 작업(기능)을 수행하도록 설계된 독립적인 프로그램.

	  이러한 함수들이 정해진 순서에 따라 실행됨으로써 프로그램의 기능을 수행.

2) C 프로그램은 함수들로 구성

- 전체의 실행 내용을 몇 개의 모듈(module)로 분류.

- 각각의 모듈에 해당하는 내용을 함수로 작성.

- 실행순서에 따라 그 함수들을 차례로 호출하여 실행.

3) 함수의 특성

- 함수들은 서로를 자유로이 호출 가능.

- 모든 함수는 서로 독립적.

4) 함수의 장점

- 프로그램의 수정이 용이하다.

- 함수 재사용으로 코드 중복을 최소화한다.

- 프로그램의 기능을 한 눈에 파악할 수 있게 해줌으로써 유지관리가 쉽다.

5) 단위 프로그램을 하나의 함수에 기술한 경우

- 함수의 길이가 커짐.

- 프로그램의 가독성 문제.

- 수정의 어려움.

- 일부분만 재호출 어려움.

6) 기능별 독립된 단위(함수)로 구성한 경우(효율적)



2. 표준 함수(C언어 자체에서 제공하는 함수)


- 표준 함수의 원형은 헤더파일에 정의.

- 표준 함수의 실체는 라이브러리 파일에 수록.

- 표준함수를 사용하려면 원형이 선언되어 있는 헤더파일을 #include 시켜 주어야 한다.

 ex) int printf(const char*format, ...);
     
     int scanf(const char*format, ...);
     
     => 헤더파일에 정의되어 있음(stdio.h를 #include)
     
     double sin(double x);
     
     double cos(double x);
     
     => 헤더파일에 정의되어 있음(math.h를 #include)

 
 
3. 사용자 정의 함수(사용자가 정의하여 사용하는 함수)


1) C프로그램에서의 함수
  
- main()함수 안에 표준함수를 사용하는 형태.

- 그러나 동일 블록 내의 프로그램 길이가 길어지면 전체 프로그램은 복잡해지고 이해하기가 어려워진다.

- 따라서 전체 프로그램을 짧은 길이의 단위 프로그램으로 나누어 정의함으로써 프로그램의 작성과 이해를 쉽게 할 필요가 있다.

2) 사용자 정의 함수

- 사용자가 단위 프로그램을 함수로 정의하여 사용.

- 함수 정의의 구조

반환자료형 함수명( 자료형 매개변수1, 자료형 매개변수2, ...){함수몸체}

{% highlight js %}

int sum(int a, int b)
{
	int d;
	d = a + b;
	return(d);
}

{% endhighlight %}

3) 함수의 정의

- 함수 헤더(반환자료형)

반환자료형 함수명( 자료형 매개변수1, 자료형 매개변수2, ...)

int sum (int a, int b)

- 반환자료형 : 생략이 가능하며, 생략할 경우 자료형은 int로 간주. 반환값이 없는 함수인 경우는 void형으로 선언.

- 자료형과 매개변수 : 매개변수가 없으면 void형으로 사용.

- main()함수의 예

{% highlight js %}

//반환 자료형이 있는 경우 return값 명시
int main(void){

	printf("함수의 정의\n");
	
	return(d);

}

//반환 자료형이 void인 경우 return값 생략
//(void)와 ()는 동일 의미
void main(){

	printf("함수의 정의\n");

}

{% endhighlight %}

- 함수의 사용

함수의 원형 선언 -> 함수의 호출 -> 함수의 정의

{% highlight js %}

#include <stdio.h> 

// 함수에 대한 원형 선언 : 컴파일 되기 전에 컴파일러에게 이런 함수가 있다 알려줌.
int sum(int a, int b);

void main()
{
	int x, y, c;
	scanf("%d %d", &x, &y);
	
	// 함수의 호출
	c = sum(10, 20);
	printf("%d", c);
}

// 함수의 정의
int sum(int a, int b) {
	int d;
	d = a + b;
	return(d);
}

{% endhighlight %}

- 함수의 원형 선언

함수는 변수와 같이 사용되기 전에 미리 선언.

함수의 원형선언은 일반적으로 main()함수 이전에 한다.

원형선언은 함수정의 부분의 헤더부분에 세미콜론(;)만 추가하면 된다.

함수 원형선언은 함수와 관련된 3가지 성질을 선언.

> 함수의 반환형, 매개변수의 개수, 매개변수의 자료형.


- 함수의 원형선언이 필요없는 경우


{% highlight js %}

#include <stdio.h> 

// 피호출 함수가 main() 함수 이전에 선언된 경우
// 보통은 main() 함수 이후에 선언함.(가독성을 위하여)
int sum(int a, int b) {
	int d;
	d = a + b;
	return(d);
}

void main()
{
	int x, y, c;
	scanf("%d %d", &x, &y);
	
	// 함수의 호출
	c = sum(10, 20);
	printf("%d", c);
}

{% endhighlight %}

- 함수의 호출

실 매개변수 : 함수를 호출하는 함수(호출함수)에 쓰이는 매개변수.

형식 매개변수 : 호출당하는 함수(피 호출함수)에 쓰이는 매개변수.

* 실 매개변수와 형식 매개변수 사이에는 자료형과 변수의 개수가 일치해야 한다.

자료형이 일치하지 않을 경우는 형 변환이 발생.( 피호출함수 입장에서 바뀜)

개수가 일치하지 않을 경우 컴파일 에러가 발생.


## 7강. 함수와 기억클래스(2)


1. 매개변수 사이의 자료전달

1) 값에 의한 자료전달(call by value)

> 기본적인 자료전달 방법.

> 실 매개변수와 형식 매개변수 사이에 값의 전달.

> 호출한 함수의 실행이 끝난 다음 전달받은 값을 되돌려 받지는 못한다.

func(a,b);

...

func(int x, int y)

2) 참조에 의한 자료전달(call by reference)

> 호출함수와 피 호출함수의 매개변수 값을 서로 교환할 수 있는 자료전달 방법.

> 값을 전달하는 것이 아니라 실 매개변수의 값이 들어있는 주소 값이 전달된다.

fcn1(&a, &b);

...

int fcn1(int *x, int *y)

{% highlight js %}

#include <stdio.h> 

void swap(int x, int y);

void main()
{
	int a = 3, b = 5;
	printf("호출 전 a = %d, b = %d\n", a, b);
	swap(&a, &b);
	printf("호출 후 a = %d, b = %d\n", a, b);
}

void swap(int *x, int *y) {
	int temp;
	temp = *x;
	*x = *y;
	*y = temp;

	printf("함수 내 x = %d, y = %d\n", *x, *y);
}

//출력결과
/*
호출 전 a = 3, b = 5
함수 내 x = 5, y = 3
호출 후 a = 5, b = 3
*/

{% endhighlight %}


2. 기억클래스(storage class)

- 변수를 기억공간의 특정영역에 할당하는 방법.

- 즉, 각 변수의 유효범위와 존속기간을 설정.


1) 변수의 사용위치에 따라 지역변수, 전역변수로 나뉨.

* 지역변수(local variable)

> 특정 범위 내에서만 통용되는 변수.

> 선언된 블록이나 함수 내에서만 사용 가능.

> 함수에서 사용되는 매개 변수도 해당.


* 전역변수(global variable)

> 함수 밖이나 외부파일에서 선언되어 프로그램 전체에 걸쳐 사용될 수 있는 변수.

> 가급적 프로그램 선두에 위치하는 것이 좋음. 전역변수는 초기화 안 하면 0으로 자동 초기화.


* 전역변수와 지역변수의 비교

> 동일 범위 내에서는 지역변수가 우선

> 전역변수의 선언은 프로그램 선두에 위치

> 가급적 지역변수를 사용하는 것이 효율적
	
	- 함수의 독립성 향상

	- 디버깅 효율 향상
	
	- 기억 공간 절약
	
	
2) 변수의 기억클래스 종류

변수의 존속기간에 따라 자동변수(auto), 정적변수(static), 외부변수(extern), 레지스터(register) 변수로 나뉨.

* 형식 : 기억클래스 자료형 변수명;

* 기능 : > 기존의 변수 선언문에 기억클래스만 기입.
	
	 > 선언된 변수에 저장된 자료는 해당 기억영역에 놓이게 됨.
	 
* 사용예 : auto int a;

	  static int b;

	  extern int c;

	  register int d;

* 자동변수

> 함수 실행시 만들어지고, 실행이 끝나면 기억공간이 제거됨.

> 예약어 auto를 사용(생략 가능)

> 통용 범위는 변수가 선언된 블록이나 함수 내로 한정.

> 지역 변수에 해당.

> 초기화가 필요. (초기화 안 해주면 기존에 사용하던 값이 들어있을 수 있다)


* 정적변수

> 기억영역이 프로그램 끝날 때까지 유지

> 예약어 static을 사용

> 전역 변수에 해당

> 변수의 값은 프로그램 실행 중 계속 유지

> 초기화가 없으면 0으로 초기화 됨


* 외부변수

> 함수의 외부에서 선언

> 예약어 extern 을 사용

> 전역 변수에 해당

> 초기화가 없으면 0으로 초기화 됨

> 다른 파일에서 외부변수로 선언된 변수의 값을 참조할 수 있다


* 레지스터 변수

> CPU 내의 레지스터에 자료를 저장하고자 할 때

> 예약어 register 를 사용

> 자동 변수와 동일한 속성

> 프로그램의 실행속도 증가를 목적으로 사용(주로 반복문에서 카운터 변수로 사용)

> 빠른 효과를 내기 위하여...



## 8강. 배열와 포인터(1) (교재 6장)

1. 배열의 개념


> 100개의 자료처리를 위해


-지금까지 방법

100개의 변수 필요, 모든 변수 이름 기억, 자료처리 복잡

- 일관성 있고 효율적인 새로운 변수 필요

하나의 변수 이름에 순서에 의한 번호 부여,

변수명[1], 변수명[2], ..., 변수명[100]

효율적인 자료 처리 가능


2. 배열의 정의와 형태

1) 배열의 정의 

> 동일한 자료형을 갖는 자료들의 리스트

> 배열의 각 요소는 하나의 변수로 취급

> 배열은 배열명과 첨자로 구분


2) 배열의 선언 형태

> 1차원 배열 : 자료형 배열명[개수]  => int a[10] => 1차원 배열로서, 배열명은 a이고 배열의 크기는 10이며, 정수값이 기억됨.

- 배열의 첨자가 하나만 있는 배열

- 첨자의 개수는 배열 전체의 구성요소의 개수를 의미

- 배열의 각 요소는 배열명과 첨자로 구분 (첨자는 0부터 시작)

- 배열의 각 요소는 일반변수와 동일한 개념 (자료형과 기억 클래스는 갖는다)

* 1차원 배열의 초기화 : 배열을 선언하면 기억공간을 초기화 해야 함.

- 배열선언 후 초기값 할당
	
	int array[4]; // 한번에 초기화 하는 것이 아니므로 배열의 크기 생략 불가
	
	array[0] = 10;
	
	array[1] = 20;
	
	array[2] = 30;
	
	array[3] = 40;

- 배열선언과 동시에 초기값 할당
	
	int array[4] = {10,20,30,40}; // 배열의 각 요소에 초기값 할당
	
	int array[ ] = {10,20,30,40}; // 배열의 크기 생략 가능
	
	int array[4] = {10,20,30, }; // array[3] = 0 으로 초기화
	
	int array[4] = {10, ,30,40}; // 에러발생
	
	int array[4] = {10,20,30,40,50}; // 초기값이 배열의 크기보다 많으면 에러 발생
	
	
- 외부로부터 자료를 입력 받아 초기화

{% highlight js %}

	int x[10];
	
	for(i=0; o<10; i++){
		
		scanf("%d", &x[i]);
	
	}
	
{% endhighlight %}


{% highlight js %}

#include <stdio.h> 

void main()
{
	static int x[] = { 1,2,3,4 };
	static int y[] = { 10,20,30,40 };

	int i, z[4];

	for (i = 0; i < 4; ++i)
		z[i] = x[i] + y[3 - i];
	printf("반대 위치의 배열요소 합\n");

	for (i = 0; i < 4; ++i)
		printf("%d + %d = %d\n", x[i], y[3 - i], z[i]);

	//출력결과
	/*
	반대 위치의 배열요소 합
	1 + 40 = 41
	2 + 30 = 32
	3 + 20 = 23
	4 + 10 = 14
	*/
}

{% endhighlight %}


> 2차원 배열 : 자료형 배열명[행의 수][열의 수]  => int a[3][4] => 2차원 배열로서, 배열명은 a이고 3행 4열로 된 12개의 요소를 가진 정수형 배열.

- 2차원 배열의 선언과 초기화

int array[3][3] = {1,2,3,4,5,6,7,8,9}; //가능하지만 아래의 표현이 가독성이 더 높은 방법.

int array[3][3] = {{1,2,3},{4,5,6},{7,8,9}};


{% highlight js %}

void main()
{
	static int score[4][3] = { {90,90,90},{80,80,80},{70,70,70},{60,60,60} };

	int sum, i, j;
	printf("번호 국어 수학 영어 합계\n");
	for (i = 0; i < 4; ++i) {
		sum = 0;
		printf("%-7d", i+1);
		for (j = 0; j < 3; j++) {
			printf("%-7d", score[i][j]);
			sum += score[i][j];
		}
		printf("%-7\n", sum);
	}
	//출력결과
	/*
	번호 국어 수학 영어 합계
	1      90     90     90
	2      80     80     80
	3      70     70     70
	4      60     60     60
	*/
}

{% endhighlight %}


> 3차원 배열 : 자료형 배열명[면의 수][행의 수][열의 수] => int a[2][3][4] 
		
	       => 3차원 배열로서, 배열명은 a이고 2면 3행 4열로 된 24개의 요소를 가진 정수형 배열.

int a[2][3][4] = {{{1,2,3,4},{5,6,7,8},{9,10,11,12}},{{13,14,15,16},{17,18,19,20},{21,22,23,24}}};


> char형 배열 : char 배열명[문자열 길이 + 1] => char str[12] => 배열명이 str이고, 12문자 길이를 가진 char형 배열

배열의 크기가 문자열 길이 + 1 인 이유: 문자열이 기억공간에 보관될 때 null문자가 자동적으로 마지막에 추가 되기 때문에.

- char형 배열선언과 초기화 

char name[] = "HONG GIL DONG"; // ""라고 되어있으므로 문자열을 의미, null 문자, 공백 포함 14개의 기억공간을 선언. 문자열 단위로 초기화.

char address[] = {'S','E','O','U','L','\0'};

{% highlight js %}

void main()
{
	char name[] = "HONG GIL DONG"; 

	char address1[] = { 'S','E','O','U','L','\0' };

	char address2[] = { 'S','E','O','U','L'}; // 마지막 요소를 null 값 안 넣어주면 뒤에 쓰레기 값이 붙을 수 있음.

	printf("\n name : %s", name);
	printf("\n address1 : %s", address1);
	printf("\n address2 : %s", address2);

	//출력결과
	/*
	 name : HONG GIL DONG
	 address1 : SEOUL
	 address2 : SEOUL儆儆儆儆儆?EOUL
	*/
}

{% endhighlight %}

- char형 배열의 사용 예2

{% highlight js %}

void main()
{
	char string[50];
	int i = 0;
	printf("문자열을 입력하세요: ");
	scanf("%s", string); //string 앞에 &를 안 쓰는 이유: 배열형은 이미 주소값을 가리키고 있기 때문에.
	printf("입력 받은 문자열 : %s\n", string);
	printf("문자 단위 출력: ");
	while (string[i] != '\0') {
		printf("%c", string[i]);
		i++;
	}

	// 출력 결과
	/*
	문자열을 입력하세요: Hello
	입력 받은 문자열 : Hello
	문자 단위 출력: Hello
	*/
}

{% endhighlight %}

## 9강. 배열와 포인터(2) (교재 6장)
3. 배열 요소의 참조 방법

4. 배열의 기억공간 표현

## 8강. 구조체와 공용체

## 9강. 파일처리함수

## 10강. 메모리 동적할당

