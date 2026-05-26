CSS 15. 의사 요소
=
의사 요소
-----

> **의사 요소(pseudo-elements) 란?**  
> : 선택자에 추가하는 키워드로, 선택한 요소의 특정 부분에 대한 스타일을 정의할 수 있음

의사 요소의 코드 기본 구조입니다.`선택자::의사 요소{
속성명: 속성값;
}`

실제 저 구조를 적용하면 아래처럼 쓸 수 있습니다.

ex) li 요소의 첫 번째 글자만 크기를 20px로 변경 (기본값 = 16px)`li::first-letter{
font-size: 20px;
}`  

아래 표는 의사 요소 중 가장 많이 사용되는 것 일부를 정리한 것입니다.

| 의사 요소 | 의미 |
| --- | --- |
| after | 요소의 앞에 의사 요소를 생성 및 추가 |
| before | 요소의 뒤에 의사 요소를 생성 및 추가 |
| first-line | 블록 레벨 요소의 첫 번째 선에 스타일 적용&nbsp&nbsp |
| maker | 목록 기호의 스타일 적용 |
| placeholder | 입력 요소의 자리표시자 스타일 적용 |

  

***의사 요소 예시1***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>의사 요소</title>
<style>
p::first-line {
color: red;
}
p::first-letter {
font-size: 24px;
}
</style>
</head>
<body>
<p>
퍼스트 라인 & 레터 테스트
<br />
퍼스트 라인 & 레터 테스트
<br />
퍼스트 라인 & 레터 테스트
<br />
퍼스트 라인 & 레터 테스트
</p>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/d976268c-1087-42b5-a2e2-ea5592190815/image.png)

의사 요소를 통해 첫 번째 p 태그의 전체 한 줄 색을 red로, 그 첫 번째 줄의 첫 번째 텍스트 크기만 24px로 바꾸었습니다.

  

***의사 요소 예시2***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>의사 요소</title>
<style>
li::marker {
color: darkcyan;
font-size: 50px;
}
input::placeholder {
font-size: 28px;
color: plum;
}
</style>
</head>
<body>
<ul>
<li>사탕</li>
<li>초콜릿</li>
<li>젤리</li>
<li>쿠키</li>
</ul>
<input type="text" placeholder="아무거나 작성하기" />
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/ee83ee94-12de-4fbb-a804-3b65f604c7cd/image.png)

li::marker { ... } 의사 요소를 통해 목록 표시의 색상과 크기를 바꾸었습니다.

또한 input 내부 placehoder 텍스트의 크기와 색상도 변경하였습니다.

***의사 요소 예시3***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>의사 요소</title>
<style>
h2::before {
content: "h2 앞에 before 옵션으로 추가한 텍스트";
font-size: 12px;
font-weight: 900;
color: brown;
}
h2::after {
content: "h2 뒤에 after 옵션으로 추가한 텍스트";
font-size: 12px;
font-weight: 400;
color: darkgoldenrod;
}
</style>
</head>
<body>
<h2>원래 작성된 내용</h2>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/520a2e24-f4de-4e13-bc58-56edefa8fbfb/image.png)

before과 after 의사 요소를 통해 기존 h2 요소 앞 뒤에 각각 텍스트를 추가하였습니다.