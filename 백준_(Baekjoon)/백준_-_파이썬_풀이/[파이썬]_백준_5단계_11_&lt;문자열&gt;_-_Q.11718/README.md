[파이썬] 백준 5단계 11 &lt;문자열&gt; - Q.11718
=
**Q.11718**
-----------

입력 받은 대로 출력하는 프로그램을 작성하시오.

**입력**

입력이 주어진다. 입력은 최대 100줄로 이루어져 있고, 알파벳 소문자, 대문자, 공백, 숫자로만 이루어져 있다. 각 줄은 100글자를 넘지 않으며, 빈 줄은 주어지지 않는다. 또, 각 줄은 공백으로 시작하지 않고, 공백으로 끝나지 않는다.

**출력**

입력받은 그대로 출력한다.

![](https://blog.kakaocdn.net/dn/ymmp4/btsKtSceuSk/RfRHR9cZN2TqifRttncdQk/img.png)

**EOFError**란?  
 : *입력의 끝(End Of File, EOF)*에 도달했음을 나타내는 *예외(Error)*

```
while True:
    try:
        S = input()
        print(S)
    # EOFError에 도달하면 종료
    #  -> Ctrl + Z 클릭 시 해당 EOFError에 도달하게 됨
    #     = 아무것도 입력 안하는거랑은 다름
    except EOFError:
        break
```