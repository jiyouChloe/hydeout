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

- goto 문













## 6강. 함수와 기억클래스

## 7강. 배열와 포인터

## 8강. 구조체와 공용체

## 9강. 파일처리함수

## 10강. 메모리 동적할당

