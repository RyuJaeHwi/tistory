HTML 07. 링크 추가하기
=
링크
--

### 링크의 개념

> **링크(Link)란?**  
> : 현재 문서에서 다른 문서로 이동할 수 있는 수단

ex) 외부 링크 클릭 시 해당 페이지로 이동...

  

### 링크 = anchor (a 태그)

> **<a> ~ </a> 태그란?**  
> : href 속성으로 특정 URL을 지정하여 하이퍼링크를 만들 수 있는 태그

해당 a 태그는 인라인 요소입니다. 내부 콘텐츠(텍스트나 이미지...)를 클릭하면 지정된 URL로 이동하게 됩니다.

<a> 태그의 기본 구조는 다음과 같습니다.`<a href="지정할 URL"> 콘텐츠 (텍스트 또는 이미지...) </a>`

* href="URL" : 하이퍼링크가 될 URL
* 콘텐츠 : 사용자가 클릭하는 콘텐츠

  

#### 어떤 탭에서 열까?

링크 클릭 시, 기존 탭에서 이동하거나 아예 새로운 탭을 통해 이동하는 방법 2가지가 있습니다.

이는 **target 속성**을 통해 지정 가능합니다. 기본값은 현재 탭에서 이동입니다.`<a href="https://www.naver.com/" target="_self">
네이버 이동 (현재 탭에서 열기, 기본값)
</a>
<a href="https://www.google.com/" target="_blank">
구글로 이동 (새 탭에서 열기)
</a>`  

이제 실제로 만들어진 링크들이 어떻게 나타나는지 직접 테스트를 하려고 합니다.

***링크 만들기 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>링크 제작</title>
</head>
<body>
<a href="https://www.naver.com/" target="_self">네이버 이동 (현재 탭, 기본값)</a>
<br />
<a href="https://www.google.com/" target="_blank">구글로 이동 (새 탭)</a>
<br />
<a href="https://www.daum.net/" target="_blank">
<img src="../daum-logo.png" alt="다음 로고" width="150" height="70" />
</a>
</body>
</html>`  
target 속성을 "\_self"로 하면 기존 탭에서 열고, "\_blank"로 하면 새로운 탭에서 엽니다.
![](https://velog.velcdn.com/images/choco_dev/post/c3279f19-3167-41c6-a850-d01b63b4a1e0/image.png)
  

#### 전화 걸기, 이메일 보내기

a 태그를 통해 전화번호와 이메일 주소를 적어서 지정할 수도 있습니다.`<a href="tel:010-1234-5678">010-1234-5678</a>
<a href="mailto:beansdrawer@naver.com">beansdrawer@naver.com</a>`

이렇게 하면 전화 걸기, 이메일 보내기 등의 기능을 구현할 수 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/8fa10932-c094-4a9f-9fd9-03e91b42ad03/image.png)