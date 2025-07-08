## 변수 선언

JS의 변수 선언에는 크게 var, let, const 이렇게 3가지 종류가 있다.
하지만 각각 차이가 존재한다.

### var
var로 선언한 변수는 호이스팅이 진행된다.
호이스팅이란 자바스크립트에서 변수 및 함수 선언이 해당 범위, 즉 스코프의 최상단으로 끌어올려지는 것처럼 보이는 현상을 의미한다.
예를 들어 다음과 같은 코드가 있다고 가정하자

```javascript
console.log(say) // undefined

var say = 'hello'
```

분명 say변수는 console.log의 아래 코드라인에 존재해 있지만 say변수를 먼저 사용하므로써 undefined가 할당이 된것이다.
하지만 var로 함수를 선언한다면 함수의 구현된 부분도 같이 호이스팅 되기 때문에 다음과 같이 출력된다.

```javascript
myFunction() // say Hello

function myFunction() {
  console.log('say Hello')
}
```

또한 var변수는 재할당, 재선언이 가능하다.

### let
let으로 선언한 변수도 호이스팅이 된다.  
하지만 var와는 다르게, 호이스팅이 되었더라도 **"초기화되지 않은 상태"**로 존재하며,  
**Temporal Dead Zone(TDZ, 일시적 사각지대)**이라는 구간에 들어가게 된다.

TDZ는 변수가 선언되었지만 초기화되기 전까지 접근할 수 없는 구간을 의미한다.  
즉, 선언 이전에 해당 변수에 접근하면 `ReferenceError`가 발생한다.

예를 들어 다음 코드를 보자:

```javascript
console.log(say) // ReferenceError

let say = 'hello'
```

let으로 선언한 변수는 **구조 분해 할당**이 가능하다.
아래의 코드를 보자:

```javascript
let foo = { bar: 10, baz: 12 }
let { bar } = foo // 10
```

이처럼 foo객체의 속성을 해체하여 그 값을 개별 변수에 담을 수 있게 하는 것이 구조분해 할당이다.

또한 let변수는 재선언은 불가하지만, 재할당은 가능하다

### const
const로 선언한 변수는 var, let과 같이 호이스팅이 되지만, let과 같이 TDZ에 들어가 `RefenrenceError`가 발생한다.

또한 const로 선언한 변수 또한 구조 분해 할당이 가능하며, const는 위의 두 변수와 다르게 재선언 및 재할당 모두 불가하다.
