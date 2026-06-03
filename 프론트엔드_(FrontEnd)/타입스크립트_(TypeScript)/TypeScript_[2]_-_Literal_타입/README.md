TypeScript [2] - Literal 타입
=
Literal 타입 시작
-------------

> Literal 타입이란?  
>  : 문자열과 숫자에 한해서 직접 값 자체를 타입으로 선언하는 것

리터럴 타입은 집합 타입의 보다 구체적인 하위 타입이다.

이 말이 이해가 안될 수 있다.

쉽게 표현하자면, 타입 시스템 안에서 "Hello World"는 string이지만, string은 "Hello World"가 아닌 것이다.

타입은 무조건 number, string, array와 같은 자료형만 넣는 것이 아니다.

타입스크립트에는 문자열과 숫자, 그리고 불리언 총 세 종류의 리터럴 타입이 있는데, 이를 잘 사용하면 문자열이나 숫자에 정확한 값을 지정할 수 있다.

  

### 리터럴 타입 좁히기 (Literal Narrowing)

**var** 또는 **let**으로 변수를 선언할 경우엔 이 변수의 값이 변경될 가능성이 있음을 컴파일러에게 알린다.

반대로, **const**로 변수를 선언하게 되면 TypeScript에게 이 객체는 절대 변경되지 않음을 알린다.

ex)`// const를 사용하여 변수 helloWorld가 절대 변경되지 않음을 보장
// 즉 TypeScript는 문자열이 아닌 "Hello World"로 타입을 선언
const helloWorld = "Hello World";
// 반면, let은 변경될 수 있으므로 컴파일러는 문자열이라고 선언할 것
let hiWorld = "Hi World";`

즉 타입 좁히기란...

* 무한한 수의 케이스 *ex) 문자열* ⇒ 유한한 수의 케이스 *ex) helloWorld는 1개*
* 변수가 가질 수 있는 케이스를 더 적게 한정해 주는 것

  

### 숫자 리터럴 타입 (Numeric Literal Types)

아래와 같은 상수는 number 타입이라고 생각할 수 있다.

그러나 직접 확인해보면 타입 자체가 "3"이라는 것을 알 수 있다.

ex)`const num = 3;`![](https://velog.velcdn.com/images/choco_dev/post/1ef72e63-54ad-4207-baf0-60e6bb5ca4b9/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/d61cd5d3-f823-4e7c-9fe3-1274d8c93792/image.png)
  

타입스크립트의 타입은 자료형뿐만 아니라, 값 자체(숫자와 문자 한정)를 타입으로 지정할 수 있다.

왜냐하면 타입은 아주 정확하게 명시하는 것이 타입스크립트의 기본이기 때문이다.

  
const 상수는 한 번 초기화하면 값을 바꿀 수 없으니, 이는 편리한 판단이라고 볼 수 있다.
  

ex)`const num1: 3 = 3;
const num2 = 3; // 타입 생략`![](https://velog.velcdn.com/images/choco_dev/post/88cebb38-10c6-4801-8f05-62c0405c4471/image.png)
![](https://velog.velcdn.com/images/choco_dev/post/68e78a8c-6558-4edc-b455-f7aa60c1d4c3/image.png)
  
코드 내에서 설정값을 추가할 때도 이러한 숫자형 리터럴 타입을 사용하기도 한다.
  

ex)`declare function setupMap(config: MapConfig): void;
// ---생략---
interface MapConfig {
lng: number;
lat: number;
tileSize: 8 | 16 | 32;
}
setupMap({ lng: -73.935242, lat: 40.73061, tileSize: 16 });`  

### 문자열 리터럴 타입 (String Literal Types)

문자열 리터럴 타입도 숫자와 똑같다.

문자열에 값을 정확히 지정해야 할 때 사용하면 된다.

ex)`// Easing 이라는 새로운 타입은 오직 딱 3가지 문자열만 허용
type Easing = 'ease-in' | 'ease-out' | 'ease-in-out';
// 함수 animate의 세 번째 인자는 위 Easing 세 문자열 중 하나
function animate(dx: number, dy: number, easing: Easing) {
if (easing === 'ease-in') {
// ...
} else if (easing === 'ease-out') {
} else if (easing === 'ease-in-out') {
} else {
// null이나 undefined를 전달하면 필터링 실행
}
}
animate(0, 0, 'ease-in');
animate(0, 0, 'uneasy'); // 오류: 다른 문자열은 허용 X`  

### 불린형 리터럴 타입 (Boolean Literal Types)

숫자와 문자뿐만 아니라 불린 형태의 리터럴 타입도 있다.

보통 어떤 객체가 그 속성과 서로 관련이 있는 경우에 속성값을 제한하기 위해 사용한다.  
*ex) 검증이 성공한 경우 isValid는 true로 제한, 실패한 경우 false로 제한...*

ex)`interface ValidationSuccess {
isValid: true;
reason: null;
}
interface ValidationFailure {
isValid: false;
reason: string;
}
type ValidationResult = ValidationSuccess | ValidationFailure;`  
  