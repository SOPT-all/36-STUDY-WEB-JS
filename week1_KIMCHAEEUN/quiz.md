## Q1.
마지막 줄에서 출력되는 count의 값은 무엇인지 이유와 함께 답하세요.

```javascript
var count = 0;

function increase() {
  for (var count = 0; count < 3; count++) {
    console.log(count);
  }
}

increase();
console.log(count); // ???
```

## Q2.
다음 문장을 읽고 참이면 O, 거짓이면 X로 답하세요.

1. var 키워드로 선언된 변수는 함수가 끝나면 즉시 메모리에서 해제된다. ( )

2. 전역 변수는 어플리케이션 전역에서 접근 가능하기 때문에 유지 보수가 어렵다. ( )

3. 암묵적으로 선언된 변수도 전역 객체의 프로퍼티가 된다. ( )

## Q3.
다음 문장을 읽고 참이면 O, 거짓이면 X로 답하세요.

1. let 키워드로 선언된 변수는 재할당이 불가능하다. ( )

2. const 키워드로 선언된 객체의 프로퍼티는 변경할 수 없다. ( )

3. var는 변수 선언 이전에도 참조할 수 있다. ( )

4. let과 const는 블록 레벨 스코프를 가진다. ( )


## Q4.
아래 코드의 문제점을 설명하고, 더 안전하고 명확하게 리팩토링 해보세요.

```javascript
function calculate() {
  var result = 0;

  for (var i = 0; i < 5; i++) {
    var result = i * 2;
  }

  console.log(result); // ?
}
calculate();
```