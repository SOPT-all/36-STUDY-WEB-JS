# 13장 - 스코프

## ✅ 핵심 개념 정리

- **스코프**: 변수에 접근할 수 있는 유효 범위
- **전역 스코프**: 코드 어디서든 접근 가능
- **지역 스코프**: 함수 내에서만 접근 가능
- **스코프 체인**: 내부 함수가 외부 변수에 접근할 수 있는 구조
- **함수 레벨 스코프**: `var`은 함수 단위로 스코프를 가짐
- **렉시컬 스코프**: 선언 시점의 상위 스코프에 따라 결정됨 (실행 위치와 무관)

## ✅ 예제 코드

### 스코프 체인 예제

```javascript
const x = "global";

function outer() {
  const x = "outer";
  function inner() {
    console.log(x); // 'outer'
  }
  inner();
}
outer();
```

### 함수 레벨 스코프 (var 문제점)

```javascript
if (true) {
  var foo = "hello";
}
console.log(foo); // 'hello' (블록 밖에서도 접근됨)
```
