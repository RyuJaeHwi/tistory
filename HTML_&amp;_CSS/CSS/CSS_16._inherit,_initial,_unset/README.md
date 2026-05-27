CSS 16. inherit, initial, unset
=
상속(Ingeritance)
---------------

> **상속(Ingeritance) 이란?**  
> : 하위 요소가 상위 요소의 스타일 속성값을 물려받는 것

이 상속 기능이 이루어지는 속성과, 영향을 받지 않는 속성이 따로 있습니다.

아래 표는 이러한 속성들을 구분한 것입니다.

| 상속 여부 | 상속 O | 상속 X |
| --- | --- | --- |
| 속성 | &nbsp&nbsp&nbspcolor, font-family, font-size, font-&nbsp&nbsp&nbspweight, text-align, cursor 등 | &nbsp&nbsp&nbspbackground-color, background-image, &nbsp&nbsp&nbspbackground-repeat, border, display 등 |

  

***상속(Ingeritance) 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>의사 요소</title>
<style>
div {
display: flex;
justify-content: center;
align-items: center;
width: 300px;
height: 300px;
/* p 태그의 텍스트는 아래 tomato 색을 상속받음
(따로 p 태그 스타일이 있으면 해당 스타일 적용) */
color: tomato;
font-size: 24px;
border: 3px dashed violet;
}
p {
border: 1px solid blue;
}
</style>
</head>
<body>
<div>
<p>가운데 p 태그</p>
</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/2e46f5f6-f10f-4612-bb6c-c817c5709b89/image.png)

p 태그 요소에는 텍스트 색을 따로 지정하지 않았지만 div 태그 요소가 가진 color: tomato; 색상이 그대로 상속되었습니다.

  `p {
color: teal;
border: 1px solid blue;
}`![](https://velog.velcdn.com/images/choco_dev/post/065628c2-2343-47fa-b1c7-2986013d3706/image.png)

p 태그 요소에 따로 색상 속성을 추가하면, 해당 속성을 우선적으로 적용합니다.

  

공용 키워드
------

> **공용 키워드란?**  
> : 모든 CSS 속성에 사용 가능한 키워드, "전역 값"이라고도 표현

아래는 공용 키워드의 종류를 정리한 것입니다.

| 키워드 | 의미 |
| --- | --- |
| inherit | 상위 요소로부터 해당 속성의 값을 받아 사용 |
| initial | (브라우저에 지정되어 있는) 해당 속성의 기본값을 요소에 적용 |
| unset | 상속 속성에 대해서는 inherit처럼, 상속되지 않는 속성에 대해서는 initial처럼 적용&nbsp&nbsp |

  
  

***공용 키워드 사용 예시1***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>의사 요소</title>
<style>
div {
display: flex;
justify-content: center;
align-items: center;
width: 300px;
height: 300px;
color: tomato;
font-size: 36px;
border: 3px dashed violet;
}
p {
color: initial;
font-size: inherit;
border: inherit;
}
</style>
</head>
<body>
<div>
<p>가운데 p 태그</p>
</div>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/a71a1deb-21c0-4754-b252-b16717492b5a/image.png)

color는 상속받지 않는 기본값인 initial로 하였기 때문에 검은색으로 됩니다.

font-size는 p태그 상위 요소인 div의 크기를 상속받으니 36px입니다.

여기서 border도 inherit으로 상속받는데, 만약 initial로 바꾸면 어떻게 될까요?`p {
color: initial;
font-size: inherit;
border: initial;
}`![](https://velog.velcdn.com/images/choco_dev/post/4b3a40c8-f0a0-4481-a353-49fd5ce59a14/image.png)

border는 기본값이 없으니 initial을 사용할 수 없습니다.

따라서 border: initial;라고 한 경우엔 테두리가 아예 없어지게 됩니다.

border: unset;이라고 한 경우엔 상속받는 값이면 inherit을, 그렇지 못하는 값이면 initial을 적용합니다.`p {
color: initial;
font-size: inherit;
border: unset;
}`![](https://velog.velcdn.com/images/choco_dev/post/479a5710-b78a-4224-a6c2-3046d13e7c91/image.png)

즉 똑같이 p 태그 요소의 테두리 선이 없어집니다.