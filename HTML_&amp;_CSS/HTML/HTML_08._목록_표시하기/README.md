HTML 08. 목록 표시하기
=
목록
--

> **목록이란?**  
> : 서로 연관 있는 항목(item)들을 나열한 것을 의미

.html 문서에서 목록은 "순서 없는 목록"과 "순서 없는 목록"으로 구분합니다.

**Unordered List**

* 공부하기
* 운동하기
* 독서하기

**Ordered List**

1. HTML
2. CSS
3. JavaScript

  

각 리스트 종류마다 사용하는 태그는 다음과 같습니다.

> * 순서가 있는 목록 (Ordered List) : **<ol> ~ </ol>**

* 순서가 없는 목록 (Unordered List) : **<ul> ~ </ul>**

  

#### 각 항목을 나타내는 태그는?

리스트 내부의 각 항목들은 **<li> ~ </li>** 태그를 사용합니다.

이 태그는 리스트의 종류에 상관없이 둘 다 공통으로 사용하는 태그입니다.  
<li> ~ </li> 태그를 감싸는 상위 태그가 무엇이냐에 따라 각 항목의 기호가 달라지는 원리입니다.

***목록 만들기 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>목록 만들기</title>
</head>
<body>
<h1>오늘 할 일</h1>
<ul>
<li>html 공부하기</li>
<li><strong>pt 수업 들으러 가기</strong></li>
<li>낮잠자기</li>
<li>독서하기</li>
</ul>
<hr />
<h1>프론트엔드 공부 순서</h1>
<ol>
<li><mark>HTML</mark></li>
<li>CSS</li>
<li>JavaScript</li>
<li>React</li>
</ol>
</body>
</html>`  
![](https://velog.velcdn.com/images/choco_dev/post/13eafe55-41aa-418f-808e-30a03b9423dc/image.png)
  
여기서 리스트 영역이랑 항목 영역을 개발자 모드를 통해 확인하면, ol, ul, li 태그 셋 모두 블록 레벨 요소를 표시하는 태그란 걸 확인할 수 있습니다.
![](https://velog.velcdn.com/images/choco_dev/post/9f09940c-1222-4249-8347-22065ae23e00/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/e896a6a3-32c4-48ca-a1d9-fc960473491b/image.png)