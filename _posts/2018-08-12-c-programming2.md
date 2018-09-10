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

{% highlight js %}

int array[3][3] = {1,2,3,4,5,6,7,8,9}; //가능하지만 아래의 표현이 가독성이 더 높은 방법.

int array[3][3] = { {1,2,3},{4,5,6},{7,8,9} };

{% endhighlight %}


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

int a[2][3][4] = { { {1,2,3,4},{5,6,7,8},{9,10,11,12}},{ {13,14,15,16},{17,18,19,20},{21,22,23,24} } };


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

1. 포인터의 개념

포인터(pointer): 변수의 일종

변수 : 특정 데이터 값을 가지고 있음. 변수는 데이터 값과 할당된 기억공간의 주소를 갖는다.

포인터 : 특정 데이터가 저장된 기억장소의 주소(번지)값을 가지고 있음.

> 따라서 포인터는 기억공간을 변수명으로 접근하지 않고 주소로 접근하기 위해 사용.

{% highlight js %}

void main()
{
	int days = 365;
	int month = 12;
	int Table[5] = { 1,2,3,4,5 };
	printf("days의 주소는 %x\n", &days);
	printf("month의 주소는 %x\n", &month);
	printf("배열명 Table의 주소는 %x\n", Table);
	printf("배열명 Table의 첫번째 요소의 주소는 %x\n", &Table[0]);
	printf("배열명 Table의 두번째 요소의 주소는 %x\n", &Table[1]);
	//출력결과
	/*
	days의 주소는 8ff8bc
	month의 주소는 8ff8b0
	배열명 Table의 주소는 8ff894         //첫번째 요소의 주소와 같다.
	배열명 Table의 첫번째 요소의 주소는 8ff894
	배열명 Table의 두번째 요소의 주소는 8ff898
	*/
}

{% endhighlight %}


2. 포인터변수의 선언 방법


* 형식 : 자료형 *포인터변수명;

* 사용예 : int *p;

* 기능 : 변수 p는 포인터 변수로서 정수형의 자료형을 갖는 변수의 주소를 갖는다.

{% highlight js %}

void main()
{
	int a,b;
	int *p;
	a = 5000;
	p = &a; //*가 빠지면 주소값을 의미함.
	b = *p; //*가 붙으면 값을 의미함.
}

{% endhighlight %}



3. 포인터변수의 참조 방법

{% highlight js %}

void main()
{
	int *p,i=4;
	*p = i; // p의 주소값이 정해지지 않은 상태에서 값만 넣는 것은 아무 의미가 없다.
	
	// 올바른 포인터변수의 참조 예
	
	int *p,i=4;
	p=&i;
	*p=10;
	
	//
	int *p,i=3,j;
	p=&i;
	j=*p;
	j++;
	printf("*p = %d\n",*p); //3
	printf(" p = %x\n", p); //p의 주소는 i공간의 주소와 같음.
	printf(" j = %d\n", j); //4
}

{% endhighlight %}

* void 형 포인터

 	형식 : void *포인터명;

	의미 : 프로그램 실행시에 자료형이 결정되는 경우에 사용.

	       저장하기 전에 명시적 형변환이 필요.

{% highlight js %}

void main()
{
	int a = 100;
	char b = 'b';
	void *p = NULL; 	//void 형 포인터를 선언한 후 초기화
	p = (int*)&a; 	 	//void형 포인터 p에 int형 변수a의 주소를 명시적 형변환을 이용하여 대입
	printf("*p=%d\n", *(int*)p);
	p = (char*)&b;		//void형 포인터 p에 char형 변수 b의 주소를 명시적 형변환을 이용하여 대입
	printf("*p=%c\n", *(char*)p);
	//출력결과
	/*
	*p=100
	*p=b
	*/
}

{% endhighlight %}

4. 포인터의 기억공간 표현



5. 포인터 연산

 : 포인터 변수에 +,-,++,-- 연산자를 사용하는 연산.

두개의 포인터 배열이 동일한 기억공간을 가지고 있을 때 위치상의 차는 구할 수 있다. 동일한 기억공간 아닐경우 연산 불가.

* 포인터 연산의 예1

{% highlight js %}

int *p, a[] = { 10,20,30,40,50 };
	p = &a[0];
	printf("*p == %d\n", *p); //10
	printf("*p++ == %d\n", *p++); // 포인터 p의 값을 출력 후 주소를 1(2byte)증가
	printf("*++p == %d\n", *++p); // 위에서 1 증가된 포인터 p의 주소를 1(2byte) 증가 후 출력

	p = p + 2;					// 포인터 p의 주소를 2(4byte)증가
	printf("*p == %d\n", *p); 
	printf("a[2] == %d\n", a[2]); 
	printf("*p+2 == %d\n", *p+2); 

	/*
	*p == 10
	*p++ == 10
	*++p == 30
	*p == 50
	a[2] == 30
	*p+2 == 52
	*/

{% endhighlight %}


* 포인터 연산의 예2

{% highlight js %}

void main()
{
	int *p, *q;
	int a[] = {10,20,30,40,50,60,70,80,90,100};
	p = &a[3];
	printf("*p == %d\n", *p); //40
	printf("*(p+3) == %d\n", *(p + 3)); //70
	q = p + 3;
	printf("*q == %d\n", *q); //70
	printf("p-q == %d\n", p-q); //-3  두 포인터간의 뺄셈(동일 배열을 가르키는 경우에 가능)
	printf("q-p == %d\n", q-p); //3   두 포인터간의 뺄셈(동일 배열을 가르키는 경우에 가능)
	//printf("q+p == %d\n", q+p); //두 포인터 간의 덧셈은 불가능

	/*
	*p == 40
	*(p+3) == 70
	*q == 70
	p-q == -3  
	q-p == 3
	*/
}

{% endhighlight %}


## 10강. 배열와 포인터(3) (교재 6장)


1. char형 포인터

포인터는 문자열 처리에 효과적.

문자열 처리에 char형 포인터 사용.

char *cp = "COMPUTER"; //C가 보관되어있는 주소가 cp에 저장됨.

{% highlight js %}

void main()
{
	char *cp = "COMPUTER";
	int i = 0;
	do
		printf("*(cp+%d) : %c\n", i, *(cp + i));
	while (*(cp + i++) != 0);
	/*
	*(cp+0) : C
	*(cp+1) : O
	*(cp+2) : M
	*(cp+3) : P
	*(cp+4) : U
	*(cp+5) : T
	*(cp+6) : E
	*(cp+7) : R
	*(cp+8) :
	*/
}

{% endhighlight %}


2. 포인터와 배열의 관계

> 포인터를 이용한 1차원 배열의 참조 예

{% highlight js %}

void main()
{
	static int a[] = { 10,20,30,40,50 };
	int *pt, b, c, d;
	pt = a;
	b = *pt + *(pt + 3); //10 + 40 = 50
	pt++; //1
	c = *pt + *(pt + 3); // 20+50 = 70
	d = *pt + 3; // 20 + 3 = 23
	printf("b=%d, c=%d, d=%d", b, c, d); // b=50, c=70, d=23
}

{% endhighlight %}

> 포인터를 이용한 2차원 배열의 참조 예

{% highlight js %}

void main()
{
	static a[3][3] = { {1,2,3},{4,5,6},{7,8,-9} };
	int *pt;
	pt = a[0]; // &a[0][0] 과 동일
	while (*pt != -9) {
		printf("%d", *pt);
		pt++;
	}
	//12345678
}

{% endhighlight %}

3. 포인터 배열

> 포인터와 배열은 서로 호환적이다.

int A[] = {10,20,30,40,50};

int *p,i;

A+i == &A[i];

A[i] == *(A+i);

*(p+i) == p[i];

> 포인터와 배열의 호환 예

{% highlight js %}

void main()
{
	char A[] = "ARRAY";
	char *p = "POINTER";
	int i;

	for (i = 0; i < 5; i++)
		printf("*(A+%d):%c\n", i, *(A + i));
	for (i = 0; i < 7; i++)
		printf("p[%d]:%c\n", i, p[i]);
	/*
	*(A+0):A
	*(A+1):R
	*(A+2):R
	*(A+3):A
	*(A+4):Y
	p[0]:P
	p[1]:O
	p[2]:I
	p[3]:N
	p[4]:T
	p[5]:E
	p[6]:R
	*/
}

{% endhighlight %}

> 포인터와 배열의 값 변경

배열 A[i]에서 A++,A--와 같이 값 변경 불가

포인터 *p에서 p++,p--와 같이 값 변경 가능

> 배열과 포인터의 기억공간 확보

*배열 : 기억공간 중 자료영역을 고정적으로 확보

*포인터 : 기억공간 중 자료영역을 유동적으로 확보 (필요할 때만 자료용 기억 공간을 확보, 자료의 개수가 가변적인 경우 효과적)

*** 포인터가 배열보다 활용의 폭이 넓다.

> 포인터 배열 : 포인터의 집합

		동일 속성의 포인터가 여러개 사용 될 때 포인터 배열로 선언

		주로 문자열 배열 처리에 사용
		
		char *name1, *name2, *name3;
		
		char *name[3]; 

> 포인터 배열 선언과 기억공간 표현


4. 이중 포인터

Pointer to pointer

자료가 있는 곳을 이중음로 가리키는 포인터

- 이중 포인터가 가리키는 주소로 가보면 자료가 아닌 주소 값이 들어 있고, 그 주소에 자료가 들어 있음.

- 형식 : int **p;

- 의미 : 포인터 변수에 다시 포인터를 지정하는 것으로서, 포인터에 대한 포인터이다.

{% highlight js %}

void main()
{

	//int **p;

	//p : 기억공간 주소

	//*p : 주소 p에 수록되어 있는 값. 이 값이 주소로 사용됨.

	//**p : 주소가 *p인 곳에 수록되어 있는 값. 즉 int 형 자료.
	
	// 이중 포인터의 사용 예
	
	char a = 'A', *p, **pp;
	p = &a;
	pp = &p;
	printf("**pp=%c",**pp);
	
	//**pp=A
}

{% endhighlight %}

## 11강. 구조체와 공용체(1)


1. 구조체의 개념


1) 구조체(structure)란? 

서로 다른 자료형을 갖는 자료들의 모임을 하나의 자료형으로 정의하여 사용하는 자료형.


2) 구조체 : 사용자 정의 자료형.

	다양한 형식의 자료를 간결한 형식으로 표현 가능.

	사용자가 새로운 형식을 정의하여 사용할 수 있다.


3) 구조체의 필요성

- 10대의 차량에 대한 자료처리의 경우

{% highlight js %}

// 일반 변수 사용

	char maker[15];
	long int km;
	long int cost;
	char maker[15];
	long int km;
	long int cost;
	...
	char maker[15];
	long int km;
	long int cost;

//구조체 사용 (훨신 편해짐)
	int sum(int a, int b);

	void swap(int x, int y);

	struct vehicle {
		char maker[15];
		long int km;
		long int cost;
	} car[10];


{% endhighlight %}


2. 구조체의 정의와 변수 선언

1) 구조체의 정의

{% highlight js %}

struct 구조체명 {
	멤버1;
	멤버2;
	...
};

{% endhighlight %}


2) 구조체 변수의 선언

형식 : struct 구조체명 변수명1, 변수명2, 변수명3;

struct score x,y[10],*z;


3) 구조체 정의와 변수선언 예 1

* 실제 자료형태 

{% highlight js %}

학번:2102

이름:홍길동

국어:70

영어:85

수학:80

국사:90

{% endhighlight %}

* 구조체로 정의

{% highlight js %}

 struct score{
 	char no[4];
	char name[8];
	int kor;
	int eng;
	int math;
	int hist;
 };
 
 struct score X,Y;

{% endhighlight %}

4) 구조체 정의와 변수선언 예 2

{% highlight js %}

 struct score{
 	char no[4];
	char name[8];
	int kor;
	int eng;
	int math;
	int hist;
 }X,Y;

{% endhighlight %}

5) 구조체 정의와 변수선언 예 3 (가장 많이 사용함)

{% highlight js %}

 typedef struct score{
 	char no[4];
	char name[8];
	int kor;
	int eng;
	int math;
	int hist;
 }jumsu;	//struct score를 jumsu라는 새로운 자료형으로 정의
 
 jumsu X,Y;

{% endhighlight %}


3. 구조체 변수의 초기화 및 참조

1) 구조체 변수의 초기화

{% highlight js %}

 struct person{
	char name[8];
	int age;
	char sex;
 };
struct person X={"홍길동",20,'M'};

{% endhighlight %}

{% highlight js %}

 struct person{
	char name[8];
	int age;
	char sex;
 }X={"홍길동",20,'M'};

{% endhighlight %}


2) 구조체 멤버의 참조

*형식 : 구조체변수명.멤버명

*사용예 : X.name, X.age, X.sex

3) 구조체 멤버의 참조 예

{% highlight js %}

#include <stdio.h> 
#include <string.h> 

struct person {
	char name[8]; //8byte
	int age;      //2byte
	char sex;     //1byte
};

void main()
{
	struct person X = { "홍길동",30,'M' };
	struct person Y;
	strcpy(Y.name, "임꺽정"); // 구조체 멤버에 값 대입(문자열을 처리할 경우 문자열 복사 함수 strcpy()를  사용
	Y.age = 34;
	Y.sex = 'M';
	printf("X의 정보: %s, %d, %c\n", X.name, X.age, X.sex);
	printf("Y의 정보: %s, %d, %c\n", Y.name, Y.age, Y.sex);

	//출력결과
	/*
	X의 정보: 홍길동, 30, M
	Y의 정보: 임꺽정, 34, M
	*/
}

{% endhighlight %}


4. 구조체 배열

1) 구조체 배열이란?

동일한 구조를 갖는 구조체 변수가 여러개 사용될 때

그 구조체 변수들을 대표하는 배열명을 설정하여 일반 배열과 같이 사용.


2) 구조체 배열의 예

* 3명의 개인 신상정보를 저장하기 위한 구조체 배열 선언.

{% highlight js %}
	
struct person {
	char name[8]; 
	int age;      
	char sex;     
}X[3];

{% endhighlight %}

{% highlight js %}
	
struct person {
	char name[8]; 
	int age;      
	char sex;     
};

struct person X[3];

{% endhighlight %}


3) 구조체 배열의 초기화

{% highlight js %}

struct person X[3]={ {"홍길동",20,'M'}, {"황진이",22,'F'}, {"임꺽정",30,'M'} };

{% endhighlight %}


4) 구조체 배열의 멤버 참조

{% highlight js %}

strcpy(X[1].name, "홍길동"); //두번째 열의 name에 입력
X[2].sex = 'M';		    //세번째 열의 sex에 입력
K = X[2].age;		

{% endhighlight %}

5) 구조체 배열의 사용 예

{% highlight js %}

void main()
{
	struct person {
		char *name;
		int age;
		char sex;
	};

	struct person X[3] = { {"홍길동",20,'M'}, {"황진이",22,'F'}, {"임꺽정",30,'M'} };

	int i, sum = 0;
	for (i = 0; i < 3; i++) {
		printf("이름:%s 나이:%d 성별:%c\n", X[i].name, X[i].age, X[i].sex);
		sum = sum + X[i].age;
	}
	printf("나이합:%d", sum);

	//출력
	/*
	이름:홍길동 나이:20 성별:M
	이름:황진이 나이:22 성별:F
	이름:임꺽정 나이:30 성별:M
	나이합:72
	*/
}

{% endhighlight %}


5. 구조체 포인터


1) 포인터를 사용하여 구조체를 다룰 수 있게 함

- 구조체를 보다 쉽게 다룰 수 있다.

- 구조체변수 선언시 * 를 붙여 포인터로 선언

- 구조체 포인터는 포인터와 동일하게 주소값을 갖게 되며, 자료가 있는 곳을 가르킨다.


2) 구조체 포인터의 선언

* 형식 : struct 구조체명 *포인터변수명;

* 사용예 : struct person *pt;

{% highlight js %}

struct person {
	char name[8];
	int age;
	char sex;
};

struct person man; //구조체 변수 man 선언
struct person *pt; //구조체 포인터변수 pt선언
pt = &man;	   // 구조체 포인터변수의 초기화


{% endhighlight %}

3) 구조체 포인터의 멤버 참조

* 도트 연산자(.)를 이용(도트 연산자의 처리 속도가 포인터 연산자의 처리속도 보다 빠르므로 항상 포인터 변수에 소괄호를 사용해야하는 불편함이 있음.)

	(*pt).name
	
* 포인터 연산자(->)를 이용 (도트 연산자보다 포인터 연산자가 가독성에 더 좋음.)

	pt->name
	
{% highlight js %}

struct student {
	char name[10];
	int kor;
	int math;
};

void main()
{
	struct student hs[4] = { {"Chloe",100,90},{"Judy",85,90},{"Miho",70,85},{"Samir",95,75} };
	struct student *p;
	p = hs;

	printf("%s %d %d \n", p->name, p->kor, p->math);
	p += 3;
	printf("%s %d %d \n", p->name, p->kor, p->math);
	p--;
	printf("%s %d %d \n", p->name, p->kor, p->math);
	
	//실행 결과 
	/*
	Chloe 100 90
	Samir 95 75
	Miho 70 85

	*/
}


{% endhighlight %}	

## 12강. 구조체와 공용체(2)


1. 함수와 구조체

1) 함수에서의 구조체 사용

* 구조체를 함수의 매개변수로 사용

> 일반변수를 함수의 매개변수로 사용하는 것과 동일

> 매개변수가 구조체인 경우 함수의 형식매개변수를 구조체로 선언

> 해당 구조체 전체가 복사되기 때문에 편리

> 구조체 전체가 복사되기 때문에 시간이 많이 걸리고 기억공간의 낭비가 심하다.


* 구조체를 함수의 매개변수로 사용 예

{% highlight js %}

struct num calc(struct num);

struct num {
	int x;
	int y;
	int sum;
	int mul;
};

// 넘겨받은 struct num 형 구조체의 멤버끼리 계산
struct num calc(struct num number2) {
	number2.sum = number2.x + number2.y;
	number2.mul = number2.x*number2.y;
	return(number2);
};

void main()
{
	struct num number1; //구조체 변수 선언
	number1.x = 10;
	number1.y = 20;
	number1 = calc(number1); // 피호출 함수 calc()에 struct num형 구조체를 매개변수로 넘겨줌.

	printf("x.%d, y.%d, sum:%d, mul:%d\n", number1.x, number1.y, number1.sum, number1.mul);

	// 실행결과
	// x.10, y.20, sum:30, mul:200
}

{% endhighlight %}	


* 구조체 포인터를 함수의 매개변수로 사용(주로 이방법을 많이 사용함)

> 일반적으로 구조체 포인터를 함수의 매개변수로 사용

> 구조체를 복사하지 않기 때문에 실행속도가 향상되고, 기억공간의 사용효율도 좋다.


* 구조체포인터를 함수의 매개변수로 사용 예

{% highlight js %}

struct num calc(struct num*);
struct num calc(struct num *number2) {  //구조체 포인터를 매개변수로 넘겨 받음.
	number2->sum = number2->x + number2->y;
	number2->mul = number2->x * number2->y;
};

void main()
{
	struct num number1; //구조체 변수 선언
	number1.x = 10;
	number1.y = 20;
	calc(&number1);  // 참조호출(& 사용)

	printf("x.%d, y.%d, sum:%d, mul:%d\n", number1.x, number1.y, number1.sum, number1.mul);
}

// 실행결과
// x.10, y.20, sum:30, mul:200

{% endhighlight %}

2. typedef

1) 이미 존재하는 자료형에 새로운 이름을 붙이기 위한 키워드

* 형식 : typedef 기존 자료형 새로운 자료형 이름;

* 사용 예 : typedef int INT;

2) typedef의 사용

{% highlight js %}

typedef unsigned int BYTE; //unsigned int 형을 BYTE라는 새로운 이름으로 정의

BYTE val; // 컴파일러가 unsigned int val로 해석

typedef int *PTR; // int*를 PTR로 재정의

PTR p1,p2;

{% endhighlight %}

{% highlight js %}

struct data {
	int x;
	int y;
};
typedef struct data DATA;

/*
//이방법을 더 많이 사용(간략하므로)
typedef struct data {
	int x;
	int y;
} DATA;
*/
void main()
{

	DATA d = { 1,2 };
	printf("%d,%d\n", d.x, d.y);

	//실행결과
	//1,2
}

{% endhighlight %}

* typedef의 사용 예2

{% highlight js %}

struct person {
	char name[20];
	int age;
	char sex;
};
typedef struct person MAN;
typedef unsigned char CHAR;
typedef int* PTR;

void main()
{
	MAN member;
	CHAR data;
	PTR pt;
	strcpy(member.name, "홍길동");
	member.sex = 'M';
	member.age = 30;
	data = 100;
	pt = &(member.age);
	printf("*pt=%d\n", *pt);
	//출력결과
	/*
	*pt=30
	*/
}

{% endhighlight %}


3. 구조체 비트필드

1) 구조체의 비트필드(bit field)

> 주기억장치의 기억공간을 byte 단위가 아닌 bit단위로 사용.

	- 프로그램 시 bit단위의 연산이 필요할 경우 int형 변수를 사용.

	- 이때 int형은 2byte(16bit)이므로 1bit를 제외한 15bit의 기억공간이 낭비.

> 구조체의 비트필드를 사용하면
	
	- 기억공간을 절약하고,
	
	- 더욱 융통성 있는 데이터 구조체를 만들 수 있다.


2) 구조체 비트필드의 정의

{% highlight js %}

struct 비트필드명 {
	자료형 비트필드변수 : 비트크기;
		
};

struct nibble {
	unsigned a : 1;
	unsigned b : 2;
	unsigned c : 1;
};

{% endhighlight %}

> 구조체 비트필드의 선언 예와 기억공간 구조

{% highlight js %}

struct test {
	unsigned a : 4; //16개의 값 들어갈 수 있음 0~15
	unsigned b : 2; // 0~3
	unsigned c : 1; // 0,1
	unsigned d : 7; // 0~127
	// 총 14byte임. 만약 int크기가 2byte라면 총 16 byte까지 선언가능.

};

struct test bit; // 구조체 비트필드의 변수의 선언

// 구조체 비트필드의 참조예
bit.a = 15;
bit.b = 3;
bit.c = 0;
bit.d = 127;

{% endhighlight %}

* 주의 사항

비트 필드의 자료형은 int 나 unsigned로 선언.

비트필드에 대한 포인터나 배열은 사용 안됨.

비트필드의 전체 크기는 시스템이 제공하는 int의 크기 이내여야 함.


* 구조체 비트필드의 사용 예

{% highlight js %}

struct test {
	unsigned a : 5;
	unsigned b : 6;
	unsigned c : 6;
	unsigned d : 4;
};

void main()
{
	struct test v = {1,2,3,4}; // 구조체 비트필드의 변수의 선언과 초기화
	printf("v.a=%d v.b=%d v.c=%d v.d=%d\n", v.a, v.b, v.c, v.d);
	printf("v는 %d byte 를 사용한다.\n",sizeof(v));
	//실행결과
	/*
	v.a=1 v.b=2 v.c=3 v.d=4
	v는 4 byte 를 사용한다.
	*/
}

{% endhighlight %}

* 구조체 비트필드의 기억공간 구조

{% highlight js %}

struct test {
	unsigned a : 5;
	unsigned b : 6;
	unsigned c : 6;
	unsigned d : 4;
}; 
// int크기가 2byte인 컴퓨터에서 비트필드의 총 수가 int의 크기보다 클 경우 비트 필드가 2개의 int 사이에 걸쳐 저장될 수 없다.
// 즉, a,b는 첫번째 int에 저장이되고 c,d는 두번째 int에 저장이 된다. 첫번째 int에서 5bit는 사용이 되지 않는다. 
// 전체적으로 4byte가 사용됨.

{% endhighlight %}


4. 공용체의 개념


1) 공용체(union)란?

> 동일한 기억장소에 여러 유형의 자료를 저장하기 위해서 프로그래머가 선언한 자료형.

> 공용체 안에 포함된 자료들이 같은 기억장소를 공유하여 사용.

> 사용 될 자료의 자료형이 유동적일 경우 기억공간을 효율적으로 사용할 수 있는 장점.


2) 공용체의 예 

> 공용체의 멤버들이 완전히 다른 자료형을 가질 때 기억공간을 절약하기 위해 사용

예) 급여관리 프로그램

	- 원화로 월급을 지급받는 사람 : 정수형으로 처리

	- 달러로 월급을 지급받는 사람 : 실수형으로 처리

	=> 이러한 경우 공용체를 사용하면 필요에 따라 메모리의 자료형을 선택해서 값을 저장 가능.
	

3) 공용체의 정의

> 형식  : 

{% highlight js %}

union 공용체명 {
	멤버 1;
	멤버 2;
	...
};

{% endhighlight %}

{% highlight js %}

// 공용체 정의
union var{  
	char a;
	int b;
	float c;
};

union var abc; //공용체 변수 선언

//공용체 변수의 참조
abc.a = 'A';
abc.b = 133; 
abc.c = 1234.5678;

{% endhighlight %}


> 공용체 변수의 선언

	형식 : union 공용체명 변수명;

	사용예 : union var abc;


5. 공용체의 사용

1) 공용체가 사용되면

	> 공용체의 멤버 중에서 자료크기(byte 수)가 가장 큰 멤버에 대해서만 기억공간이 할당 되고,
	
	> 기억공간의 시작위치부터 각 부분을 다른 멤버가 공용으로 사용.

{% highlight js %}
 
 union hold {
	int digit;   //2byte
	double big;  // 멤버들 중 가장 크기가 큰 자료형 8byte
	char letter; // 1byte
};
// |         |    | | | | | | |
   <-letter->
   <-   digit   ->
   <-         big           -> 
   
{% endhighlight %}


## 13강. 파일처리함수(1) - 교재 8장


1. 파일 입'출력의 개념

1) 보조기억장치의 파일을 이용한 자료의 입'출력.

	: 파일처리 함수를 이용.

2) 키보드나 모니터를 통한 자료의 입'출력.
	
	: 표준 입출력 함수를 이용.

3) 파일처리 함수

	: 보조기억장치(디스크)에 들어있는 정보들의 모임을 파일이라 하고, 이러한 파일을 제어하는 함수.

4) 파일이란?

	> 보조기억장치에 저장된 데이터들의 모임.
	
	> 일련의 바이트(byte)들로 구성
	
	> C프로그램은 운영체제를 통해서 파일을 읽거나 쓰게 된다.
	
	> C언어에서는 컴퓨터와 연결된 장치들까지도 모두 파일의 범주에 넣어 처리.

5) 파일의 구분

	> 텍스트 파일(text file)
		
		: 화면에 출력되는 문자들로 구성된 파일.
	
	> 2진 파일(binary file)
	
		: 텍스트 파일을 포함한 모든 종류의 자료를 다루는 파일.
		
		: 컴파일 되어 있어 기계어에 가까우므로 내용을 이해하거나 인쇄가 불가능.

6) 파일에 대한 자료의 입력과 출력

	> 파일 입력
	
		: 디스크 상의 특정 위치(파일)에 수록되어 있는 자료를 읽어 들여 기억공간에 수록하는 절차.
		
	> 파일 출력
	
		: 기억공간에 있는 자료를 디스크 상의 특정 위치(파일)에 수록하는 절차.
	
7) 파일처리를 위해서는 파일포인터를 사용

	> 파일포인터
	
		: 파일이 어디에 있는지를 가리키는 포인터.
		
		: 모든 파일 입출력 함수는 파일 포인터를 사용.
	
8) 파일을 입출력 할 때 버퍼(buffer)가 사용

	> 버퍼(buffer)
		
		: 기억 공간과 디스크 사이에 존재하는 임시 기억 공간(기억공간과 임시기억공간의 속도차를 줄여줌.)
		
		: 파일 입출력 시 디스크에 저장된 자료를 기억 공간으로 읽어 들이거나, 기억 공간에서 처리된 자료를 디스크에 저장할 때 사용.
		
		: 데이터를 버퍼에 다 옮겨놓고 버퍼에 있는 데이터를 목적지로 옮겨줌.
		
		
2. 파일포인터를 이용한 파일 입'출력

1) 자료의 입'출력 개념
	
	> 프로그램과 입'출력 장치(콘솔,파일,소켓 등)와의 사이에 이루어지는 자료의 입력과 출력.
	
	> 자료의 입'출력을 위한 논리적인 통로가 필요 : 스트림

2) 스트림(stream)

	스트림(출력)
		
 시스템  ------------>      콘솔,파일,소켓 

프로그램 <------------	

	스트림(입력)


3) 자료의 입출력을 위해서는 스트림이 필요
	
	> 표준 입출력장치를 이용한 자료 입출력.
	
		- 표준 입출력 장치와의 스트림은 프로그램 실행 시 자동으로 생성되고, 프로그램 종료 시 자동으로 소멸.
	
	> 파일을 이용한 자료 입출력
	
		- 파일 입출력을 위한 스트림은 프로그램을 통해 생성과 소멸을 시켜주어야 한다.
		
4) 파일 입출력의 수행과정

파일을 연다 (파일과 자료를 주고 받을 수 있는 스트림을 생성(fopen()함수 사용) )

=> 입출력을 수행한다 

=> 파일을 닫는다. (생성된 스트림을 소멸시키기 위한 과정(fclose()함수 사용) )

* 스트림의 생성

	- 파일과 프로그램과의 통로(논리적인 접속)를 구성.
	
	- 통로 역할을 파일포인터가 수행.
	

5) 파일 입출력 프로그램 구조

{% highlight js %}
 	
FILE *fp;			//파일포인터 선언 
fp = fopen("파일명","모드");	    //파일 열기
// <입출력 수행>		    //<읽기'쓰기>
fclose(fp);			//파일 닫기
   
{% endhighlight %}

6) 파일 입출력 프로그램의 구조 예

{% highlight js %}
 	
void main()
{
	char ch;
	FILE *fp;
	fp = fopen("sample.dat", "w");
	for (ch = 'A'; ch <= 'Z'; ch++)
		fputc(ch, fp);
	fclose(fp);
}

// 생성된 sample.dat파일을 열어보면 ABCDEFGHIJKLMNOPQRSTUVWXYZ 내용이 들어있음.

{% endhighlight %}


7) 파일포인터의 선언

	> 파일 입출력을 위해서는 맨 처음 파일포인터를 선언 해야 한다.
	
	> 이 파일포인터는 실제 파일과 프로그램을 연결해 주는 통로가 된다.
	
	* 형식 : FILE *변수명;
	
	* 사용 예 : FILE *fp;
	
	* 기능 : 파일형 포인터변수를 선언
	

8) 파일 포인터 변수와 버퍼의 관계

FILE *fa, *fb; // 파일형 포인터변수 선언. FILE형: 구조체형, FILE형 포인터변수 : 파일에 대한 여러가지 정보를 가진 변수

// 버퍼가 fa,fb 두개 생김. fopen()함수에 의해 실제 파일과 연결됨.

9) 파일포인터 선언과 파일 열기

* 파일 열기

	: 프로그램과 디스크상의 파일 사이에 데이터가 입출력 할 수 있도록 통로를 만들어 주는 것.
	
	* 형식 : fopen("파일명", "사용모드"); 
	
	* 사용예 : fp=fopen("test.dat","r");
	
	* 기능 : 파일을 열어 사용할 수 있게 함.
	
* fopen() 함수

	> 입출력이 정상이면 지정된 파일의 파일포인터에 시작주소 값을 리턴.
	
	> 파일이 개방되지 않을 때는 에러 값 (NULL값)을 리턴.
	
	> 사용(개방)모드 = 파일접근모드 + 데이터 입출력 모드
	
	> 파일 접근모드(
		
		r: t가 생략됨. 텍스트 모드 입력 개방,
		
		rb: 2진모드 입력 개방,
		
		w: t가 생략됨. 텍스트 모드 출력 개방, 이전 내용 삭제,
		
		wb: 2진모드 출력 개방, 이전 내용 삭제,
		
		a: t가 생략됨. 텍스트 모드 이전 내용 뒤에 추가,
		
		ab: 2진모드 이전 내용 뒤에 추가,
		
		r+,rb+: 읽기와 쓰기 겸용,
		
		w+,wb+: 읽기와 쓰기 겸용, 이전 내용 삭제,
		
		a+,ab+: 파일 읽기, 이전 내용 뒤에 추가
		
		)
	
	> 데이터 입출력 모드(t,b)
	
	> t : 텍스트 모드(text mode)
	
		- 프로그램에서 파일로 자료를 입출력 할 때 변환이 일어나는 입출력 모드
		
		- 문자 변환이 필요(\n <-> CR/LF)
	
	> b: 이진 모드(binary mode)
	
		- 변환이 일어나지 않는 입출력모드
		
		- 문자 변환이 불 필요.
	
10) 파일 열기 사용 예

{% highlight js %}
 	
void main()
{
	FILE *fp1, *fp2;
	fp1 = fopen("a:\text.txt", "w");
	fp2 = fopen("c:\source\text.c", "r");
}
	// 파일 open이 안될 경우를 고려해서 강제로 종료시켜야 함.
	if ((fp = fopen("파일명", "사용모드")) == NULL) {
		puts("파일을 열수 없음");
		exit(1); //프로그램을 종료할 때 사용하는 함수
	}

{% endhighlight %}

11) 파일닫기

	* 형식 : fclose(파일포인터 변수);
	
	* 사용예 : fclose(fp);
	
	* 기능 : 열었던 파일을 닫고, fp를 해제
		
		 개방된 통로와 버퍼를 원 상태로 환원.
		 
		 쓰기의 경우 파일 끝에 EOF(End Of File)신호를 부가 (완전한 파일로 완성됨)
		 

12) 파일 열기와 닫기 예

{% highlight js %}
 	
void main()
{
	FILE *fp1, *fp2;
	
	fp1 = fopen("a:\text.txt", "w");
	fp2 = fopen("c:\source\text.c", "r");
	...
	fclose(fp1);
	fclose(fp2);
}

{% endhighlight %}
	
	
3. 순차파일처리

1) 파일은 레코드 단위로 구성

	> 레코드(record)
	
	: 파일 입출력처리에 사용되는 논리적인 기본단위
	
	: 각 레코드들은 필드(field)들로 구성

	> 파일 처리함수를 이용하여 파일을 편성하는 방법에 따라
	
	  순차파일(레코드의 길이가 일정하지 않음)과 랜덤파일(레코드의 길이가 일정함)로 나뉘어짐.

2) 파일의 종류

	> 순차파일(sequential file)
	
		: 파일의 처음부터 자료를 차례로 읽고, 기록하는 파일
		
		: 레코드의 길이가 일정하지 않은 파일
		
	> 랜덤파일(random file)
	
		: 파일의 임의의 위치에서 자료를 읽고 기록하는 파일
		
		: 레코드의 길이가 일정한 파일.
		
3) 순차파일에서의 레코드 구성

	> 순차파일은 레코드의 길이가 일정하지 않기 때문에 레코드들의 구분이 필요 : CR/LF를 사용하여 구분.
	
	|레코드1|CR/LF|레코드2|CR/LF|레코드3|
	
	> 텍스트 모드일 경우 자동으로 CR\LF를 \n으로 변환

4) 순차파일 출력함수

	> 만들어진 파일에 자료를 기록하는 함수
	
		출력함수                 입력함수
		
		putc()			getc()
		
		fputc()			fgetc()
		
		fputs()			fgets()
		
		fprintf()		fscanf()
		


## 14강. 파일처리함수(2)

1. 순차파일 입출력함수

1)순차파일 출력함수

: 만들어진 파일에 자료를 기록하는 함수

putc() fputc() fputs() fprintf() (입력함수: getc(), fgetc(), fgets(), fscanf())

2) 순차파일 만들기

> putc()함수

: 문자 단위의 파일 출력함수

: fputc() 함수와 유사

* 형식 : putc(문자변수, 파일포인터변수);

* 사용 예 : putc(c,fp);

* 기능 : fp가 가리키는 파일에 변수 c에 있는 문자를 출력.

> putc() 함수의 사용 예

{% highlight js %}
 	
void main()
{
	FILE *fp;
	char c;
	fp = fopen("sample1.txt", "w");

	if (fp == NULL) {
		puts("파일을 열수 없음");
		exit(1); //프로그램을 종료할 때 사용하는 함수
	}

	while ((c = getchar()) != EOF) // 문자 출력의 끝을 판별(ctrl+z)
		putc(c, fp);			   // 문자를 파일로 출력
	fclose(fp);					   // 파일닫기
}

{% endhighlight %}

> fputs() 함수

: 문자열을 파일로 출력할 때 사용

* 형식 : fputs(문자열변수, 파일포인터 변수);

* 사용 예 : fputs(s,fp);

* 기능 : 지정된 파일에 문자열(하나의 레코드)을 출력.

> fputs() 함수의 사용 예

{% highlight js %}
 	
void main()
{
	char name[64];
	FILE *fp;

	if ((fp = fopen("sample2.txt", "w") )== NULL) {
		puts("파일을 열수 없음");
		exit(1); //프로그램을 종료할 때 사용하는 함수
	}
	gets(name);
	while (strcmp(name, "end")) {
		strcat(name, "\n");
		fputs(name, fp);
		gets(name);
	}
	fclose(fp);
}

{% endhighlight %}

> fprintf()함수

: 지정된 형식을 가지고 파일에 자료를 출력

: 여러 항목의 복합적인 자료로 구성된 레코드를 저장할 때 유용

* 형식 : fprintf(파일포인터 변수, "출력형식", 변수);

* 사용 예 : fprintf(fp, "%s %d\n",a,b);

* 기능 : 지정된 형식대로 자료를 파일포인터 변수가 가리키는 곳에 출력.

> fprintf() 함수의 사용 예

{% highlight js %}
 	
void main()
{
	FILE *fp;
	char no[10], name[10];
	int mid, term, rep, att, i;
	fp = fopen("sample3.txt", "w");
	if (fp  == NULL) {
		puts("파일을 열수 없음");
		exit(1); //프로그램을 종료할 때 사용하는 함수
	}
	fprintf(stdout, "학번 이름 중간 기말 레포트 출석 점수를 입력\n");
	for (i = 0; i < 5; ++i) {
		scanf("%s %s %d %d %d %d", no, name, &mid, &term, &rep, &att);

		fprintf(fp, "%10s %8s %3d %3d %3d %3d\n", no, name, mid, term, rep, att);

	}
	fclose(fp);
	//입력
	/*
	학번 이름 중간 기말 레포트 출석 점수를 입력
	97001 KIM 29 28 30 10
	97002 park 25 15 16 30
	97003 LEE 30 12 29 39
	97004 hong 10 11 22 10
	97005 YONG 30 20 10 22
	*/
	// 출력 결과
	/*
     97001      KIM  29  28  30  10
     97002     park  25  15  16  30
     97003      LEE  30  12  29  39
     97004     hong  10  11  22  10
     97005     YONG  30  20  10  22
	*/	
}

{% endhighlight %}


2) C언어에서는 입,출력 장치를 파일 개념으로 처리

> C프로그램에서는 자동적으로 3개의 표준파일에 대한 포인터를 생성.

> 이러한 표준파일에 대해서는 따로 파일포인터를 선언할 필요가 없다.

<table>
  <thead>
    <tr>
      <th>표준파일</th>
      <th>파일 포인터</th>
      <th>대응 장치</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>표준입력</td>
      <td>stdin</td>
      <td>키보드</td>
    </tr>
    <tr>
      <td>표준출력</td>
      <td>stdout</td>
      <td>모니터</td>
    </tr>
    <tr>
      <td>표준에러</td>
      <td>stderr</td>
      <td>모니터</td>
    </tr>
  </tbody>
</table>

3) 순차파일 입력함수

: 파일 출력함수에 의해 만들어진 순차파일의 저장된 자료를 읽어 내는 함수.

: 자료를 읽을 때는 파일의 끝에 있는 EOF 신호를 만날 때까지 읽을 수 있는 프로그램 작성.

(getc(),fgetc(),fgets(), fscanf())

> getc() 함수

: 문자 단위의 파일 입력함수

: fgetc() 함수와 유사

* 형식 : getc(파일포인터변수);

* 사용 예 : c = getc(fp);

* 기능 : 지정된 파일로부터 한 문자를 읽어온다.

> fgets() 함수

: 파일에 저장된 문자열 자료를 읽을 때 사용.

: 읽어 낼 문자열의 길이를 반드시 명시.

* 형식 : fgets(문자열변수, 문자열 길이 + 1, 파일포인터 변수);

* 사용 예 : fgets(s,40,fp);

* 기능 : 지정된 파일로부터 해당 문자열 길이 만큼의 문자를 읽어와 문자열 변수에 저장한다.

{% highlight js %}
 	
void main()
{
	char name[20];
	FILE *fp;

	if ((fp = fopen("sample2.txt", "r")) == NULL) {
		puts("파일을 열수 없음");
		exit(1); //프로그램을 종료할 때 사용하는 함수
	}
	
	while (fgets(name, 20, fp) != NULL) {
		printf("%s", name);
	};
	fclose(fp);
}

{% endhighlight %}


> fscanf()함수

: 숫자, 문자 등 복합적인 자료로 구성된 레코드를 읽을 때 사용.

: 일반적으로 파일의 끝을 판별하는 feof()함수와 같이 사용.

* 형식 :  fscanf(파일포인터 변수, "입력형식", 변수);

* 사용 예 : fscanf(fp, "%s %d", &a, &b);

* 기능 : 파일 포인터가 가리키는 곳으로부터 지정된 형식대로 자료를 읽어 온다.


> 레코드 추가를 위한 사용 모드

a 	a+	ab 	ab+

* 형식 : fp=fopen("파일명","a"); 

* 사용예 : fp=fopen("sample.dat","a");

* 기능 : 이미 만들어진 순차파일의 끝에 새로운 레코드 추가(append)/ 파일이 없으면 만든다.

{% highlight js %}
 	
void main()
{
	FILE *fp;
	fp = fopen("sample3.txt", "a");
	fputs("추가했다1\n", fp);
	fputs("추가했다2\n", fp);
	fputs("추가했다3\n", fp);
	fputs("추가했다4\n", fp);
	fclose(fp);
}

{% endhighlight %}

2. 랜덤파일(레코드들이 일정한 크기를 가지고 있음) 처리

1) 랜덤파일(random file)

: 파일의 임의의 위치에서 자료를 읽거나 쓸 수 있다.

: 레코드의 길이가 일정


2) 순차파일에 비해

단점 : 기억공간 낭비

장점 : 레코드 검색이 빠르고 효과적


3) 일반적으로 랜덤을 입출력할 때는 2진모드로 파일을 개방

fopen("파일이름","wb");

fopen("파일 이름", "rb");

> 2진모드의 특징

: 텍스트파일보다 적은 기억공간

: 레코드의 길이를 프로그래머가 결정

: 파일 포인터의 위치 변경 가능


3. 랜덤파일 입출력함수

1) 랜덤 파일 만들기

> fwrite() 함수

: 레코드의 길이를 지정

: 자료저장 변수는 포인터 형

* 형식 : fwrite(저장자료변수, 레코드길이, 레코드개수, 파일포인터);

* 사용예 : fwrite(name,10,1,fp);

{% highlight js %}
 	
void main()
{
	FILE *fp;
	char name[10];
	if ((fp = fopen("sample.txt", "wb")) == NULL) {
		puts("파일을 개방할 수 없습니다.");
		exit(1);
	}
	gets(name);
	while (strcmp(name, "END")) {
		fwrite(name, 10, 1, fp);
		gets(name);
	}
	fclose(fp);

}

{% endhighlight %}


> fread() 함수

: 읽기에 성공하면 읽은 레코드 수를 리턴

* 형식 : fread(읽을 자료변수, 레코드 길이, 레코드 개수, 파일포인터);

* 사용 예 : fread(name, 10, 1, fp);

{% highlight js %}
 	
void main()
{
	FILE *fp;
	char name[10];
	if ((fp = fopen("sample.txt", "rb")) == NULL) {
		puts("파일을 개방할 수 없습니다.");
		exit(1);
	}
	
	while (1) {
		if (fread(name, 10, 1, fp) != 1)
			break;
		
		puts(name);
	}
	fclose(fp);
}

{% endhighlight %}


4. 랜덤파일의 위치 제어

1) fseek() 함수

: 파일 포인터를 임의의 위치로 이동시키는 함수

: 랜덤파일의 특정부분을 입출력 할 수 있다.

* 형식 : fseek(파일포인터 변수, 이동할 상대위치, 기준위치를 지정하는 모드)

* 사용 예 : fseek(fp,2*REC_size, SEEK_SET); // 파일의 시작위치에서 +2 위치 표현

: 기준 위치로부터 앞, 뒤로 이동하는 상대위치 개념 사용.


2) fseek() 함수의 기준위치 지정모드

stdio.h에 정의 됨.

<table>
  <thead>
    <tr>
      <th>기준위치모드</th>
      <th>동일기호</th>
      <th>설명</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>0</td>
      <td>SEEK_SET</td>
      <td>파일의 시작위치</td>
    </tr>
    <tr>
      <td>1</td>
      <td>SEEK_CUR</td>
      <td>현재 파일포인터의 위치</td>
    </tr>
    <tr>
      <td>2</td>
      <td>SEEK_END</td>
      <td>파일의 끝 위치</td>
    </tr>
  </tbody>
</table>

{% highlight js %}
 	
void main()
{
	char str[10];
	FILE *fp = fopen("sample.txt", "wt");
	fputs("1234567890", fp);
	fclose(fp);

	fp = fopen("sample.txt", "rt");
	fseek(fp, 7, SEEK_SET);
	fgets(str, 4, fp); // 4: 문자열3개 +1 출력
	printf("7번째부터 3글자 출력 : %s \n",str);
	fseek(fp, -2, SEEK_CUR); //현재커서가 0다음에 있으므로 8다음으로 이동됨
	fgets(str, 3, fp);
	printf("현재위치에서 앞에 2글자부터 2글자 출력 : %s \n",str);
	fseek(fp, -9, SEEK_END); // 1다음으로 커서이동
	fgets(str, 6, fp);
	printf("맨뒤에서 9번째 앞부터 5글자 출력 : %s \n",str);
	fclose(fp);
	//출력결과 
	/*
	7번째부터 3글자 출력 : 890
	현재위치에서 앞에 2글자부터 2글자 출력 : 90
	맨뒤에서 9번째 앞부터 5글자 출력 : 23456
	*/
}

{% endhighlight %}
