## 자바스크립트

#### 동적 타이핑 (Dynamic Typing)

자바스크립트는 동적 타입(dynamic typed) 언어 혹은 느슨한 타입(loosely typed)	언어이다. 이건은 변수의 Type annotation(주석)이 필요없이 값이 할당되는 과정에서 자동으로 자료형이 결정(Type Inference)될 것이라는 뜻이다. 따라서 같은 변수에 여러 자료형의 값을 할당할 수 있다. 이를 동적 타이핑(Dynamic Typing)이라 한다.

```javascript
var foo;

console.log(typeof foo);  // undefined

foo = null;
console.log(typeof foo);  // object

foo = {};
console.log(typeof foo);  // object

foo = 3;
console.log(typeof foo);  // number

foo = 3.14;
console.log(typeof foo);  // number

foo = 'Hi';
console.log(typeof foo);  // string

foo = true;
console.log(typeof foo);  // boolean
```



#### 변수 호이스팅 (Variable Hoisitng)

호이스팅이란 var 선언문이나 function 선언문 등 모든 선언문이 해당 Scope의 선두로 옮겨진 것처럼 동작하는 특성을 말한다. 즉, 자바스크립트는 모든 선언문(var, let, const, function, function*, class)이 선언되기 이전에 참조 가능하다.

변수는 3단계에 걸쳐 생성된다. 

**선언 단계(Declaration phase)**

변수 객체(Variable Object)에 변수를 등록한다. 이 변수 객체는 스코프가 참조하는 대상이 된다.

**초기화 단계(Initialization phase)**

변수 객체에 등록된 변수를 메모리에 할당한다. 이 단계에서 변수는 undefined로 초기화된다.

**할당 단계(Assignment phase)**

undefined로 초기화된 변수에 실제값을 할당한다.

var 키워드로 선언된 변수는 선언 단계의 초기화 단계가 한번에 이루어진다. 즉, 스코프에 변수가 등록되고 변수는 메모리에 공간을 확보한 후 undefined로 초기화된다. 따라서 변수 선언문 이전에 변수에 접근하여도 Variable Object에 변수가 존재하기 때문에 에러가 발생하지 않는다. 다만 undefined를 반환한다. 이러한 현상을 변수 호이스팅(Variable Hoisting)이라한다.

이후 변수 할당문에 도달하면 비로소 값의 할당이 이루어진다.

![img](/var/folders/2p/blfh1vyx401bfr_ffs174x_00000gn/T/abnerworks.Typora/image.tiff)

#### var 키워드로 선언된 변수의 문제점

1. 함수 레벨 스코프 (Function-level scope)

* 전역 변수의 남발
* for loop 초기화식에서 사용한 변수를 for loop 외부 또는 전역에서 참조할 수 있다.

2. var 키워드 생략 허용

* 의도하지 않은 변수의 전역화

3. 중복 선언 허용

* 의도하지 않은 변수값 변경

4. 변수 호이스팅

* 변수를 선언하기 전에 참조가 가능하다.



**변수의 유효 범위(scope)는 좁을수록 좋다.** 전역 변수는 유효 범위가 넓어서 어디에서 어떻게 사용될 지 파악하기 힘들다. 이는 의도치 않은 변수의 변경이 발생할 수 있는 가능성이 증가한다. 또한 여러 함수와 상호 의존하는 등 부수 효과(side effect)가 있을 수 있어서 복잡성이 증가한다.

