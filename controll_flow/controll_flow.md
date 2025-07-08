### 조건문 ( if )
JS에서 조건문은 특정 조건이 참 (true)인지 확인하고, 그에 따라 코드를 실행 할 수 있도록 해준다.

기본 형태는 다음과 같다:
```javascript
if (조건) {
    // 조건이 true일때 실행
} else {
    // 조건이 false일떼 실행
}
```
if문에서 조건은 Boolean 값으로 평가된다.
조건식에는 논리 연산자, 비교 연산자, 또는 truly/falsy 값을 사용할 수 있다.

```javascript
if ("hello") {
    console.log("실행됨") // 문자열은 truly이므로 실행된다.
}

if (0) {
    console.log("실행안됨") // 0은 falsy
}
```

자바스크립트의 falsy값은 다음과 같다
```bash
- false
- 0
- "" (빈 문자열)
- null
- undefiend
- NaN
```
이 외의 값은 다 truly로 취급된다.
