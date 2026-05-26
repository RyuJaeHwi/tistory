HTML 10. select ~ textarea
=
select 태그
---------

> **<select> ~ </select> 태그란?**  
> : 여러 옵션(선택지)들을 제공해주는 컨트롤 생성 태그

select 태그를 사용하면 여러 선택지 중 하나를 고를 수 있는 메뉴 형식의 콘텐츠가 만들어집니다. 간단히 말하면 **"드롭다운"**을 만들어줍니다.

이때 <select> ~ </select> 태그 안의 각 선택지들은 option 태그를 사용합니다.

select 태그도 각 요소마다 name을 지정할 수 있습니다.`<select name="dessert" multiple>
<option value="jelly">젤리</option>
<option value="cookie">쿠키</option>
</select>`

이 코드를 보면 select 태그 안에 name 속성을 넣어서 어떤 옵션들이 있는지 안내합니다.

또한 각각의 option마다 value 속성을 지정할 수 있습니다. 여기서 value는 실제로 처리될 값을 뜻합니다.

이제 직접 예시를 통해 알아보도록 하겠습니다.

***select 태그 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>select ~ textarea</title>
</head>
<body>
<h1>먹고 싶은 간식 선택</h1>
<select name="dessert">
<option value="candy">사탕</option>
<option value="chocolate">초콜릿</option>
<option value="jelly">젤리</option>
<option value="cookie">쿠키</option>
</select>
</body>
</html>`  
![](https://velog.velcdn.com/images/choco_dev/post/2eae61b3-ab46-43cc-af0a-436fe3cd478e/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/03311fdc-d82d-48b5-8fc5-b5381372e61e/image.png)

결과를 보면 해당 드롭다운을 클릭해야 아래로 선택지들이 펼쳐지는 것을 확인할 수 있습니다.

그러면 이러한 것도 속성을 통해 조정하려면 어떻게 해야할까요?

![](https://velog.velcdn.com/images/choco_dev/post/92d098ff-df40-41b2-bc34-37b5d81c02d5/image.png)

select 태그에 **"multiple"** 속성을 넣으면 됩니다! 해당 속성은 드롭다운 클릭을 하지 않아도 처음부터 전체 선택지가 펼쳐지도록 해줍니다.

![](https://velog.velcdn.com/images/choco_dev/post/ff699fb8-5ccd-4457-a847-6ed05ff005ed/image.png)

그리고 **"multiple"**속성이 있는 경우엔 Ctrl 키를 누르면서 클릭하면 다중 선택이 가능합니다.

추가로 select 태그 안의 option 태그도 **"selected"**라는 속성이 있습니다. 이 속성은 이미 해당 option 태그의 값이 선택되어 있도록 해주는 속성입니다.`<option value="candy">사탕</option>
<option value="chocolate" selected>초콜릿</option>
<option value="jelly">젤리</option>`

이렇게 특정 option 태그에 추가하면, 해당 option의 선택지는 이미 선택되어 있는 것으로 나타납니다.

![](https://velog.velcdn.com/images/choco_dev/post/b0556fb7-bdfd-4b24-8d95-90aa4df0d6a3/image.png)

결과를 보면 **"selected"** 속성이 있는 "초콜릿" 선택지만 먼저 선택되어 있는 것을 알 수 있습니다!

  

textarea
--------

> **textarea란?**  
> : 여러 줄의 텍스트를 입력할 수 있게 해주는 입력 요소 태그

여기서 textarea랑 input의 입력이 무슨 차이인지 헷갈릴 수 있는데, input 태그는 한 줄밖에 쓸 수 없지만 textarea는 여러 줄의 텍스트를 입력할 수 있습니다.

그리고 textarea에서 초기값을 지정하려면 직접 해당 태그 안에 콘텐츠로 입력합니다.

***textarea 사용 예시***`<!doctype html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>select ~ textarea</title>
</head>
<body>
<h1>textarea</h1>
<textarea name="content" rows="10" cols="30">기본적으로 쓰여 있는 텍스트</textarea>
</body>
</html>`![](https://velog.velcdn.com/images/choco_dev/post/e13ac8bf-e182-4dda-8473-2d1c12b446ac/image.png)

여기서 textarea 또한 select와 똑같이 name 속성을 추가하여 구별할 수 있다는 걸 알 수 있습니다.

![](https://velog.velcdn.com/images/choco_dev/post/e0996d1a-c192-4d1f-92ea-eb98b0ec7bec/image.png)

**rows**와 **cols**들은 각각 입력창의 가로와 세로 크기를 지정할 수 있는 옵션들입니다.

위 예제에서 cols="30"라고 했으니, 평균적인 글자 크기를 기준으로 약 30글자가 들어갈 정도의 너비로 만들어집니다.

그리고 rows="10"이라고 했으니, 한 번에 10줄의 텍스트가 보일 정도의 높이로 만들어집니다.