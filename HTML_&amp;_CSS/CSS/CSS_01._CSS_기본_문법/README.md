CSS 01. CSS 기본 문법
=
CSS 기본 문법
---------

CSS의 가장 기초적인 코드 구조는 다음과 같습니다.`선택자{
속성명: 속성값;
}`

* 선택자 : 어떤 요소에 스타일을 적용할지에 대한 정보
* { 중괄호 } : 선택한 요소에 적용할 스타일을 정의하는 영역
* 속성명 : 어떤 스타일을 정의하고 싶은지에 대한 정보 (색상, 크기 등)
* 속성값 : 어떻게 정의하고 싶은지에 대한 정보

  

ex)`p{
color: red;
}`![](https://velog.velcdn.com/images/choco_dev/post/93615a60-d69f-48c3-bae3-b9a46762a480/image.png)

이 예시의 코드는 p 태그에 스타일을 적용한다는 뜻입니다.

p{...} 안에 텍스트 색을 뜻하는 color 속성을 red로 정의합니다.

CSS 주석 사용
---------

CSS 문서에서도 .html과 똑같이 주석을 사용할 수 있습니다!

ex)`p{
/* css 문서의 주석 처리 */
/* color: red; */
}`![](https://velog.velcdn.com/images/choco_dev/post/1bcf730c-dcd8-4851-aaa7-5e8484ce5d89/image.png)

CSS 문서는 위처럼 주석을 사용할 수 있습니다. 이러면 컴퓨터는 인식을 하지 못하니 p 태그의 텍스트도 기본 스타일로 다시 지정됩니다.

HTML에 CSS를 추가하기
---------------

.html 문서에 CSS 코드를 적용하려면 어떻게 해야할까요?

다음과 같은 방식들을 사용하면 됩니다.

* **인라인 스타일** : 태그마다 직접 스타일 적용
* **스타일 태그** : 스타일시트를 위한 태그를 추가하여 적용
* **문서 간의 연결** : 스타일시트 문서를 따로 작성하여 .html 문서와 연결

  
하나씩 알아보도록 하겠습니다!
  
  

### 인라인 스타일

각 태그마다 style 속성을 추가하여 직접적으로 스타일을 정의하는 방식을 뜻합니다.

ex)`<p style="color: blue">
인라인 스타일로 텍스트에 색 추가
</p>`![](https://velog.velcdn.com/images/choco_dev/post/44b23ac4-733b-46d0-a971-bdfd201bd0f7/image.png)

인라인 스타일은 따로 선택자가 필요 없습니다. 대신 웹 콘텐츠와 스타일시트를 분리하려면 이는 아예 사용하지 않는 것이 좋은 방법입니다.

### 스타일 태그

.html 문서에 <style> ~ </style> 태그를 추가하여 그 안에 CSS 코드를 작성하는 방법입니다.

ex)`<style>
/* style 태그 안에는 CSS 코드 작성하기 */
p {
color: red;
font-size: 32px;
}
</style>`![](https://velog.velcdn.com/images/choco_dev/post/4858b6b0-5f45-452f-9caf-cd73a12ce6b8/image.png)
  

### 문서 간의 연결

확장자가 .css인 스타일시트 코드파일을 생성하여 이 파일에 CSS 코드를 작성합니다.

이는 .html 문서와 연결이 가능하고, <link> 태그를 사용하여 연결합니다.

+ <link> 태그는 .html 문서의 <head></head> 안에 적는 태그입니다!

  `<link href="./style.css" rel="stylesheet" />`

* href : 연결하려는 외부 소스의 URL을 작성하는 속성
* rel : 현재 문서(.html)와 외부 소스의 연관 관계를 작성하는 속성

ex)

index.html`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<title>CSS 기본 문법</title>
<link href="./style.css" rel="stylesheet" />
</head>
<body>
<p>텍스트에 .css 문서를 통헤 css 스타일 적용</p>
</body>
</html>`

style.css`p {
color: pink;
font-size: 24px;
}`![](https://velog.velcdn.com/images/choco_dev/post/aabdab26-ad1a-446e-9407-01db9c6ee4c6/image.png)