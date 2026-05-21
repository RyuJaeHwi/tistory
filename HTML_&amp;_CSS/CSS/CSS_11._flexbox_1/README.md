CSS 11. flexbox 1
=
flexbox
-------

> **flexbox 란?**  
> 박스 내 요소 간의 공간 배분과 정렬 기능을 제공하기 위한 1차원 레이아웃 모델

여기서 flexbox를 1차원 모델이라 부르는 이유는, 레이아웃을 다룰 때 한 번에 하나의 차원만 다루기 때문입니다.

즉 한 번에 행, 또는 열 하나만 다룹니다. (동시에 X)

![](https://velog.velcdn.com/images/choco_dev/post/b0b3ae60-9527-48da-83da-7202f1fbf48c/image.png)

  

### flexbox 만들기

flexbox는 flex 컨테이너라고도 불립니다. (= 요소들을 포함)

flexbox를 만들기 위해선, 컨테이너가 되는 요소에 **display: flex;**를 적용하면 됩니다.

ex)  
flexbox 적용 전...`<div>
<div class="item">요소1</div>
<div class="item">요소2</div>
<div class="item">요소3</div>
</div>`


![](https://velog.velcdn.com/images/choco_dev/post/0241dced-b086-445f-9c92-0159e2b6c841/image.png)

  
flexbox 적용 후`<div style="display: flex">
<div class="item">요소1</div>
<div class="item">요소2</div>
<div class="item">요소3</div>
</div>`


![](https://velog.velcdn.com/images/choco_dev/post/484f4607-66d7-400f-8723-d7232ed8c63c/image.png)

각 요소가 개별로 취급되어 위에서부터 하나씩 쌓이던 것을 display: flex; 속성을 추가하여 하나의 컨테이너로 취급되고 나란히 배치되게 하였습니다.

  

flex-direction
--------------

flexbox에는 **"주축(main-axis)"**과 **"교차축(cross-axis)"**이 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/d97df509-8d51-401a-9915-7cbaf2b41f80/image.png)

> **flex-direction 이란?**  
> : flexbox 내 요소를 배치할 때 사용할 주축과 방향(정방향, 역방향)을 지정하는 속성

| 속성값 | 의미 |
| --- | --- |
| row | 기본값, 주축은 행이고 방향은 콘텐츠의 방향과 동일&nbsp&nbsp |
| row-reverse | 주축은 행이고 방향은 콘텐츠의 방향과 반대 |
| column | 주축은 열이고 방향은 콘텐츠의 방향과 동일 |
| column-reverse | 주축은 열이고 방향은 콘텐츠의 방향과 반대 |

***flex-direction 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>flexbox</title>
<style>
.container {
display: flex;
/* row = 행, column = 열 */
flex-direction: row;
}
.item {
width: 80px;
height: 80px;
background-color: pink;
}
</style>
</head>
<body>
<div class="container">
<div class="item">1</div>
<div class="item">2</div>
<div class="item">3</div>
</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/5b159dd0-689d-4160-a586-51ceb7a5e216/image.png)

기본값인 **flex-direction: row;** 속성일 때의 결과입니다.

이제 flex-direction 속성을 다른 것들로 하나씩 바꿔보도록 하겠습니다.`.container {
display: flex;
/* row = 행, column = 열 */
flex-direction: row-reverse;
}`![](https://velog.velcdn.com/images/choco_dev/post/592fecf2-f410-47e1-a377-856d4d76306f/image.png)

**flex-direction: row-reverse** 속성으로 바꿨더니, 요소가 오른쪽부터 반대 방향으로 나열됩니다.`.container {
display: flex;
/* row = 행, column = 열 */
flex-direction: column;
}`![](https://velog.velcdn.com/images/choco_dev/post/c3ec5a31-58ae-4637-a063-8e891a1d2b28/image.png)

**flex-direction: column** 속성은 교차축 방향으로 요소들이 나열됩니다.`.container {
display: flex;
/* row = 행, column = 열 */
flex-direction: column-reverse;
}`![](https://velog.velcdn.com/images/choco_dev/post/655fc1d6-81a7-4ba1-acd4-422f07aa60cf/image.png)

**flex-direction: column-reverse** 속성으로 바꾸니, 기존의 요소들이 거꾸로 나열되는 것을 확인할 수 있습니다.