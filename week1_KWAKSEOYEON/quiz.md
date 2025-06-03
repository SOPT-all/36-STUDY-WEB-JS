## 📌 퀴즈 1. 스코프 체인

```jsx
var x = "global";

function outer() {
  var x = "outer";

  function inner() {
    console.log(x);
  }

  inner();
}

outer();
```

Q1: inner 함수에서 출력되는 x 값은?

## 📌 퀴즈 2. 함수 레벨 스코프 (var vs let)

```jsx
function foo() {
  console.log(x);
  var x = 5;
}

foo();
```

Q2: 위 코드에서 x의 최종 출력 결과는 ?

## 📌 퀴즈 3. 호이스팅

```jsx
function foo() {
  console.log(x);
  var x = 5;
}

foo();
```

Q3: 이 코드의 출력 결과는?

## 📌 퀴즈 4. 렉시컬 스코프

```jsx
var x = 100;

function bar() {
  console.log(x);
}

function baz() {
  var x = 200;
  bar();
}

baz();
```

Q4: bar 함수는 어디서 정의되었을까요? 출력값은?
