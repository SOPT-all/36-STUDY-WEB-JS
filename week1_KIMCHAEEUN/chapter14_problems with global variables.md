# 14장 - 전역 변수의 문제점

## ✅ 핵심 개념 정리

- **변수의 생명주기**: 선언 -> 사용 -> 소멸 (지역변수는 함수 종료 시 소멸)
- **전역 변수의 문제점**
  - 암묵적 결합
  - 의존성 증가
  - 네임스페이스 충돌
  - 클로저에 의해 의도치 않게 유지 가능
- **전역 변수 역제 방법**
  - IIFE
  - 네임스페이스 객체
  - ES6 모듈

## ✅ 예제 코드

### 암묵적 전역 변수 (선언 없이 사용)

```javascript
function foo() {
  bar = 100; // var, let, const 없이 선언 → 전역 변수가 됨!
}
foo();
console.log(bar); // 100
```

### 네임스페이스 객체 패턴

```javascript
const MY_APP = {};
MY_APP.value = 42;
console.log(MY_APP.value); // 42
```

### IIFE 사용 예시

```javascript
(function () {
  var secret = "hidden";
  console.log(secret); // 'hidden'
})();
console.log(secret); // ReferenceError
```
