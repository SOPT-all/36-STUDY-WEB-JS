## Q1. 다음 코드의 실행 결과는?

```js
var x = 1;

const obj = {
  x: 10,
  getX: function () {
    const inner = () => this.x;
    return inner();
  },
};

console.log(obj.getX());
```

## Q2. 다음 코드의 실행 결과는?

```js
function foo() {
  console.log(this);
}

const obj = { foo };

obj.foo(); // (1)
(foo = obj.foo)(); // (2)
```

## Q3. 다음 코드에서 `console.log(x);`의 출력하는 값은?

```js
const x = 1;

function outer() {
  const x = 2;
  function inner() {
    console.log(x);
  }
  return inner;
}

const fn = outer();
const x = 3;
fn();
```

## Q4. 다음 문장을 읽고 참이면 O, 거짓이면 X로 답하세요.

1. 화살표 함수 내부의 this는 자신이 정의된 위치의 상위 스코프의 this 값으로 평가되며, 이는 함수가 호출되는 방식과는 무관하다. ( )

2. 실행 컨텍스트는 소스코드 실행 시 생성되며, 코드 실행에 필요한 식별자 정보나 this 바인딩 등을 포함한 렉시컬 환경을 동적으로 구성한다. ( )

3. 중첩 함수가 상위 함수보다 나중에 호출되더라도, 상위 함수의 실행 컨텍스트가 스택에서 제거되었기 때문에 해당 지역 변수는 더 이상 참조할 수 없다. ( )

4. 전역 코드, 함수 코드, eval 코드, 모듈 코드는 각각 실행될 때마다 별도의 실행 컨텍스트를 생성하며, 이는 실행 순서에 따라 스택에 쌓였다가 제거된다. ( )

5. 클로저는 외부 함수의 변수에 대한 참조를 내부 함수가 유지하고 있을 때만 성립하며, 단순히 중첩 함수가 있다고 해서 클로저가 형성되는 것은 아니다. ( )