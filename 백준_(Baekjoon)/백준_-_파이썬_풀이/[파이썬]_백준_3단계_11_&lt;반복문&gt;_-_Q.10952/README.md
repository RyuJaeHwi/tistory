[파이썬] 백준 3단계 11 &lt;반복문&gt; - Q.10952
=
**Q.10952**
-----------

두 정수 A와 B를 입력받은 다음, A+B를 출력하는 프로그램을 작성하시오.

**입력**

입력은 여러 개의 테스트 케이스로 이루어져 있다.

각 테스트 케이스는 한 줄로 이루어져 있으며, 각 줄에 A와 B가 주어진다. (0 < A, B < 10)

입력의 마지막에는 0 두 개가 들어온다.

**출력**

각 테스트 케이스마다 A+B를 출력한다.

![](https://blog.kakaocdn.net/dn/z1FQu/btsKnSvKvw2/VxWk9nUj0KjLgoitXyhsYK/img.png)

```
while True:
    A, B = map(int, input().split())
    
    if A == 0 and B == 0:
        break
    print(A + B)
```