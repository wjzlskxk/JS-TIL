### 함수

JS에서 함수는 다른 객체처럼 속성 및 method를 가질 수 있으며, 인자를 가질 수 있는 코드 블럭이다. javascript에서 함수는 매우 중요한 특징이며, 특히 부모 함수의 지역변수에 접근할 수 있다.

#### 함수 선언 방식

**1) 함수 선언문**

```javascript
function sayName(name) {
  return 'Hi' + name
}

console.log(sayName('kiki')) // Hi kiki
```

선언문 방식은 호이스팅 되기 때문에 선언 전에 호출하여도 동작한다.

**2) 함수 표현식**

```javascript
const sayName = function (name) {
  return 'Hi' + name
}

console.log(sayName('kiki')) // Hi kiki
```

변수에 함수가 **익명 함수**형태로 할당됨
함수 선언 전에 호출 시 호이스팅이 되지 않아 오류 발생

**3) 화살표 함수**

```javascript
const add = (a, b) => {
  return a + b
}
```

간결한 문법이 특징이고, this객체를 바인딩 하지 않는다 (lexical scope)
객체 리턴 시는 괄호로 감싸야한다. ex) `() => ({ name: "JS" })`

#### 함수의 매개변수와 반환

```javascript
function multiply(a, b) {
  return a * b
}

let result = multiply(3, 4)
console.log(result) // 12
```

함수의 매개변수는 없거나 여러개 일 수 있다.
return 문으로 값을 반환화며, 생략 시 undefined를 반환한다.

#### 클로저 (Closure)

JS 함수는 자신이 선언된 **스코프(문맥)**을 기억한다.

```javascript
function outer() {
  let count = 0
  return function inner() {
    count++
    console.log(count)
  }
}

const counter = outer()
counter() // 1
counter() // 2
```

`inner()`함수는 `outer()`함수의 지역변수인 count에 계속 접근 가능
이처럼 외부 함수의 변수에 접근하는 내부 함수를 클로저라고 한다.
