[파이썬] 백준 5단계 7 &lt;문자열&gt; - Q.2675
=
**Q.2675**
----------

문자열 S를 입력받은 후에, 각 문자를 R번 반복해 새 문자열 P를 만든 후 출력하는 프로그램을 작성하시오. 즉, 첫 번째 문자를 R번 반복하고, 두 번째 문자를 R번 반복하는 식으로 P를 만들면 된다. S에는 QR Code "alphanumeric" 문자만 들어있다.

QR Code "alphanumeric" 문자는 0123456789ABCDEFGHIJKLMNOPQRSTUVWXYZ\$%\*+-./: 이다.

**입력**

첫째 줄에 테스트 케이스의 개수 T(1 ≤ T ≤ 1,000)가 주어진다. 각 테스트 케이스는 반복 횟수 R(1 ≤ R ≤ 8), 문자열 S가 공백으로 구분되어 주어진다. S의 길이는 적어도 1이며, 20글자를 넘지 않는다. 

**출력**

각 테스트 케이스에 대해 P를 출력한다.

![](https://blog.kakaocdn.net/dn/bq1ZDN/btsKtWsa7d9/WSB3JDZWoA1yhel5frSYp1/img.png)

```
T = int(input())

for i in range(T):
    R, S = input().split()
    R = int(R)
    # 문자열 S에서 하나씩 뺀다음 횟수 R과 곱하여 출력
    # end='' 는 줄바꿈 없이 이어서 출력한다는 의미
    for j in S:
        print(j * R, end='')
    # 출력 후 줄바꿈 & 그 다음 문자열에 대한 계산 for문 작동
    print()
```