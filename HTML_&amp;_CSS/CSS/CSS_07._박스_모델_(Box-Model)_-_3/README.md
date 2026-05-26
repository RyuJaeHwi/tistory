CSS 07. 박스 모델 (Box-Model) - 3
=
box-sizing
----------

> **box-sizing 이란?**  
> : 해당 요소의 너비(width)와 높이(height)를 계산하는 방법을 지정하는 속성

너비와 높이가 같더라도, box-sizing 속성값에 따라 크기가 달라질 수 있습니다.

아래는 해당 box-sizing 속성값을 정리한 표입니다.

| 속성값 | 의미 |
| --- | --- |
| content-box | 기본값, 너비와 높이가 콘텐츠 영역만을 포함&nbsp |
| border-box | 너비와 높이가 안쪽 여백과 테두리까지 포함 |

  
  
만약 200px \* 20px의 너비와 높이 콘텐츠인 경우...

* **content-box** : 내부 콘텐츠 영역 크기만 200px \* 20px
* **border-box** : border와 padding까지 합하여 200px \* 20px

이렇게 값이 계산되어 나타납니다.

아래 예시를 통해 어떤 식으로 값이 적용되는지 확인해보겠습니다.

***box-sizing 적용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>box-sizing</title>
<style>
div {
width: 200px;
padding: 20px;
border: 10px solid black;
margin-bottom: 20px;
}
.content-box {
box-sizing: content-box;
}
.border-box {
box-sizing: border-box;
}
</style>
</head>
<body>
<div class="content-box">content-box</div>
<div class="border-box">border-box</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/34138dbf-8025-424c-9d66-51c5b758ac06/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/8b704d17-0a92-4330-8f9c-0445cfcbe560/image.png)

결과를 보면 content-box 속성인 div 박스는 width: 200px가 내부 콘텐츠 영역의 너비로만 적용되었습니다.

그래서 padding 값과 border 값까지 합하여,  
**200px + 40px + 20px = 260px** 이렇게 되었습니다.

반대로 border-box 속성인 div 박스는 padding 값과 border 값까지 다 합하여 width: 200px이 적용됩니다.

그래서 내부 콘텐츠 영역이 그 값들만큼 줄어든 것을 확인할 수 있습니다.