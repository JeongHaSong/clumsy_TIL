#### 삼항 연산자(ternary operator)

조건 ? 조건이 true일 때 변환할 값 : 조건이 false일때 변환할 값

```javascript
var condition = true;
var result = condition ? 'true' : 'false';
console.log(result); // 'true'

```



// id의 길이가 INPUT_ID_MIN_LEN보다 작으면 에러 메시지를 출력한다.

```javascript
var id = 'lee';
var INPUT_ID_MIN_LEN = 5;
var errMsg = id.length < INPUT_ID_MIN_LEN ? '아이디는 5자리 이상으로 입력하세요' : '성공';
console.log(errMsg); // '아이디는 5자리 이상으로 입력하세요'
```



#### 타입 연산자 (Type Operators)

| Operator   | Description                                                  |
| ---------- | ------------------------------------------------------------ |
| typeof     | 피연산자의 데이터 타입(자료형)을 문자열로 반환한다. null과 배열의 경우 object, 함수의 경우 function를 반환하는 것에 유의하여야 한다. |
| instanceof | 객체가 동일 객체형의 인스턴스이면 true를 반환한다.           |



#### !!

!!의 역할은 피연산자를 불린값으로 변환하는 것이다.

객체(배열 포함)의 경우 빈 객체라도 존재하기만하면 true로 변환된다.

```javascript
var obj;
console.log(!!obj); // false

obj = {};
console.log(!!obj); // true
```

