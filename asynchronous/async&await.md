### Async / Await

#### 1. async / await 이란?

`async / await`는 **Promise** 기반의 비동기 코드를 마치 동기 코드 처럼 깔끔하고 가독성있게 작성 할 수 있게 도와주는 문법이다.

`await`는 오직 `async`함수 안에서만 사용가능하다.

기본 구조는 다음과 같다:

```javascript
async function sample() {
  try {
    const result = await 비동기함수()
    console.log(result)
  } catch (err) {
    console.error(err)
  }
}
```

#### 2. Promise와의 비교

**Promise**

```javascript
function getData() {
  return new Promise((resolve, reject) => {
    setTimeout(() => resolve('데이터 도착!'), 1000)
  })
}

getData()
  .then((data) => console.log(data))
  .catch((err) => console.error(err))
```

**async/await**

```javascript
async function showData() {
  try {
    const data = await getData()
    console.log(data)
  } catch (err) {
    console.error(err)
  }
}

showData()
```

> 둘은 같은 동작을 하지만, async/await는 코드 흐름이 직관적이다.

#### 3. 주의할 점

- await은 Promise가 아닌 값에도 사용할 수 있다. (자동으로 Promise.resolve() 처리)
- await은 반드시 async 함수 내부에서만 사용가능
- 여러 await 작업을 병렬로 처리하고 싶다면 Promise.all()과 함께 쓰는것이 좋다.

```javascript
async function run() {
  const [a, b] = await Promise.all([fetchA(), fetchB()])
}
```

async / await는 복잡한 `then().then().catch()`체인을 피할 수 있게 해주며, 동기 코드 처럼 깔끔한 흐름으로 비동기 로직을 완성할 수 있게 된다.
