CSS 02. 선택자 - 기본 선택자, 그룹 선택자
=
선택자 기본 개념
---------

> **선택자란?**  
> : 어떤 요소에 스타일을 적용할 것인지에 대한 정보를 나타내는 요소`선택자{
속성명: 속성값;
}`

선택자에는 아래와 같은 종류들이 있습니다.

* **기본 선택자**
* **그룹 선택자**
* 특성 선택자
* 결합 선택자
* 의사 클래스
* 의사 요소

  

이번 글에서는 위 종류들 중에서 가장 기초라고 할 수 있는 **기본 선택자**와 **그룹 선택자**부터 공부해보려고 합니다!

기본 선택자
------

### 전체 선택자

> **전체 선택자**란, **문서 내 모든 요소를 선택**할 때 사용하는 선택자입니다.

ex)`*{
color: blue;
}`

**\*(애스타리스크)**란, **'문서 내의 모든 요소'**를 의미하는 기호입니다.

즉 위 예시 코드는, 문서 내 모든 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.

  

### 태그 선택자

> **태그 선택자**란, 해당 이름을 가진 요소만 선택할 때 사용하는 선택자입니다. (= 유형 선택자)

만약 해당 이름을 가진 요소가 문서 내 여러 개인 경우, 해당 요소들을 모두 선택합니다.

ex)`p{
color: pink;
}`

위 예시 코드는, 문서 내 모든 p 태그 요소의 텍스트 색을 분홍으로 지정한다는 뜻입니다.

  

### 클래스 선택자

> **클래스 선택자**란, 주어진 class 속성값을 가진 요소만을 선택할 때 사용하는 선택자입니다.

만약 해당 class 속성값을 가진 요소가 문서 내 여러 개인 경우, 해당 요소들을 모두 선택합니다.

ex)`.text{
color: blue;
}`

위 예시 코드는, 문서 내 class가 "text"인 모든 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.

  

### 아이디 선택자

> **아이디 산택자**란, 주어진 id 속성값을 가진 요소를 선택할 때 사용하는 선택자입니다.

여기서 id는 고유한 식별자 역할을 하는 전역 속성입니다.  
(참고 링크 추가)

ex)`#topic{
color: blue;
}`

위 예시 코드는, 문서 내id가 "topic"인 요소의 텍스트 색을 파란 색으로 지정한다는 뜻입니다.

그룹 선택자
------

> **그룹 선택자**란, 다양한 유형의 요소를 한꺼번에 선택하고자 할 때 사용하는 선택자입니다.  
> **쉼표( , )**를 이용해 선택자를 그룹화합니다.

ex)`h1, p, div{
color: green;
}`

위 예시 코드는, 문서 내 모든 h1, p, div 태그 요소의 텍스트 색을 초록색으로 지정한다는 뜻입니다.

선택자가 겹치는 경우?

만약 위 선택자들이 고른 요소들이 서로 겹치는 경우엔 어떻게 될까요?

**1) 선택자가 겹치는 경우**

=> 기본적으로 나중에 작성된 스타일이 적용됩니다. (아래에 적힌 것들)

**2) 선택자가 다르지만 요소가 겹치는 경우**

=> "선택자 우선순위"에 의해 적용될 스타일이 결정됩니다.

  
> "선택자 우선순위"

*아이디 선택자 > 클래스 선택자 > 태그 선택자*

  

이제 직접 테스트를 해보며 선택자에 대해 공부해봅시다.

***선택자 사용 예시 - 전체 선택자***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자 테스트</title>
<style>
/* 전체 선택자 스타일 */
* {
color: green;
}
</style>
</head>
<body>
<h1>제목</h1>
<p>문단 테스트1</p>
<p>문단 테스트2</p>
<p>문단 테스트3</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/7db473d6-5293-4b11-8713-0ab6ebc9873f/image.png)

먼저 전체 요소들을 선택하는 **"\*" 선택자**입니다. 이를 사용하니<body> 태그 안 모든 요소들의 텍스트 색이 green으로 바뀌었습니다.

***선택자 사용 예시 - 태그, 클래스, 아이디 선택자***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자 테스트</title>
<style>
/* 태그 선택자 스타일 */
p {
color: green;
}
/* 클래스 선택자 스타일 */
.text {
color: blue;
font-size: 32px;
}
/* 아이디 선택자 스타일 */
#number {
color: orange;
}
</style>
</head>
<body>
<h1 class="text">제목</h1>
<p id="number">문단 테스트1</p>
<p class="text">문단 테스트2</p>
<p>문단 테스트3</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/f646485f-ed84-44c2-b62c-cc3924736cd4/image.png)

결과를 보면 p 태그 요소들의 텍스트 색은 green입니다.

그런데 아래 클래스 선택자와 아이디 선택자가 나와서 이 스타일이 덮어씌어집니다. **(선택자 우선순위)**

***선택자 사용 예시 - 그룹 선택자***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>선택자 테스트</title>
<style>
/* 그룹 선택자 스타일 */
h1,
p {
color: purple;
}
/* 우선순위는 클래스 선택자 > 태그 선택자 */
.text {
color: red;
}
h1 {
color: blue;
}
</style>
</head>
<body>
<h1 class="text">제목</h1>
<p id="number">문단 테스트1</p>
<p class="text">문단 테스트2</p>
<p>문단 테스트3</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/1bdbfcdc-1e81-4e5a-a4c8-dca62f7c9fbd/image.png)

선택자 사이의 우선 순위는 *클래스 선택자 > 태그 선택자* 입니다.

즉 위 예시 코드에서는 마지막에 h1{...} 태그 선택자가 나와서 제목 텍스트 색으로 파란 색상을 지정했지만, 우선 순위로는 클래스 선택자가 먼저이므로 .text {...} 의 red 컬러가 적용된 것입니다.