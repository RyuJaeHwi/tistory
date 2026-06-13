TypeScript [8] - 함수 (1)
=
타입스크립트의 함수 소개
-------------

### 함수의 기본 정의

함수는 자바스크립트로 된 모든 애플리케이션를 구성하는 기본 요소이다.

타입스크립트에는 클래스, 네임스페이스, 모듈이 있지만, 함수는 여전히 이 일을 어떻게 할 것인지를 설명하는 데 있어 핵심 역할을 수행한다.

타입스크립트에서의 함수는 기존의 자바스크립트 함수가 작업을 수월하게 할 수 있도록 몇 가지 새로운 기능이 추가된 상태이다.

먼저 간단한 자바스크립트 함수를 확인해보자.

ex)`function sum(a, b) {
return a + b;
}`  

위 자바스크립트의 함수에 타입을 부여해보면 다음과 같이 된다.

ex)`function sum(a: number, b: number): number {
return a + b;
}`  

즉 기존 자바스크립트 함수의 선언 방식에서 **매개변수와 함수의 반환 값에 타입을 추가**하게 되면, 그것이 타입스크립트의 함수 표현이 된다.

TIP: 함수의 반환 값에 타입을 정하지 않을 때는 void라도 사용하자!

  

### 함수의 여러가지 표현 방법

함수를 표현하는 방법에는 크게 3가지가 있다.

#### 표현1 - 함수 선언식`// 함수 선언식
function myFunc1(x: number, y: number): number {
return x + y;
}`

가장 기본적인 함수를 정의하는 방법이며, **function** 키워드를 사용하여 완전히 독립적으로 함수를 선언한다.

**호이스팅(Hoisting)**이 발생하기 때문에 함수 선언 전에도 호출이 가능하다.

#### 표현2 - 함수 표현식`// 함수 표현식
let myFunc2 = function (x: number, y: number): number {
return x + y;
};`

함수를 **특정 변수에 값으로 선언**하여 정의하는 방법이다.

호이스팅(Hoisting)의 영향을 받지 않기 때문에, 반드시 선언한 이후에 호출해야 한다.

#### 표현3 - 화살표 함수 (Arrow Function)`// 화살표 함수
let myFunc3 = (x: number, y: number): number => {
return x + y;
};
// 중괄호 요약 시 - 표현식이 한 줄이면 {} 와 return 생략 가능
let myFunc3 = (x: number, y: number): number => x + y;`

함수 표현식을 더 간단히 표현하기 위해 사용한다.

  

### Call Signature (함수 타입)

> **Call Signature(함수 타입)** 이란?  
>  : 함수를 표현하는 타입 (= 문자열의 string, 정수 배열의 number[] 등...)

함수 타입을 미리 선언하고 뒤에 함수의 식을 붙여 넣으면, 함수 아규먼트에서 타입을 또 선언하지 않아도 된다는 특징이 있다.

*아규먼트(argument) = 함수를 호출할 때 전달하는 값*

ex)`// 변수에 미리 함수 타입 지정
let myFunc4: (arg1: number, arg2: number) => number;
myFunc4 = function (x, y) {
return x + y;
}; // 미리 변수에 함수 타입을 지정함 -> 대입하는 함수의 식에 타입을 쓰지 않아도 됨
// 위의 과정을 한줄로 표현
let myFunc5: (arg1: number, arg2: number) => number = (x, y) => {
return x + y;
};`

함수 타입 부분을 화살표 함수와 헷갈리지 않도록 주의하자.

type 별칭 및 인터페이스 역시 개별적으로 함수타입을 선언하여 사용될 수 있다.

ex)`// type 리터럴로 함수 타입 지정
type Add1 = (x: number, y: number) => number;
let myFunc6: Add1 = (x, y) => {
return x + y;
};``// 인터페이스로 함수 타입을 지정
interface Add2 {
(x: number, y: number): number;
}
let myFunc7: Add2 = (x, y) => {
return x + y;
};`  

타입스크립트의 매개변수 표현
---------------

타입스크립트에서는 함수의 인자를 모두 필수 값으로 간주한다.

함수의 매개변수를 설정하면 **undefined**나 **null**이라도 인자로 넘겨주어야 하며, 컴파일러에서는 정의된 매개변수 값이 넘어왔는지 확인한다.

즉 정의된 매개변수 값만 받을 수 있고, 추가로 인자를 받을 수는 없다는 의미가 된다.

ex)`function sum(a: number, b: number): number {
return a + b;
}
sum(10, 20); // 30
sum(10, 20, 30); // Error, Expected 2 arguments, but got 3. (인자 개수 초과)
sum(10); // Error, Expected 2 arguments, but got 1. (인자 개수 부족)`  

### 선택적 매개변수 : (?) 사용

만약 자바스크립트처럼 좀 더 유연하게 표현하고 싶다면, **(?) 키워드**를 사용하여 정의하면 된다.

인자에 **옵션 속성**을 부여하여 넣어도 되고, 안넣어도 되도록 선택 사항으로 만드는 것이다.

아래 예제 코드는 인자인 "b"에 **(?) 키워드**를 사용하여 선택적 매개변수로 지정한 모습이다.

그래서 b가 받을 인수가 없어도 에러가 발생하지 않는다.

ex)`function sum(a: number, b?: number): number {
return a + b;
}
sum(10, 20); // 30
sum(10, 20, 30); // Error, Expected 2 arguments, but got 3. (인자 개수 초과)
sum(10);`  

위 예제는 유니온 타입 **"| undefined"**를 사용한 것과 같은 뜻이다.

(둘 중 하나 선택)

ex)`function sum(a: number, b: number | undefined): number {
return a + b;
}
sum(10, 20); // 30
sum(10);`  

**Null 병합 연산자( ?? )**와 함께 응용하여 사용해보자.

선택적 매개변수인 b와 c에 값이 있다면 그대로 사용하여 리턴하고, 없다면 0을 각각의 인자에 부여하여 계산한다.

ex)`function add(a: number, b?: number, c?: number): number {
return a + (b ?? 0) + (c ?? 0);
}
add(1, 2, 3); // 6
add(1, 2); // 3
add(1); // 1`  

이러한 선택적 매개변수를 사용할 때도 주의할 점이 있다.

선택적 매개변수가 이외의 함수 인자 앞으로 위치하면 안된다.

(= 선택적 매개변수는 무조건 뒤에 위치)

ex)`function sum(b?: number, a: number): number {
return a + (b ?? 0);
}`![](https://velog.velcdn.com/images/choco_dev/post/d7b89a6f-fe91-43cc-af57-6716bdad02d7/image.png)
  

만약 해당 선택적 매개변수를 앞에 작성해야 한다면, 같은 기능으로 작동하는 **유니온(Union) 타입**으로 대신 작성하면 된다.

ex)`function sum(b: number | undefined, a: number): number {
return a + (b ?? 0);
}
sum(20, 11); // 31
sum(undefined, 11); // 11`  

### 매개변수 초기화

매개변수의 초기화는 ES6+ 문법과 동일하다.

기본값을 할당한 매개변수의 함수 타입을 보면 선택적 매개변수가 적용된 걸 확인할 수 있다.

(매개변수에 기본값 존재 => 값을 할당하지 않아도 됨)

그리고 매개변수에 기본값이 있다면 인자의 타입을 선언하지 않아도 된다는 특징이 있다. (= **타입 추론**)

ex)`// 매개변수에 기본값이 존재 -> 인자의 타입을 선언하지 않아도 됨 (= 타입 추론)
// b 인자의 기본값은 100
function sum(a: number, b = 100): number {
return a + b;
}
sum(10, undefined); // 110
sum(10); // 110
sum(10, 10) // 20`

위 코드의 b 인자에는 기본값이 있는데, 이는 **b?: number** 라고 선언한 것과 같은 의미가 된다.

  

### 나머지(rest) 매개변수

ES6에서 사용되는 문법 중 하나인 **스프레드 매개변수**도 타입을 잘 지정해준다면, 타입스크립트에서 사용 가능하다.

REST 문법이란?
매개변수 이름 앞에 점 3개(...)를 붙여서 정의한 매개변수,  
이렇게 전달된 인수들은 배열로 전달됨

ex)`myArray(1, 2, 3, 4, 5);
function myArray(...rest) {
console.log(rest) // 1, 2, 3, 4, 5
}`  

이 REST 문법을 적용해보면 다음과 같다.`function sum(a:number, ...nums: number[]):number {
const totalOfNums = 0;
for(let key in nums) {
totalOfNums += nums[key];
}
return a + totalOfNums;
}`

만약 sum(10, 1, 2, 3);로 호출했다고 가정하면, **a**에는 가장 첫 번째 값인 10이 들어간다.

그리고 나머지 값들은 숫자 배열 타입을 가진 인자인 **...nums** 안에 하나의 배열로 묶여서 저장된다.

즉 **nums = [1, 2, 3]** 의 형태가 되는 것이다.

그 아래 for문에서는 nums의 내부 요소들이 하나씩 더해지니 1 + 2 + 3 = 6 이고,

마지막에 a + totalOfNums이니 10 + 6 = 16 이 된다.

#### 나머지 매개변수 사용 시 주의할 점

타입스크립트에서는 strict 모드를 true로 설정하여 사용한다.

즉 자바스크립트의 arguments 예약어 기능을 사용하지 못하니 이를 주의하여 나머지 매개변수를 사용하자.

arguments 예약어란?  
자바스크립트에서 매개변수를 따로 선언을 하지 않아도,  
 함수에 넘긴 값들을 자동으로 담아주는 특별한 객체
  
  

ex)`function aa() {
console.log([...arguments]); // 전달된 인수들을 배열로 출력
}
aa(1, 2, 3, 4, 5); // Error`  
위 오류를 수정하면 아래와 같다.
  
  `// 매개변수를 명시적으로 선언 (arguments 예약어 사용 불가)
function aa2(...args: number[]): number[] {
return args;
}
aa2(1, 2, 3, 4, 5); // [1, 2, 3, 4, 5]`  
  