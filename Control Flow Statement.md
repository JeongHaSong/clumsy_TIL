### 제어문 (Control flow statement)

제어문은 조건에 따른 명령 실행(조건문)이나 반복 실행(반복문)이 필요할 때 사용된다. 일반적으로 코드는 위에서 아래로 아래 방향으로 순차적 실행을 하지만 실행 순서를 변경하거나 조건에 따라 실행 여부를 결정하기도 하고 반복할 수도 있다.



#### 1. 블록 구문(Block statement)

블록 구문에서는 구문들의 집합으로 중괄호는 그 범위를 정한다. 블록 구문은 일반적으로 함수, 객체리터럴, 흐름 제어 구문(control flow statement)에 사용된다. (e.g if, for, while)

#### 2. 조건문(Conditional statement)

프로그래밍(coding)이란 변수를 통해 값을 저장하고 참조하며 연산자로 값을 연산, 평가하고 조건문과 반복문에 의한 흐름제어로 데이터의 흐름을 제어하고 함수로 구문의 집합을 만들며 객체, 배열 등으로 자료를 구조화한다.

데이터의 흐름을 제어한다는 것은 일정 조건에 따른 의사결정(decision)을 통해 다음 진행 흐름으로 유도(Control flow)하는 것이다. 이는 가장 원시적인 형태의 인공 지능(Artificial Intelligence)을 부여하는 것이라고 볼 수 있다. 즉, 의사결정(상황판단)의 기준을 제시하고 그 결과에 따른 행위를 지시하는 것이다.



#### Truthy & Falsy values

아래 값들은 Boolean context 에서 false로 평가된다.

* false
* undefined
* null
* 0
* NaN(Not a Number)
* ' '(빈 문자열)

Falsy value 이외의 값들 (object 포함)은 모두 true로 평가된다. 