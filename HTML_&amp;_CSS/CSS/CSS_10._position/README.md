CSS 10. position
=
position
--------

> **position 이란?**  
> : 요소의 위치 지정 방식을 설정하는 속성

position이 요소의 위치를 어떻게 배치할 지 먼저 방법을 정합니다.

그리고 그 다음 top, bottom, right, left가 각각의 값을 통해 세부적으로 요소의 위치를 조절하여 결정합니다.

* **position** : 요소의 배치 방식
* **top** : 위에서부터 얼만큼 떨어뜨릴지 값 지정
* **right** : 오른쪽에서부터 얼만큼 떨어뜨릴지 값 지정
* **bottom** : 아래에서부터 얼만큼 떨어뜨릴지 값 지정
* **left** : 왼쪽에서부터 얼만큼 떨어뜨릴지 값 지정

  

position의 배치 방식에는 다음과 같은 키워드들이 있습니다.

| 속성값 | 의미 |
| --- | --- |
| static | 기본값, 요소를 일반적인 문서 흐름에 따라 배치 |
| relative | 일반적인 문서 흐름에 따라 배치하되, 상하좌우 위치 값에 따라 오프셋 적용 |
| absolute | 일반적인 문서 흐름에서 제거 후, 가장 가까운 position 지정 요소에 대한 상대적 오프셋 적용 |
| fixed | 일반적인 문서 흐름에서 제거 후, 지정한 위치에 **고정** |
| sticky | 일반적인 문서 흐름에서 제거 후, 스크롤 동작이 존재하는 가장 가까운 요소에 대한 오프셋 적용 |

  

### position: static;

**position: static** 속성은 top, bottom, right, left 세부 값을 지정할 수 없는 정적인(static) 위치 지정 방식입니다.

위에서부터 일반적인 문서 흐름대로 배치됩니다.

***position: static 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>position</title>
<style>
div {
width: 100px;
height: 100px;
background-color: rosybrown;
position: static;
top: 100px;
left: 200px;
}
</style>
</head>
<body>
<div></div>
<p>p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/cf64c655-38ec-43e7-9020-a98548796414/image.png)

style로 top과 left 값을 지정했는데 적용되지 않습니다.

  

### position: relative;

**position: relative** 속성은 요소를 일반적인 문서 흐름에 따라 배치하는 것은 static과 똑같습니다.

그러나 상하좌우 위치 값에 따라 **오프셋**을 적용한다는 차이점이 있습니다.

오프셋이란? 위치를 얼마만큼 이동시키는지 지정하는 값

  

***position: relative 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>position</title>
<style>
div {
width: 100px;
height: 100px;
background-color: rosybrown;
position: relative;
top: 100px;
left: 200px;
}
</style>
</head>
<body>
<div></div>
<p>p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/fd56af85-f2d0-465e-80d6-76c8165978cb/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/4e4df146-c0a8-4547-b6fa-320df1af28d5/image.png)

위에서부터 100px, 왼쪽에서부터 200px 떨어뜨린 위치에 배치된 것을 볼 수 있습니다.

  

### position: absolute;

**position: absolute** 속성은 요소를 일반적인 문서 흐름에서 제거 후,상위 요소 중 가장 가까운 position 지정 요소에 대해 상대적인 오프셋을 적용합니다.

position 지정 요소란? position 속성에 속성값이 정의되어 있는 요소!

  

***position: absolute 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>position</title>
<style>
div {
width: 200px;
height: 200px;
background-color: blanchedalmond;
position: relative;
border: 2px solid black;
}
.absolute {
width: 100px;
height: 100px;
background-color: red;
position: absolute;
top: 50px;
left: 150px;
}
</style>
</head>
<body>
<div></div>
<div>
<div class="absolute"></div>
<p>p태그p태그p태그</p>
</div>
<p>p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그p태그</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/b05ff567-5e6f-40a0-99b7-b99467f70ecb/image.png)

class="absolute"의 빨간 div 박스는 absolute입니다. 즉 position 속성을 가진 가장 가까운 상위 요소에 맞춰서 위치가 지정됩니다.

class="absolute" div의 상위 요소는 div로, 두 번째 위치의 베이지색 div 박스입니다.

이 div 박스를 기준으로 세부 위치를 지정합니다.

위로 50px, 왼쪽으로 150px 떨어진 곳에 배치하도록 설정해서 저렇게 나타났습니다.

top과 left 값을 바꾸어보면 어떻게 될까요?

![](https://velog.velcdn.com/images/choco_dev/post/6b672ad4-909f-47d6-836d-d8fe6f1c8927/image.png)

top: 10px, left: 80px 으로 설정하니 이런 식으로 배치되었습니다.

즉 absolute는 자신보다 상위 요소 중 position 속성을 가진 가장 가까운 요소를 기준으로 세부적인 배치 값을 적용한다는 것을 알 수 있습니다.

### position: fixed;

**position: fixed** 속성은 문서 흐름을 무시하고 브라우저 화면을 기준으로 요소를 배치합니다.

  

***position: fixed 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>position</title>
<style>
.fixed {
width: 200px;
height: 200px;
background: tomato;
position: fixed;
top: 50px;
left: 150px;
}
</style>
</head>
<body>
<div>
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
</div>
<div class="fixed"></div>
<div>
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/b6dd67c2-31f2-42fc-aa30-b104d57a4309/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/1350882c-642b-477e-9e82-d4d6a3a95de1/image.png)

결과를 보면 스크롤을 위아래로 계속 바꾸어도 div 박스의 위치는 고정되어 있습니다.

이처럼 fixed는 문서 흐름과는 상관없이 지정된 위치에 고정시킵니다.

  

### position: sticky;

**position: sticky** 속성은 스크롤 기능에 따라 position이 지정됩니다.

스크롤을 하다가 브라우저에서 설정한 위치가 되면 해당 요소의 배치가 결정됩니다.

  

***position: sticky 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>position</title>
<style>
.sticky {
width: 200px;
height: 200px;
background: tomato;
position: sticky;
top: 50px;
left: 150px;
}
</style>
</head>
<body>
<div>
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
첫번째<br />첫번째<br />첫번째<br />첫번째<br />
</div>
<div class="sticky"></div>
<div>
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
두번째<br />두번째<br />두번째<br />두번째<br />
</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/7d06b877-06da-4060-80cb-efb14d1810b4/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/a868ebdc-86bb-4e80-8170-bd1361f3f9ac/image.png)

처음에는 아래에 있었지만, 스크롤을 하다가 top: 50px, left: 150px인 위치가 되는 순간 해당 위치에 고정되어 멈춥니다.

이는 위로 다시 스크롤을 하면 처음처럼 아래로 돌아갑니다.