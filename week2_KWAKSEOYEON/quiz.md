1. 화살표 함수와 일반 함수의 차이를 말해보세요
2. 다음 중 스프레드 문법을 사용할 수 없는 것은 무엇일까요?

A. `...new Set([1, 2, 3])`

B. `...document.querySelectorAll('div')`

C. `...{ a: 1, b: 2 }`

D. `...['a', 'b', 'c']`

3. 다음 코드의 실행 결과는 무엇일까요?

```jsx
const original = [{ x: 1 }, { y: 2 }];
const copy = [...original];

copy[0].x = 100;

console.log(original[0].x);
```

4. 다음 코드를 실행했을 때 arr3의 값은 무엇일까요?

```jsx
const arr1 = ["a", "b"];
const arr2 = ["c"];
const arr3 = [...arr2, "d", ...arr1];

console.log(arr3);
```
