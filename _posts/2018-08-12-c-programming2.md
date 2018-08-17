---
layout: post
categories:
  - Computer Science
tags:
  - Computer Science
  - C programming
---
## 3장. 입출력함수와 연산자(1)

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


## 4장. 입출력함수와 연산자(2)

1. 연산자(operator)
 
 : 임의의 자료에 대해 각종 연산을 수행하도록 하는 기호. 

1) 산술 연산자

 : 피 연산자에 대해 사칙연산을 포함한 각종 산술연산을 수행하는 연산자
 
 -이항 연산자 : +,-,*,/,%
 
 -단항 연산자 : -(부호의 반전),--,++
 
 
 


## 5장. 선택제어문과 반복제어문

## 6장. 함수와 기억클래스

## 7장. 배열와 포인터

## 8장. 구조체와 공용체

## 9장. 파일처리함수

## 10장. 메모리 동적할당

