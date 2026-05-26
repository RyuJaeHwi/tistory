[파이썬] 백준 7단계 2 &lt;2차원 배열&gt; - Q.2566
=
**Q.2566**
----------

<그림 1>과 같이 9×9 격자판에 쓰여진 81개의 자연수 또는 0이 주어질 때, 이들 중 최댓값을 찾고 그 최댓값이 몇 행 몇 열에 위치한 수인지 구하는 프로그램을 작성하시오.

예를 들어, 다음과 같이 81개의 수가 주어지면

![](https://blog.kakaocdn.net/dn/bDgYp6/btsKyzKDuFi/vJYswQVxxyyKADtm0GCzP1/img.png)

이들 중 최댓값은 90이고, 이 값은 5행 7열에 위치한다.

**입력**

첫째 줄부터 아홉 번째 줄까지 한 줄에 아홉 개씩 수가 주어진다. 주어지는 수는 100보다 작은 자연수 또는 0이다.

**출력**

첫째 줄에 최댓값을 출력하고, 둘째 줄에 최댓값이 위치한 행 번호와 열 번호를 빈칸을 사이에 두고 차례로 출력한다. 최댓값이 두 개 이상인 경우 그 중 한 곳의 위치를 출력한다.

![](https://blog.kakaocdn.net/dn/nvyL0/btsKzd8rvYN/h19kY0NWaX94sfkY4QIKRk/img.png)

```
# 9 * 9 행렬을 저장할 빈 리스트
matrix = []

# 9 * 9 행렬에 입력한 값 추가 (+ 리스트로 변환)
for i in range(9):
    row = list(map(int, input().split()))
    matrix.append(row)

max_value = 0 # 현재까지 찾은 최댓값
row = 0 # 위 최댓값의 행 위치
col = 0 # 위 최댓값의 열 위치

# 입력된 전체 9 * 9 행렬의 1행 1열부터 하나씩 돌아가며 값을 비교
#  현재 저장된 값보다 큰 값을 발견하면 max_value, row, col 전부 갱신
for i in range(9):
    for j in range(9):
        if matrix[i][j] >= max_value:
            max_value = matrix[i][j]
            row = i+1
            col = j+1

print(max_value)
print(row, col)
```