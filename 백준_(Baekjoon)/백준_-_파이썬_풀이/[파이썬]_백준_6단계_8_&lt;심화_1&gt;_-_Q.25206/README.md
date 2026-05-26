[파이썬] 백준 6단계 8 &lt;심화 1&gt; - Q.25206
=
**Q.25206**
-----------

인하대학교 컴퓨터공학과를 졸업하기 위해서는, 전공평점이 3.3 이상이거나 졸업고사를 통과해야 한다. 그런데 아뿔싸, 치훈이는 깜빡하고 졸업고사를 응시하지 않았다는 사실을 깨달았다!

치훈이의 전공평점을 계산해주는 프로그램을 작성해보자.

전공평점은 전공과목별 (학점 × 과목평점)의 합을 학점의 총합으로 나눈 값이다.

인하대학교 컴퓨터공학과의 등급에 따른 과목평점은 다음 표와 같다.

P/F 과목의 경우 등급이 P또는 F로 표시되는데, 등급이 P인 과목은 계산에서 제외해야 한다.

과연 치훈이는 무사히 졸업할 수 있을까?

**입력**

**20**줄에 걸쳐 치훈이가 수강한 전공과목의 과목명, 학점, 등급이 공백으로 구분되어 주어진다.

**출력**

치훈이의 전공평점을 출력한다.

정답과의 절대오차 또는 상대오차가 10⁻⁴ 이하이면 정답으로 인정한다.

**제한**

![](https://blog.kakaocdn.net/dn/AbV9L/btsKw3EHpqy/QhUFVXc6x5cWvLIBdj4u20/img.png)
![](https://blog.kakaocdn.net/dn/lf9d4/btsKv6vsbqE/oBGKKCQ46YqJEd8p1mdn00/img.png)
![](https://blog.kakaocdn.net/dn/n36Nj/btsKxNA9CEx/2AwMiyELcNZC1tLR5Twxrk/img.png)

과목명, 학점(float 타입), 등급이 한 줄에 입력되고 이것이 20번 반복...

여기서 등급이 P인 경우는 계산에서 제외

```
# 딕셔너리 형태로 등급에 따른 학점 데이터 저장
grade_score = {
    "A+": 4.5, "A0": 4.0,
    "B+": 3.5, "B0": 3.0,
    "C+": 2.5, "C0": 2.0,
    "D+": 1.5, "D0": 1.0,
    "F": 0.0
}

# 전체 학점
total = 0

# 입력한 수를 모두 더한 총점
sum_score = 0

for i in range(20):
    # 순서대로 과목명, 학점, 등급
    subject, score, grade = input().split()
    # 'P' 과목인 경우에는 계산X -> continue 사용
    if grade == 'P':
        continue
    score = float(score)
    sum_score += score * grade_score[grade]
    total += score

print(sum_score/total)
```