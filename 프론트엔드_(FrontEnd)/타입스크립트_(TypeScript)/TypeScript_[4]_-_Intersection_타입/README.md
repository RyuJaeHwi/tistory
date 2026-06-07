TypeScript [4] - Intersection 타입
=
Intersection 타입
---------------

> **인터섹션(Intersection) 타입**이란?  
>  : 여러 타입을 모두 만족하는 하나의 타입

&(ampersand)를 사용해 2개 이상의 타입을 조합하는 경우, 이를 인터섹션 타입이라고 부른다.

이전에 배운 유니온 타입이 **"OR"**이라는 의미라면, 인터섹션 타입은 **"AND"**라고 이해하면 된다.

![](https://velog.velcdn.com/images/choco_dev/post/cca7c2f1-6bc3-4a12-939d-2938eda3afa1/image.png)
  

ex)`interface Person {
name: string;
age: number;
}
interface Developer {
name: string;
skill: number;
}
type Capt = Person & Developer;`  

위 예제 코드는 Person 인터페이스의 타입 정의와 Developer 인터페이스의 타입 정의를 **"&" 연산자**를 통해 합쳤다. 그리고 Capt 이라는 새로운 타입에 할당하였다.

이런 방식으로 만들어진 Capt 타입은 아래와 같이 정의된다.`{
name: string;
age: number;
skill: string;
}`

이렇게 **"&" 연산자**를 사용하여 여러 개의 타입 정의를 하나로 합치는 방식을 인터섹션 타입 정의라고 한다.

  
  