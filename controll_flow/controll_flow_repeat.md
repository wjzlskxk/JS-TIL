### 반복문 ( for, while )

JS에서 반목문은 특정 조건이 참(true)일때 실행하는 것과, 반복 횟수를 정하여 반복하는것이 있다.

**for**
먼저 for문은 반복 횟수를 정하여 반복하는 방법이다.

기본 형태는 다음과 같다:

```javascript
for (let i = 시작할 위치; i<반복할 횟수; i++/-- (증감식)) {
    // 반복할 코드 작성
}
```

예를 들어, 0부터 4까지 총 5번 반복한 것을 출력하고 싶다면 다음과 같이 작성하면 된다.

```javascript
for (let i = 0; i < 5; i++) {
  console.log(i)
}
```

for문은 배열을 순회 할때도 주로 사용한다.

```javascript
const fruits = ['apple', 'banana', 'pear', 'orange']

for (let i = 0; i < fruits.length; i++) {
  console.log(fruits[i])
  // 출력 : 'apple', 'banana', 'pear', 'orange'
}
```

또한 조건을 잘못 설정하면 무한 루프에 갇힐 수 있기때문에 주의해야한다.

```javascript
// 조건이 false가 되는 상황이 존재하지 않음 -> 무한 루프
for (let i = 0; i >= 0; i++) {}
```

for문은 for ... in과 for ... of로도 존재하는데,

### for ... in

for ... in은 key, value 쌍을 받을 수 있기 때무에 객체를 순회하는 상황에 사용하기 적합하다.

```javascript
const object = {
  1: 'one',
  2: 'two',
  3: 'three',
}

for (let i in object) {
  console.log(i)

  /**
   * 결과
   *
   * 1
   * 2
   * 3
   */
}

for (let i in object) {
  console.log(object[i])

  /**
   * 결과
   *
   * 'one'
   * 'two'
   * 'three'
   */
}
```

### for ... of

for ... of는 배열을 순회하는 상황에 사용하기 적합하다.

```javascript
const arr = ['for', 'of', 'example']

for (let i of arr) {
  console.log(i)

  /**
   * 결과
   *
   * 'for'
   * 'of'
   * 'example'
   */
}
```

**while**
`while` 문은 **조건이 true인 동안 계속해서 반복**되는 반복문이다.  
즉, 조건이 거짓이 되기 전까지는 무한히 반복될 수 있다.

기본 형태는 다음과 같다:

```javascript
while (조건식) {
  // 조건이 true일 동안 실행할 코드
}
```

예를 들어, 0부터 4까지 숫자를 출력하는 while문은 다음과 같다.

```javascript
let i = 0

while (i < 5) {
  console.log(i)
  i++
}
```

하지만, while문 또한 조건식이 항상 true일 경우 무한 루프에 빠질 수 있으므로 반복을 종료 시킬수 있는 **조건 변경 로직 ex)i++**이 꼭 필요하다.

```javascript
let i = 0

while (true) {
  console.log(i)
  // break가 없으면 무한히 반복됨

  if (i > 5) break

  i++
}
```

또한 while문은 반복 횟수가 명확하지 않은 상황에서 유리하다.
예를 들어, 사용자의 입력을 받을때까지 반복하거나, 특정 이벤트가 발생할때 까지 반복할 수 있다.

```javascript
let answer

while (answer !== 'yes') {
  answer = prompt('계속 하시겠습니까? (yes입력시 종료)')
}
```
