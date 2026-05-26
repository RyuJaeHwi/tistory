[파이썬] 백준 7단계 1 &lt;2차원 배열&gt; - Q.2738
=
**Q.2738**
----------

N\*M크기의 두 행렬 A와 B가 주어졌을 때, 두 행렬을 더하는 프로그램을 작성하시오.

**입력**

첫째 줄에 행렬의 크기 N 과 M이 주어진다. 둘째 줄부터 N개의 줄에 행렬 A의 원소 M개가 차례대로 주어진다. 이어서 N개의 줄에 행렬 B의 원소 M개가 차례대로 주어진다. N과 M은 100보다 작거나 같고, 행렬의 원소는 절댓값이 100보다 작거나 같은 정수이다.

**출력**

첫째 줄부터 N개의 줄에 행렬 A와 B를 더한 행렬을 출력한다. 행렬의 각 원소는 공백으로 구분한다.

![](https://blog.kakaocdn.net/dn/vIPYw/btsKzFwjLUX/KCdMSHqzzRrrBVd8kkEGf0/img.png)

```
# N = 행의 개수, M = 각 배열의 요소 개수
N, M = map(int, input().split())

matrix_A = []

for i in range(N):
    # 각 행렬을 리스트로 변환
    element_A = list(map(int, input().split()))
    matrix_A.append(element_A)

matrix_B = []

for i in range(N):
    # 각 행렬을 리스트로 변환
    element_B = list(map(int, input().split()))
    matrix_B.append(element_B)

# 두 행렬의 합 구하기
for i in range(N):
    for j in range(M):
        print(matrix_A[i][j] + matrix_B[i][j], end=' ')
    print()
```