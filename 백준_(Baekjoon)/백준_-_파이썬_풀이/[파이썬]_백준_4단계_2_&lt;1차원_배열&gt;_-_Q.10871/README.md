[파이썬] 백준 4단계 2 &lt;1차원 배열&gt; - Q.10871
=
**Q.10871**
-----------

정수 N개로 이루어진 수열 A와 정수 X가 주어진다. 이때, A에서 X보다 작은 수를 모두 출력하는 프로그램을 작성하시오.

**입력**

첫째 줄에 N과 X가 주어진다. (1 ≤ N, X ≤ 10,000)

둘째 줄에 수열 A를 이루는 정수 N개가 주어진다. 주어지는 정수는 모두 1보다 크거나 같고, 10,000보다 작거나 같은 정수이다.

**출력**

X보다 작은 수를 입력받은 순서대로 공백으로 구분해 출력한다. X보다 작은 수는 적어도 하나 존재한다.

![](https://blog.kakaocdn.net/dn/cF0dS7/btsKpnjzySs/hn4TrUSEEHBfqc5J5bGpa0/img.png)

```
N, X = map(int, input().split())

A = [int(i) for i in input().split()]

# len()을 사용하여 리스트 A의 각 요소에 A[i] 형식으로 접근
# ex) A[0], A[1], A[2] ... 해당 인덱스 위치의 값을 확인
for i in range(len(A)):
    if A[i] < X:
        print(A[i])
```