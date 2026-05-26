[파이썬] 백준 5단계 5 &lt;문자열&gt; - Q.11720
=
**Q.11720**
-----------

N개의 숫자가 공백 없이 쓰여있다. 이 숫자를 모두 합해서 출력하는 프로그램을 작성하시오.

**입력**

첫째 줄에 숫자의 개수 N (1 ≤ N ≤ 100)이 주어진다. 둘째 줄에 숫자 N개가 공백없이 주어진다.

**출력**

입력으로 주어진 숫자 N개의 합을 출력한다.

![](https://blog.kakaocdn.net/dn/qAf17/btsKsmZrZqb/oHTjs2ooV5KaaROi9kyLRK/img.png)

```
N = int(input())

# 공백없이 주어지는 숫자들 -> 문자열 형태로 숫자 출력
numbers = input()


total = 0

for i in range(N):
    # 각 인덱스 자리의 숫자들을 int()를 통해 정수화
    total += int(numbers[i])

print(total)
```