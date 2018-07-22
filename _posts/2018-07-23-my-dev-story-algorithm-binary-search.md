---
layout: post
categories:
  - My Dev Story
tags:
  - My Dev Story
  - Binary Search
  - Data Structure
---
## Binary Search(이진 탐색)
이미 정렬이 되어있는 상태에서 검색할 때 이진 탐색을 사용한다.
이진 탐색은 스무고개와 비슷하다.
예를 들어 정수 오름차순으로 정렬되어있는 배열 arr에서 item에 담겨져 있는 숫자의 배열 번호를 알아내고 싶을 때
100 개의 숫자가 배열에 담겨있고 item이 38이라 가정했을 때 질문을 다음과 같이 던질 수 있다.
Q. 50보다 크니 작니? A. 작아요.
Q. (50 / 2 = 25) 25 보다 크니 작니? A. 커요.
Q. ((25 + 50) / 2 = 38) 보다 크니 작니? A. 정답이에요!
순서대로 검색한다고 가정했을 때(단순 탐색) 운이 안좋으면 100번까지 질문을 해야 하는 상황이 올 수도 있는데
이진탐색을 하니 3번의 질문으로 정답을 찾았다!
n개의 원소를 가진 리스트에서 이진탐색을 하면 최대 O(log2n)번 만에 답을 찾을 수 있는 것이다.
### Code
아래의 코드는 정수 오름차순으로 정렬되어있는 배열 arr에서 item에 담겨져 있는 숫자의 배열 번호를 알아내는 알고리즘이다.
{% highlight java %}
// low와 high는 값의 범위 이다.
int[] arr = {-1,4,5,6,7,8,18,38,97,100,101,108};
int item = 38;

int low = 0;
int high = arr.length - 1;

while(low <= high) {
	int mid = (low + high) / 2;
	int guess = arr[mid];
	if(guess == item) {
		return mid;
	} else if(guess > item) {
		high = mid - 1;
	} else {
		low = mid + 1;
	}
}
return -1;
{% endhighlight %}