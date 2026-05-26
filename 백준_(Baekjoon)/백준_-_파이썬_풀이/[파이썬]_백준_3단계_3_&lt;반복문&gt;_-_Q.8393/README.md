[파이썬] 백준 3단계 3 &lt;반복문&gt; - Q.8393
=
**Q.8393**
----------

n이 주어졌을 때, 1부터 n까지 합을 구하는 프로그램을 작성하시오.

**입력**

첫째 줄에 n (1 ≤ n ≤ 10,000)이 주어진다.

**출력**

1부터 n까지 합을 출력한다.

![](https://blog.kakaocdn.net/dn/cIzsIk/btsKnlLZDhF/0eQKU4bJkHesuaQx9HEowk/img.png)

```
n = int(input())

total = 0

for i in range(1, n + 1):
    # ex) i = 4,
    # total = 1
    # total = 1 + 2 = 3
    # total = 3 + 3 = 6
    # total = 6 + 4 = 10
    total += i

print(total)
```