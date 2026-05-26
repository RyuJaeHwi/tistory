CSS 13. 선택자 - 특성 선택자, 결합 선택자
=
특성 선택자
------

### 특성 선택자의 특징

**특성 선택자(속성 선택자)**는 주어진 속성의 존재 여부나 그 값에 따라 요소를 선택합니다.

ex) 클래스 속성을 가진 요소 선택하기`[class]{
background-color: tomato;
}`

ex) 클래스가 "item"인 요소 선택하기`[class="item"]{
background-color: tomato;
}`  

### 특성 선택자의 값 확인

특성 선택자는 **기호를 추가**하여 요소를 선택하는 방식을 다양하게 만들 수 있습니다.

ex) 클래스 값에 **"it"가 포함**되는 요소 선택`[class *= "it"]{ color: white; }`

ex) 클래스 값이 **"it"로 시작**하는 요소 선택`[class ^= "it"]{ color: white; }`

ex) 클래스 값이 **"it"로 끝**나는 요소 선택`[class $= "it"]{ color: white; }`  

***특성 선택자 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자</title>
<style>
[class*="t"] {
color: green;
}
[id="unique"] {
color: blueviolet;
}
[class^="my"] {
color: pink;
}
[id$="sh"] {
color: red;
}
</style>
</head>
<body>
<h1>선택자 연습</h1>
<p>1번 문단 - p 태그</p>
<p class="item">2번 문단 - 클래스가 있는 p 태그</p>
<p id="unique">3번 문단 - 아이디가 있는 p 태그</p>
<p class="text">4번 문단 - 클래스가 있는 p 태그</p>
<p class="myclass">5번 문단 - 클래스가 있는 p 태그</p>
<p id="finish">6번 문단 - 아이디가 있는 p 태그</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/d07b2d8f-5129-42a1-a59f-c4f2c960fb12/image.png)

[class\*="t"]는 "t" 문자가 포함되는 클래스를 가진 요소들의 색을 green으로 바꿉니다.

[id="unique"]는 id가 "unique"인 요소의 색을 blueviolet로 바꿉니다.

[class^="my"]는 "my" 문자로 시작하는 클래스를 가진 요소들의 색을 pink로 바꿉니다.

[id$="sh"]는 "sh" 문자로 끝나는 id를 가진 요소들의 색을 red로 바꿉니다.

  

결합 선택자
------

### 결합 선택자의 특징

결합 선택자(결합자)는 두 개 이상의 선택자를 결합시키고, 결합된 조건을 만족하는 요소를 선택합니다.

이 결합 선택자의 종류는 두 개로 구분합니다.

* **자손 결합자**
* **형제 결합자**

  

### 결합 선택자 : 자손 결합자

두 개의 선택자 중, 첫 번째 선택자 요소의 자손을 선택할 수 있습니다.

ex) div 요소 안에 위치하는 모든 p 요소 선택`div p{ color: white; }`

ex) div 요소의 **바로 아래에 위치**하는 모든 p 요소 선택`div > p{ color: white; }`  

***자손 결합자 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자</title>
<style>
body h1 {
color: brown;
}
p > span {
color: red;
font-size: 24px;
}
</style>
</head>
<body>
<h1>선택자 연습</h1>
<p>1번 문단 - p 태그</p>
<p class="item">2번 문단 - 클래스가 있는 p 태그</p>
<p id="unique">3번 문단 - 아이디가 있는 p 태그</p>
<p class="text">4번 문단 - 클래스가 있는 p 태그</p>
<p class="myclass">5번 문단 - 클래스가 있는 p 태그</p>
<p id="finish">6번 문단 - 아이디가 있는 p 태그</p>
<p>7번 문단 - <span>span 태그가 있는</span>p 태그</p>
<h3>마지막 문단</h3>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/e52fe8e0-ad70-43d5-8ccd-c505fa3a3784/image.png)

body 안의 모든 h1 요소들의 색을 brown으로, p 태그 안의 span 요소의 텍스트색과 크기를 조절하였습니다.

여기서 span 태그 요소는 상위 요소가 p 태그인데, 자손 결합자는 자신의 바로 아래에 있는 자식 요소만 선택 가능합니다.

즉 body > span { ... } 이런 형태는 불가능하며 바로 위, 아래 관계여야 합니다.

  

### 결합 선택자 : 형제 결합자

두 개의 선택자 중, 첫 번째 선택자 요소의 형제를 선택할 수 있습니다.

ex) h1 요소의 뒤에 오는 형제 중, 모든 p 요소 선택`h1 ~ p{ color: red; }`

ex) h1 요소의 바로 뒤에 오는 형제 p 요소 선택`h1 + p{ color: red; }``<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자</title>
<style>
/* h1 안의 모든 p 태그 선택 (span 태그 제외됨) */
h1 ~ p {
color: rebeccapurple;
}
/* 클래스가 text인 요소 바로 아래 p 태그만 선택 */
.text + p {
color: green;
}
/* 클래스가 myclass인 요소 바로 아래 p 태그만 선택 */
.myclass + p {
color: red;
}
</style>
</head>
<body>
<h1>선택자 연습</h1>
<p>1번 문단 - p 태그</p>
<p class="item">2번 문단 - 클래스가 있는 p 태그</p>
<p id="unique">3번 문단 - 아이디가 있는 p 태그</p>
<p class="text">4번 문단 - 클래스가 있는 p 태그</p>
<p class="myclass">5번 문단 - 클래스가 있는 p 태그</p>
<p id="finish">6번 문단 - 아이디가 있는 p 태그</p>
<p>7번 문단 - <span>span 태그가 있는</span>p 태그</p>
<h3>마지막 문단</h3>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/de470c09-cb03-4521-b6d9-b2ffad6d99eb/image.png)

h1 태그 다음에 나오는 모든 p 태그 요소들을 rebeccapurple 색상으로 바꿉니다.

그리고 class="text"인 요소 뒤에 나오는 p 태그 요소의 텍스트 색은 green으로,

class="myclass"인 요소 뒤에 나오는 p 태그 요소의 텍스트 색은 red로 바꿉니다.