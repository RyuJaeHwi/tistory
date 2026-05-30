CSS 17. z-index
=
z-index
-------

> **z-index 란?**  
> : 요소들의 쌓임 순서(stack order)를 정의하는 속성

정수 값을 지정하여 쌓임 맥락(stacking context)에서의 레벨을 정의하는 방식으로 사용합니다.

즉 위치 지정 요소에 대해 적용 가능한 속성입니다.

위치 지정 요소란? position 속성이 정의되어 있는 요소

  

#### 쌓임 맥락(Stacking context)이란?

2차원 평면의 HTML 페이지를 Z축이 있는, 즉 3차원적인 관점으로 표현하는 개념

&nbsp&nbsp=> 즉 요소들이 겹칠 때, 해당 요소가 다른 요소 위나 아래에 **쌓이는 순서**를 따져서 맥락상 우선순위를 정하는 규칙!

  

z-index의 기본값 = **auto**

여기서 auto는 새로운 쌓임 맥락이 형성되지 않은 상태!

***z-index 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>z-index</title>
<style>
div {
width: 100px;
height: 100px;
position: relative;
}
div:nth-child(1) {
background-color: yellow;
}
div:nth-child(2) {
background-color: cyan;
bottom: 50px;
}
div:nth-child(3) {
background-color: ivory;
bottom: 100px;
}
div:nth-child(4) {
background-color: mediumaquamarine;
bottom: 150px;
}
/* z-index : 숫자가 클수록 더 위에 쌓임 */
.first {
z-index: 1;
}
.second {
z-index: 2;
}
.third {
z-index: 4;
}
.fourth {
z-index: 3;
}
</style>
</head>
<body>
<div class="first">1</div>
<div class="second">2</div>
<div class="third">3</div>
<div class="fourth">4</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/df73a9f0-25e7-468b-838e-085363716cfb/image.png)

z-index 숫자가 가장 큰 3번째 div 요소가 제일 위에 올라왔습니다.