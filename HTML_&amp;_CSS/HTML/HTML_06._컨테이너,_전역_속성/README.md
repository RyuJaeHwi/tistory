HTML 06. 컨테이너, 전역 속성
=
컨테이너 태그
-------

> **컨테이너 태그란?**  
> : 콘텐츠나 레이아웃에 아무런 영향을 주지 않고, 여러 요소들을 묶어 관리하기 편하게 해주는 태그

보통의 개발자들은 콘텐츠 내용을 구분하거나 공통적인 스타일을 적용할 때 컨테이너를 사용합니다.

아래 두 가지 태그가 컨테이너 역할을 하는 태그들입니다.

* **<div> ~ </div>** : 블록 레벨 컨테이너
* **<span> ~ </span>** : 인라인 레벨 컨테이너

  
직접 코드를 작성해보며 컨테이너 영역이 어떤 식으로 이루어지는지 확인해보도록 하겠습니다.
  
  

***컨테이너 영역 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>영역 구분</title>
</head>
<body>
<div>
<h2>컨테이너로 영역 구분 - 블록 레벨</h2>
<p>블록 레벨 영역 내부</p>
<img src="test.png" alt="인트로" width="450" height="150" />
</div>
<br />
<div>
<h2>컨테이너로 영역 구분 - 인라인 레벨</h2>
<p>인라인 레벨 영역 내부</p>
<p>이 문단 텍스트에서 <span>인라인 레벨 영역</span>은 이 부분입니다.</p>
</div>
</body>
</html>`  
![](https://velog.velcdn.com/images/choco_dev/post/d24a1888-975b-446f-ab39-5269d862d08e/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/3e83d077-d60c-4eac-a911-e4eea9cbfdb3/image.png)

결과를 보면, 총 두 개의 div 태그가 각각의 영역을 차지하고 그 안에 콘텐츠들을 표기합니다.

![](https://velog.velcdn.com/images/choco_dev/post/ad6e1b1c-ca4c-4409-ae1c-aa5667a6726f/image.png)

그리고 인라인 레벨의 컨테이너 태그인 span은 해당 요소의 영역만큼만 차지하여 표기하는 것을 볼 수 있습니다.

이렇게 컨테이너 태그는 콘텐츠에 아무런 영향이 없지만, 각 요소들을 묶어서 편리하게 관리할 수 있도록 도와줍니다.

  

전역 속성
-----

> **전역 속성(Global attributes) 이란?**  
> : 모든 html 태그에서 공통으로 사용 가능한 속성

수많은 속성들 중에서 공통적으로 쓰이는 것들을 전역 속성이라고 부릅니다. 대표적인 전역 속성은 다음과 같습니다.

* **id** : 요소에 고유한 이름을 부여하는 식별자 역할 속성
* **class** : 요소를 그룹 별로 묶을 수 있는 식별자 역할 속성
* **style** : 요소에 적용할 CSS 스타일을 선언하는 속성
* **title** : 요소의 추가 정보를 제공하는 텍스트 속성, 사용자에게 툴팁 제공

  

***전역 속성 사용하기 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>전역 속성</title>
</head>
<body>
<h1>오늘 할 일</h1>
<div id="study">
<h2 class="title">공부하기</h2>
<p>html, css 강의 들은 후, 노트 정리하기</p>
</div>
<hr />
<div id="workout">
<h2 class="title">운동하기</h2>
<p>걷기 30분, 헬스장 pt 강습 듣기</p>
</div>
</body>
</html>`  

id와 class 전역 속성은 태그명이 서로 같은 요소들을 식별하기 위해 사용합니다.

예를 들어 위 예시에서는 div 태그 컨테이너가 두 갠데, 여기에 id 속성을 넣어서 각각 어떤 컨테이너인지 구분할 수 있도록 도와줍니다.

그리고 id는 태그당 하나씩만 지정해야 하지만, class는 다중 지정 및 중복 사용이 가능합니다.

예를 들어 위 예시에서 id="study"는 해당 div 태그만 갖고 있어야 합니다.  
그러나 내부 h2 태그의 class="title"은 모든 h2 태그들이 갖고 있는걸 확인할 수 있습니다.