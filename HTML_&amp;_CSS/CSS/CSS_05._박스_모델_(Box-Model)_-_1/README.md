CSS 05. 박스 모델 (Box-Model) - 1
=
박스 모델 (Box-Model) 이란?
---------------------

브라우저가 요소를 렌더링할 때, 각각의 요소는 보통 사각형 형태로 영역을 차지합니다. 이 영역을 **"박스"**라고 합니다.

CSS는 이러한 박스들의 크기, 위치, 속성(색, 배경, 테두리 등)을 결정합니다.

아래는 박스가 가지는 영역 4가지와, 해당 영역의 크기를 정의하는 속성입니다.

* 콘텐츠 영역 : **width, height**
* 안쪽 여백 : **padding**
* 경계선 (테두리) : **border-width**
* 바깥쪽 여백 : **margin**

  

이미지로 정리하면 다음과 같습니다.

![](https://velog.velcdn.com/images/choco_dev/post/1fd04325-803d-4341-9e71-1248df0eee28/image.png)

  

***box-model 요소 확인 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>box model</title>
<style>
div {
border: 5px solid blueviolet;
padding: 20px;
margin: 20px;
width: 150px;
height: 50px;
}
</style>
</head>
<body>
<div>요소의 콘텐츠 - box</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/3c5b87fb-8c62-4686-95b5-711dd6986b23/image.png)

하나씩 살펴보도록 하겠습니다.

우선 border입니다. 저번 글에서 배웠던 것인데, 5px 두께의 실선 테두리를 추가하였습니다.

이 border를 기준으로 안쪽 여백, 바깥쪽 여백을 구분할 수 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/bd8124a8-8cec-410b-9523-2fe342eae4a6/image.png)

위 이미지에서 초록 부분이 안쪽 여백인 padding, 주황색 부분이 바깥쪽 여백인 margin입니다. 그 사이 보라색이 border이고 이것으로 구분합니다.

가장 내부 파란 부분은 콘텐츠 영역이에요.

코드에서 준 값인 padding=20px, margin=20px이 잘 적용되었고 콘텐츠 영역도 150px \* 50px 크기로 이루어진 것을 볼 수 있습니다.

다른 것도 확인해보도록 하겠습니다.

***box-model 요소 확인 예시2***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>box model</title>
<style>
span {
width: 100px;
height: 60px;
}
</style>
</head>
<body>
<span>영역 check</span>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/6424c515-e6d7-4474-9627-d89e4e3a7f04/image.png)

style 태그로 span 영역에 width와 height를 넣었는데 적용이 안 됩니다. 왜 그럴까요?

span 같은 인라인 요소는 width와 height 값 지정이 안됩니다. 이미 해당 요소가 사용하는 만큼의 영역만 차지하기 때문인데, 그럼 어떻게 지정할 수 있을까요?

저번에 공부했던 display의 inline-block 옵션을 추가하면 됩니다!

***box-model 요소 확인 예시3***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>box model</title>
<style>
span {
display: inline-block;
width: 100px;
height: 60px;
}
</style>
</head>
<body>
<span>영역 check</span>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/c737fa56-c1de-46e1-a1c5-5c6bd380bd0a/image.png)

inline-block을 추가하였더니 span에도 width랑 height 값이 적용되는 것을 확인할 수 있습니다.