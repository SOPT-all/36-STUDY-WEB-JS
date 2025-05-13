## Q1. 다음 코드의 출력 결과는 무엇이며, 그 이유는 무엇일까요?

```jsx
const obj = {
  value: 42,
  print: function () {
    const inner = function () {
      console.log(this.value);
    };
    inner();
  },
};

obj.print();
```

## Q2. 다음 중 `this`가 생성자 함수가 생성할 인스턴스를 바인딩하는 경우는 언제일까요?

A. 일반 함수 호출
B. 객체의 메서드 호출
C. `new` 키워드를 사용한 생성자 함수 호출
D. 콜백 함수 내부에서 호출

## Q3. 다음 중 **실행 컨텍스트가 새로 생성되는 순간**은 언제일까요?

A. 변수 선언문이 실행될 때
B. 함수가 정의될 때
C. 함수가 호출될 때
D. if 문이 실행될 때

## Q4. 다음 코드의 출력 결과는 무엇이며, 그 이유는 무엇일까요?

```jsx
function makeCounter() {
  let count = 0;
  return function () {
    count++;
    console.log(count);
  };
}

const counter1 = makeCounter();
counter1();
counter1();

const counter2 = makeCounter();
counter2();
```
