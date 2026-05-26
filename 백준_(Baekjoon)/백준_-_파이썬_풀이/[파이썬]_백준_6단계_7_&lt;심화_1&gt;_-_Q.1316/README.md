[파이썬] 백준 6단계 7 &lt;심화 1&gt; - Q.1316
=
**Q.1316**
----------

그룹 단어란 단어에 존재하는 모든 문자에 대해서, 각 문자가 연속해서 나타나는 경우만을 말한다. 예를 들면, ccazzzzbb는 c, a, z, b가 모두 연속해서 나타나고, kin도 k, i, n이 연속해서 나타나기 때문에 그룹 단어이지만, aabbbccb는 b가 떨어져서 나타나기 때문에 그룹 단어가 아니다.

단어 N개를 입력으로 받아 그룹 단어의 개수를 출력하는 프로그램을 작성하시오.

**입력**

첫째 줄에 단어의 개수 N이 들어온다. N은 100보다 작거나 같은 자연수이다. 둘째 줄부터 N개의 줄에 단어가 들어온다. 단어는 알파벳 소문자로만 되어있고 중복되지 않으며, 길이는 최대 100이다.

**출력**

첫째 줄에 그룹 단어의 개수를 출력한다.

![](https://blog.kakaocdn.net/dn/Ynq0B/btsKxrykelV/9p1b2FyqY2ECskdRrF5TA0/img.png)
![](https://blog.kakaocdn.net/dn/bqLtxw/btsKwtYcz44/fc2go11ajgTUtNBeVqB3b1/img.png)

문제에서 말하는 '그룹단어'란, 한 번 나온 알파벳은 안나오고 새로운 알파벳만 나오는 단어를 뜻한다.  
  → 즉 'abca'의 경우에는 a, b, c 가 순서대로 나온 후 다시 a가 나오니 그룹단어가 아님

```
N = int(input())
count = 0

for i in range(N):
    word = input()
    # 알파벳 하나씩 비교
    for j in range(0, len(word) - 1):
        if word[j] == word[j + 1]:
            pass  # 연속된 문자가 같으면 pass
        elif word[j] in word[j + 1:]:
            break  # 그룹 단어가 아니므로 break로 나옴
    else:
        # for문이 break 없이 끝났을 때만 그룹 단어 -> count 증가
        count += 1

print(count)
```