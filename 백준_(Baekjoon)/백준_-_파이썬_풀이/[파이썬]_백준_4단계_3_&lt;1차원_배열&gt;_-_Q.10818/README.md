[파이썬] 백준 4단계 3 &lt;1차원 배열&gt; - Q.10818
=
**Q.10818**
-----------

N개의 정수가 주어진다. 이때, 최솟값과 최댓값을 구하는 프로그램을 작성하시오.

**입력**

첫째 줄에 정수의 개수 N (1 ≤ N ≤ 1,000,000)이 주어진다. 둘째 줄에는 N개의 정수를 공백으로 구분해서 주어진다. 모든 정수는 -1,000,000보다 크거나 같고, 1,000,000보다 작거나 같은 정수이다.

**출력**

첫째 줄에 주어진 정수 N개의 최솟값과 최댓값을 공백으로 구분해 출력한다.

![](https://blog.kakaocdn.net/dn/ehufIW/btsKqDZYLVX/O8b52dJ3EF08XKHGSVLikk/img.png)

```
N = int(input())

list_N = [int(i) for i in input().split()]

max_list_N = max(list_N)
min_list_N = min(list_N)

print(min_list_N, max_list_N)
```