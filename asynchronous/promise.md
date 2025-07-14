### Promise

#### 1. Promise란?

Promise는 **비동기 작업의 완료 또는 실패**를 나타내는 객체이다.
과거 콜백 함수 방식의 **복잡한 비동기 흐름 [콜백지옥](./callback.md)을 해결하기 위해 등장함.**

**지금은 없지만, 나중에 생길것이다.**라는 "약속"을 표현하는 개념이다.

#### 2. Promise 기본 구조

```javascript
let promise = new Promise((resolve, reject) => {
  if (성공) {
    resolve(결괏값) // 성공시 실행
  } else {
    reject(에러) // 실패시 실행
  }
})
```

- resolve: 작업 성공시 호출
- reject: 작업 실패시 호출
- promise객체는 .then() .catch()로 결과를 처리할 수 있다.

사용예시는 다음과 같다:

```javascript
const promise = new Promise((resolve, reject) => {
  setTimeout(() => {
    resolve('작업 성공!')
  }, 1000)
})

promise
  .then((res) => {
    console.log(res)
  })
  .catch((err) => {
    console.error(err)
  })
```

#### 3. Promise 체이닝

.then() 함수를 연속적으로 이어서 쓸 수 있음(값을 넘겨받으며 순차 실행)

```javascript
doSomething()
  .then((result1) => doNext(result1))
  .then((result2) => doMore(result2))
  .then((result3) => console.log(result3))
  .catch((err) => console.error('에러 발생' + err))
```

#### 4. Promise 상태

| 상태      | 설명                                     |
| --------- | ---------------------------------------- |
| pending   | 대기 중 (비동기 작업이 아직 끝나지 않음) |
| fulfilled | 완료 (resolve 호출됨 )                   |
| rejected  | 실패 (reject 호출됨)                     |
