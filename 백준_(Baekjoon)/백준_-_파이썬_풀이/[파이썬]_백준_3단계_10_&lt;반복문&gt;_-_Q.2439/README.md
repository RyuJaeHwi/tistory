[파이썬] 백준 3단계 10 &lt;반복문&gt; - Q.2439
=
**Q.2439**
----------

첫째 줄에는 별 1개, 둘째 줄에는 별 2개, N번째 줄에는 별 N개를 찍는 문제

하지만, 오른쪽을 기준으로 정렬한 별(예제 참고)을 출력하시오.

**입력**

첫째 줄에 N(1 ≤ N ≤ 100)이 주어진다.

**출력**

첫째 줄부터 N번째 줄까지 차례대로 별을 출력한다.

![](https://blog.kakaocdn.net/dn/dLJUi5/btsKnQYZFXZ/YQioVeBNPIBkok1BYNb6d1/img.png)

```
N = int(input())

for i in range(1, N + 1):
    # 왼쪽에서부터 공백 출력
    # ex) N = 3,
    # N - i = 3 - 1 = 2 -> 2개의 공백 출력
    # N - i = 3 - 2 = 1 -> 1개의 공백 출력
    # N - i = 3 - 3 = 0 -> 공백 출력X
    for k in range(N - i):
        print(" ", end="")
    # 공백 다음에 이어 바로 별 모양 출력
    # 오른쪽에서 출력 시작X, 공백 먼저 다 출력하고 이어서 출력
    for k in range(1, i + 1):
        print("*", end="")
    print() # 줄바꿈 print() -> 없으면 줄바꿈 기능X
```