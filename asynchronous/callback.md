### 콜백함수와 콜백 지옥

**콜백함수**란 다른 함수에 인자로 전달되어 나중에 호출 되는 함수이다.
콜백 함수의 예시는 다음과 같다:

```javascript
function greet(name, callback) {
  console.log('Hi' + name)
  callback()
}

greet('JS', function () {
  console.log('Welocom!')
})
```

**콜백 지옥**이란 콜백을 중첩해서 사용하는 코드가 너무 복잡하고 가독성이 떨어지는 상태를 의미한다.

콜백 지옥이 일어나는 상황의 예시는 다음과 같다:

```javascript
login(user, function() {
    getProfile(user, function() {
        getPosts(user, function() {
            getComments(user, function() {
                ...
            })
        })
    })
})
```
