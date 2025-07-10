### 배열

JS에서 배열(Array)는 한개의 변수에 여러개의 값을 **순차적으로 저장**할 때 사용한다.

배열 형태로 변수를 선언하는 방법은 다음과 같다:

```javascript
let arr1 = new Array()
let arr2 = []
```

배열 안에 들어가 있는 값들을 요소(element, item, etc...)라고 한다.

```javascript
let arr1 = [1, '2', true]
let arr2 = [undefined, null, false, NaN, 10000]
```

배열은 숫자인덱스 (0부터 시작)를 기반으로 각 요소에 접근하며, **다양한 값과 타입**을 함께 담을 수 있다.

**🔹 배열의 인덱싱 & 길이**

```javascript
let fruits = ['apple', 'banana', 'cherry']

console.log(fruits[0]) // 'apple'
console.log(fruits[1]) // 'banana'
console.log(fruits.length) // 3
```

배열의 인덱스는 **0부터 시작**한다.
`.length`속성은 배열의 요소 개수를 나타낸다.

**🔹 배열 수정**

```javascript
fruits[1] = 'grape'
console.log(fruits) // ['apple', 'grape', 'cherry']
```

**🔹 배열 메서드**

| 메서드       | 설명                        | 예시                    | 결과 예시 / 효과 |
| ------------ | --------------------------- | ----------------------- | ---------------- |
| `push()`     | 배열 끝에 요소 추가         | `arr.push(4)`           | `[1, 2, 3, 4]`   |
| `pop()`      | 배열 끝 요소 제거           | `arr.pop()`             | `[1, 2]`         |
| `unshift()`  | 배열 앞에 요소 추가         | `arr.unshift(0)`        | `[0, 1, 2, 3]`   |
| `shift()`    | 배열 앞 요소 제거           | `arr.shift()`           | `[2, 3]`         |
| `includes()` | 특정 값 포함 여부 확인      | `arr.includes(2)`       | `true`           |
| `indexOf()`  | 특정 값의 인덱스 반환       | `arr.indexOf(3)`        | `2`              |
| `join()`     | 배열 요소들을 문자열로 결합 | `arr.join(", ")`        | `"1, 2, 3"`      |
| `slice()`    | 일부 요소 추출 (원본 유지)  | `arr.slice(1, 3)`       | `[2, 3]`         |
| `splice()`   | 요소 추가/삭제 (원본 변경)  | `arr.splice(1, 1, "X")` | `[1, "X", 3]`    |
| `reverse()`  | 배열 순서를 뒤집음          | `arr.reverse()`         | `[3, 2, 1]`      |
