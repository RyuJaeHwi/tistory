HTML 02. HTML 문서 기본 구조
=
HTML 문서의 구조
===========

보통 .html 문서는 다음과 같은 구조를 기본으로 가집니다.`<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>문서 제목</title>
</head>
<body>
<!-- 웹 페이지의 내용 -->
</body>
</html>`
출처 : https://codingeverybody.kr/category/html/
  
  
  

<!DOCTYPE html>
---------------

> **<!DOCTYPE html>이란?**  
> : 문서의 첫 부분에서 문서 유형을 지정해주는 단일 태그

웹은 과거와 다르게 매우 빨리 발전하고 있으니, 현대 웹 표준에 맞출 수 있도록 이러한 선언을 하는 것입니다.

즉 html은 버전 변경이 잦았는데, 현재 표준 html 버전을 위해 사용하는 것입니다.

이를 표준 모드(Standards Mode) 라고 하며, 표준 모드는 최신 웹 표준을 강제로 쓰게 하고 현대 브라우저 전반에서 일관되고 예측 가능한 렌더링이 되도록 보장해줍니다.

반대되는 개념...  
  
쿼크 모드(Quirks Mode)  
: 구형 브라우저에서 발견된 비표준 동작을 모방하는 레거시 렌더링 모드  
  
쿼크 모드에서는 브라우저가 CSS 박스 모델과 HTML 레이아웃을 다르게 해석할 수 있기 때문에,
일관되지 않은 페이지를 표시하는 위험이 존재

  
  

<html> ~ </html>
----------------

> **<html> ~ </html> 이란?**  
> : 실제 .html 문서가 시작되고 끝나는 것을 나타내는 태그

전 글의 태그 원리와 같습니다. 에서 .html 문서가 시작되고, > 태그에서 문서가 끝납니다.

이 태그 내부에 다른 태그들이 포함되어 웹 브라우저에 표시될 콘텐츠를 만듭니다.

즉, html 태그는 .html 문서의 최상위 요소인 루트(root) 요소입니다.

  
  

<head> ~ </head>
----------------

> **<head> ~ </head> 이란?**  
> : HTML 문서의 문자 인코딩, 타이틀, 설명, 스타일시트, 스크립트 등  
> 문서 정보(메타데이터)에 관련된 다양한 요소를 모아둔 태그

<head> ~ </head&gt 태그 안의 요소들은 웹 브라우저 화면에서는 보이지 않지만, 웹 브라우저가 알아야 할 정보들을 정의합니다.

*ex) 브라우저, 검색 엔진 및 다른 웹 기술 등 기계적 처리를 위한 정보 등*

### <meta charset="utf-8>

: HTML 문서의 문자 인코딩, 타이틀, 설명, 스타일시트, 스크립트 등  
**문서 정보(메타데이터)**에 관련된 다양한 요소를 모아둔 단일 태그

영문과 한글 모두 사용하려면 utf-8 방식을 정의해야 합니다.

### <title> ~ </title>

: 문서의 **제목**을 나타내는 <head>의 자식 태그

  
  

<body> ~ </body>
----------------

> <body> ~ </body> 란?  
> : 실제 브라우저 화면에 표시될 콘텐츠를 입력하는 태그

<body> ~ </body&gt는 <html>태그의 두 번째 요소입니다.  
(첫 번째는 &lthead&gt 태그)

  
body 태그 안에는 아래와 같은 유형의 태그들을 넣을 수 있습니다.

* 텍스트 표시 태그
* 이미지 표시 태그
* 각종사용자 인터페이스(버튼, 입력란, 드롭다운 등)를 나타내는 태그

즉, 태그 안에 태그를 넣는 방식으로 콘텐츠 구현!

  
  

실습
--

VSCode에서 index.html 코드파일을 만듭니다.

빈 .html 코드파일 안에 ! 입력 후 엔터키를 누르면 자동으로 .html 문서의 기본 구조가 완성됩니다.

![](https://velog.velcdn.com/images/choco_dev/post/74e8c7c5-7a62-41da-b76f-88ebeae1ccc0/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/ae76570a-3542-48dd-b6a7-fe18287445ef/image.png)

이렇게 완성된 기본 구조에서 웹 브라우저에 표시할 콘텐츠를 만들어보겠습니다.

간단히 웹 페이지 제목과 내부 텍스트만 추가해보려고 합니다.

아래처럼 코드를 적어보고 브라우저로 열게요!`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>문서의 제목을 쓰는 곳</title>
</head>
<body>
브라우저 화면에 표시할 내용을 작성하는 곳
</body>
</html>`  
이 코드의 결과는 아래와 같습니다.

개발자 모드를 켜보면 .html 문서의 전체 구조도 확인할 수 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/6ab7fe05-ece2-4f9d-ac20-79c93e0044e4/image.png)