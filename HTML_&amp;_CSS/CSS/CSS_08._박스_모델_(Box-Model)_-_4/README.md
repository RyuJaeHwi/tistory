CSS 08. 박스 모델 (Box-Model) - 4
=
background
----------

**배경(background)**은 콘텐츠의 배경을 정의합니다.

단축 속성이며 색상, 이미지, 반복 등 다양한 하위 속성을 추가할 수 있습니다.  
아래 표는 배경의 하위 속성 중 일부입니다.

| 하위 속성 | 역할 |
| --- | --- |
| background-color | 배경 색상 정의 |
| background-image | 배경 이미지 정의 |
| background-position | 배경 이미지의 초기 위치 정의 |
| background-size | 배경 이미지의 크기 정의 |
| background-repeat | 배경 이미지의 반복 방법 정의&nbsp&nbsp&nbsp |

  
  

***background 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>background</title>
<style>
div {
box-sizing: border-box;
width: 400px;
height: 300px;
border: 2px solid maroon;
}
.github {
background-color: blanchedalmond;
background-image: url(../githublogo.png);
}
</style>
</head>
<body>
<div class="github">깃허브</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/0c3bbddd-7a92-4b67-b63c-14760ad4669f/image.png)

깃허브 아이콘을 이미지로 해서 400px \* 300px 크기의 div안에 넣었습니다.

그러나 이미지의 기본 크기가 매우 커서 div 안에 다 담기지 않는 모습입니다. 이는 어떻게 해결해야 할까요?

속성으로 **background-size: cover;**을 추가했습니다. 이 속성은 이미지가 찌그러지지 않는 내에서 최대 사이즈로 들어갈 수 있도록 자동으로 맞춰줍니다.`.github {
background-color: blanchedalmond;
background-image: url(../githublogo.png);
background-size: cover;
}`![](https://velog.velcdn.com/images/choco_dev/post/b3c53e74-8cf9-4f0b-a555-8892dcfe9bcb/image.png)

이미지가 조금 짤렸지만, 위에서 설정한 400px \* 300px 크기에 최대한 맞도록 이미지가 들어간 것을 알 수 있습니다.

cover는 이렇게 짤리는 것을 감안하고 빈 공간 없이 이미지를 채웁니다.

cover와는 다른 속성도 있습니다. contain인데, 이는 이미지가 잘리지 않고 원본 그대로 나올 수 있는 최대 크기를 맞춰서 보여줍니다.`.github {
background-color: blanchedalmond;
background-image: url(../githublogo.png);
background-size: contain;
}`![](https://velog.velcdn.com/images/choco_dev/post/3367b7d6-f52f-4509-9887-5a9ceeb0af2f/image.png)
  

그런데 같은 이미지가 반복되어 들어가다가 잘리니 조금 지저분한 것처럼 보일 수 있습니다.

이러한 이미지의 반복을 없애려면 어떻게 해야할까요?

**background-repeat: no-repeat;** 속성을 추가하면 됩니다.

기본적으로 반복을 하는 repeat가 기본값이며, no-repeat을 넣으면 이미지가 반복되지 않습니다.`.github {
background-color: blanchedalmond;
background-image: url(../githublogo.png);
background-size: contain;
background-repeat: no-repeat;
}`![](https://velog.velcdn.com/images/choco_dev/post/6c5004bf-9b0b-481b-bb23-540fc8f6d532/image.png)

이미지가 반복되지 않고 한 번만 들어가며, 나머진 여백으로 처리되는 것을 확인할 수 있습니다.

이제 이미지 사이즈와 위치를 마음대로 커스텀하도록 하겠습니다.

각각 background-size와 background-position을 사용하면 됩니다.`.github {
background-color: blanchedalmond;
background-image: url(../githublogo.png);
background-size: 200px 100px;
background-position: right bottom;
background-repeat: no-repeat;
}`![](https://velog.velcdn.com/images/choco_dev/post/56ad5336-d63c-4956-9325-9fe174545253/image.png)

200px \* 100px 크기로 이미지가 맞춰져서 찌그러진 채로 들어갑니다.

위치도 오른쪽 아래로 알맞게 배치된 것을 알 수 있습니다.