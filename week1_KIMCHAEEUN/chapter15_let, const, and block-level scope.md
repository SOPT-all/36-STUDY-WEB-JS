# 15장 - let, const와 블록 레벨 스코프

## ✅ 핵심 개념 정리

- **var 키워드의 문제점**
  - 함수 레벨 스코프만 있음
  - 호이스팅 발생
  - 재선언 허용 -> 버그 유발
- **let**
  - 블록 레벨 스코프
  - 재할당 O, 재선언 X
  - TDZ(일시적 사각지대) 존재
- **const**
  - 블록 레벨 스코프
  - 재할당 X, 재선언 X
  - 객체는 내부 프로퍼티 변경 가능

## ✅ var vs. let vs. const 비교

| 특징        | var                  | let     | const   |
| ----------- | -------------------- | ------- | ------- |
| 스코프      | 함수                 | 블록    | 블록    |
| 호이스팅    | O (초기화 undefined) | O (TDZ) | O (TDZ) |
| 재할당 가능 | O                    | O       | ❌      |
| 재선언 가능 | O                    | ❌      | ❌      |

## ✅ 예제 코드

### let 사용 시 TDZ 발생

```javascript
{
  console.log(a); // ReferenceError
  let a = 10;
}
```

### const 객체 수정 가능

```javascript
const user = { name: "Lee" };
user.name = "Kim";
console.log(user.name); // 'Kim'
```

### var vs let 비교

```javascript
function test() {
  if (true) {
    var x = 1;
    let y = 2;
  }
  console.log(x); // 1
  console.log(y); // ReferenceError
}
test();
```
