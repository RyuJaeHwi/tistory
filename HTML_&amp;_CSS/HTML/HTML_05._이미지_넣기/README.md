HTML 05. 이미지 넣기
=
img 태그
------

> **img 태그란?**  
> : .html 문서에서 이미지를 표시할 때 사용하는 단일 태그

.html 문서에서는 이미지를 넣을 때도 태그를 사용합니다.

img 태그는 단일 태그로 콘텐츠를 적지 않는 대신, 해당 태그의 속성에 삽입하려는 이미지에 대한 정보를 주어야 합니다.  
  
  
img 태그의 기본 형태는 다음과 같습니다.`<img src="삽입할 이미지 URL" alt="이미지 설명" />`

여기에 추가로 width, height 등의 너비와 높이 옵션도 추가하여 이미지의 크기와 높낮이를 조절할 수 있습니다.`<img src="삽입할 이미지 URL" alt="이미지 설명" width="너비값 height="높이값" />`

여기서, 너비와 높이는 각각 픽셀(px) 단위입니다!

  

***이미지 넣기 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>이미지 표시</title>
</head>
<body>
<h2>웹 브라우저에 이미지 표시하기</h2>
<p>width = 너비, height = 높이</p>
<br />
<img src="test.png" alt="인트로" width="450" height="150" />
</body>
</html>`  
img 태그에 지정한 크기대로 이미지가 나타나는 것을 알 수 있습니다.
![](https://velog.velcdn.com/images/choco_dev/post/94e16e7e-ddd1-4237-91e0-4c3097d41247/image.png)
  

+ alt 속성은 왜 쓸까?

alt는 alternative의 약자로, 대체 텍스트 역할을 합니다.
이미지가 로딩되기 전이나 로딩이 실패한 경우, 이미지 대신에 보여줄 텍스트가 alt 속성입니다.  
alt를 사용하면 이미지를 볼 수 없는 시각장애인에게 웹페이지 서비스 소개 시 대비가 가능합니다. (음성인식기가 이미지 대신 alt 설명 활용)

  