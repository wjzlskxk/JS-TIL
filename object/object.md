### 객체

JS에서 객체(Object)는 한개의 변수에 여러 속성을 저장 할 수 있는 데이터 타입을 의미한다.

객체 형태로 변수를 선언하는 방법은 다음과 같다:

```javascript
let obj1 = new Object()
let obj2 = {} // 객체 리터럴 방식 (주로 사용됨)
```

객체 안에 들어가 있는 값들을 속성이라고 하고 이 속성은 { key : value } 쌍으로 존재한다.

**객체 예시:**

```javascript
const user = {
  name: 'Joshua',
  age: 19,
  isStudent: true,
}
```

#### 🔹 객체 속성 접근 방법

**1. 점 표기법**

```javascript
console.log(user.name)
```

**2. 대괄호 표기법**

```javascript
console.log(user['age'])
```

대괄호 표기법은 key가 변수이거나, 공백, 특수문자 포함시 사용

#### 🔹 속성 추가 및 수정, 삭제

**1. 속성 추가**

```javascript
user.job = 'developer'
```

**2. 속성 수정**

```javascript
user.age = 20
```

**3. 속성 삭제**

```javascript
delete user.isStudent
```

#### 🔹 객체에 함수 넣기

```javascript
let user = {
  name: 'Alice',
  greet: function () {
    console.log('Hello' + this.name)
  }, // 화살표함수 (Arrow function도 가능)
}

user.greet()
```

#### 🔹 자주 사용하는 내장 함수들

| 함수                         | 설명                        | 예시                               |
| ---------------------------- | --------------------------- | ---------------------------------- |
| `Object.keys(obj)`           | key 목록 배열 반환          | `["name", "age"] `                 |
| `Object.values(obj)`         | value 목록 배열 반환        | `["Alice", 25]`                    |
| `Object.entries(obj)`        | [key, value] 쌍의 배열 반환 | `[["name", "Alice"], ["age", 25]]` |
| `Object.hasOwnProperty("x")` | 특정 키 존재 여부           | `true` / `false`                   |
