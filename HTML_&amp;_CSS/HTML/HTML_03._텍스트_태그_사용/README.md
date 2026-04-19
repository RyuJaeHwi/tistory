HTML 03. 텍스트 태그 사용
=
문단(paragraph) 태그
----------------

> **p 태그** : 문단 요소를 나타내는 태그로, 가장 많이 쓰이는 텍스트 태그

하나의 p 태그는 하나의 문단을 표현하고, 문단 사이에는 공백이 있습니다.

***문단 태그 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>텍스트 태그 연습</title>
</head>
<body>
<p>텍스트를 표시하고 있습니다.</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut
labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in
voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</p>
</body>
</html>`

이 테스트 코드의 결과는 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/d9c87ec8-cc7d-45dc-a976-1defc80ca237/image.png)

개발자 모드로 확인하면 각 p 태그가 서로 다른 문단으로 되어있는 것을 확인할 수 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/5df2fa88-279e-443c-867a-0bef1fc35e8d/image.png)
  

제목(headline) 태그
---------------

> **h 태그** : 제목(표제) 요소를 나타내는 태그, 숫자와 함께 사용

h 태그는 숫자와 함께 쓰이는데, h1 ~ h6로 총 6종류입니다.

h1이 가장 큰 크기의 제목 텍스트이고 h6으로 숫자가 커질수록 제목 텍스트의 크기는 작아집니다.

***제목 태그 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>텍스트 태그 연습</title>
</head>
<body>
<h1>텍스트 태그 연습 h1</h1>
<h2>텍스트 태그 연습 h2</h2>
<h3>텍스트 태그 연습 h3</h3>
<h4>텍스트 태그 연습 h4</h4>
<h5>텍스트 태그 연습 h5</h5>
<h6>텍스트 태그 연습 h6</h6>
</body>
</html>`

이 테스트 코드의 결과는 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/c72cbee6-f904-47ba-a8e9-e8fdbbed84cd/image.png)
  

구분선
---

> **hr 태그** : 구분선을 표시하는 태그 (주제 또느 내용 구분 시 사용)

hr 태그는 콘텐츠 사이에 넣는 구분선을 표시합니다. 단일 태그로 사용합니다.

***구분선 태그 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>텍스트 태그 연습</title>
</head>
<body>
<h1>텍스트 태그 연습 h1</h1>
<p>구분선 위 텍스트 문단</p>
<hr />
<p>구분선 아래 텍스트 문단</p>
</body>
</html>`

이 테스트 코드의 결과는 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/f5cf1ec4-b530-49b8-8096-81dc4991c949/image.png)
  

줄바꿈 태그
------

> **br 태그** : 텍스트에서 줄바꿈(line **br**eak)을 나타내는 태그

br 태그는 특정 태그 밖이나 안에서 사용 가능합니다.

텍스트를 끊어 줄바꿈을 하고 싶은 부분에 사용하면 됩니다.

***줄바꿈 태그 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>텍스트 태그 연습</title>
</head>
<body>
<p>줄바꿈 하기 전 텍스트 문단</p>
<br />
<p>줄바꿈 한 후 텍스트 문단</p>
<br />
<br />
<p>
p 태그 내부에서도 br 태그로 줄바꿈이 가능합니다.
<br />
줄바꿈을 넣고 싶은 부분에 <br />바로 넣으면 됩니다.
</p>
</body>
</html>`

이 테스트 코드의 결과는 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/71872f2c-6d4f-40cf-8f9b-e892d4203515/image.png)
  

공백 표기
-----

> **&nbsp;**란? 공백을 표시하는 문자

.html 문서에서는 space바를 사용해 띄어쓰기를 아무리 많이 해도 딱 한 번만 한 것으로 인식됩니다.

ex)`<p>띄어쓰기 테스트 중인 텍스트 문단</p>`

이렇게 많이 공백을 넣어도 결과는 딱 한번 공백을 넣은 것으로 처리됩니다.

![](https://velog.velcdn.com/images/choco_dev/post/28253386-fe37-493a-a91d-0f1bef8adcd6/image.png)
  

.html 문서에서는 공백을 두 번 이상 넣으려면 **&nbsp;**을 사용해야 합니다.

***&nbsp; 공백 문자 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>텍스트 태그 연습</title>
</head>
<body>
<p>띄어쓰기&nbsp;를 테스트 중인 &nbsp;&nbsp;&nbsp;텍스트 &nbsp;&nbsp;문단</p>
</body>
</html>`

이 테스트 코드의 결과는 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/6f58c844-0965-4034-bc96-fd885cfa5e76/image.png)