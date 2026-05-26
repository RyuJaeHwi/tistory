HTML 시작
=
HTML 알아보기
---------

html이란?

**HTML = HyperText Markup Language**

* HyperText : 하이퍼링크를 통해 어떤 문서에서 다른 문서로 접근 가능한 텍스트
* Markup : 콘텐츠를 표시하는 것
* Language : 언어

즉, HTML은 **"하이퍼 텍스트와 콘텐츠를 표시해주는 언어"**를 뜻합니다.   
  
더 쉽게 표현해보면,  
웹브라우저(크롬, 엣지 등)를 통해 우리가 볼 수 있는 **웹페이지의 콘텐츠들을 정의할 때 쓰이는 언어**입니다.   
  
개발자는 이 HTML을 통해 웹페이지에 어떤 내용을 어떻게 나타나도록 할지를 정의하는 코드를 구현합니다.

![](https://blog.kakaocdn.net/dn/88DdU/dJMcafM6nZq/VVHV9q5KGSPfAyPUhdQ8Yk/img.png)

html 적용 과정

위와 같은 순서로 HTML 코드가 웹페이지에서 표시됩니다.     
이렇게 HTML 코드가 웹브라우저를 통해 해석되고 표현되는 과정을 **"렌더링(Rendering)"**이라고 합니다.   
  
**HTML 문서의 확장자 : `.html` 또는 `.htm`**

---

### HTML 실습

직접 테스트를 해보도록 하겠습니다.   
  
VSCode에서 `index.html` 문서를 만들고 아래와 같이 작성합니다.

```
<p>HTML 문서 작성해보기</p>
```

그리고 해당 index.html을 우클릭하면 나타나는 창에서 "Open with Live Server"를 누르면 웹브라우저로 해당 HTML 문서의 결과가 표시됩니다.

![](https://blog.kakaocdn.net/dn/MFNBP/dJMcaakGJJN/CUlvvB7j4qX8wsNb5e72f1/img.png)

.html 문서 테스트

결과는 아래와 같습니다.

![](https://blog.kakaocdn.net/dn/bW6Pan/dJMcaaye3rZ/y84yhJ89dcsXiZjvufajbK/img.png)

.html 문서 테스트 결과

위처럼 웹 브라우저에 결과가 나타나는 것을 알 수 있습니다.

다음 글부터는 HTML의 기초 문법인 태그와 주석, 속성값에 대해 알아보도록 하겠습니다.