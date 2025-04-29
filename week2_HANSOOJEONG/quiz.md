## Q1. 객체 리터럴의 구조와 실행 결과
```js
const key = 'score';
const value = 90;

const student = {
  name: 'Soojeong',
  [key]: value,
  greet() {
    return `Hello, my name is ${this.name}`;
  }
};

console.log(student.score); // ?
console.log(student['name']); // ?
console.log(student.greet()); // ?
```
(1) console의 결과를 순서대로 적어주세요.

(2) 위 코드에서 프로퍼티와 메서드를 구분해주세요. 

## Q2. 화살표 함수
(1) 화살표 함수와 일반 함수의 차이점에 대해 간단히 서술해주세요. 

(2) 화살표 함수로 메서드를 정의하는 것이 바람직하지 않은 이유에 대해 간단히 서술해주세요. 

## Q3. filter, map, forEach, reduce 중 원본 배열을 변경하는 메서드는 무엇인지 설명하고, 아래 코드의 결과를 예측해주세요.

```js
const arr = [1, 2, 3, 4, 5];

const newArr = arr.filter(num => num % 2 === 0).map(num => num * 2);

console.log('newArr:', newArr);
console.log('original arr:', arr);
```

## Q4. 코드 내부 (1)~(5)에 알맞은 말을 적고 스프레드 문법을 사용해 코드를 다시 작성해주세요.  
```js
var arr1 = [1, 4];
var arr2 = [2, 3];

/*

 apply 메서드의 2번째 인수(배열)는 apply 메서드가 호출한 splice 메서드의 인수 목록이다.
 apply 메서드의 2번째 인수 [1, 0].concat(arr2)는 (1)_______________________ 으로 평가된다.
 따라서 splice 메서드에 apply 메서드의 2번째 인수 (2)______________________ 가 해체되어 전달된다.
 즉, arr1[1]부터 (3)_____개의 요소를 제거하고, 그 자리에 새로운 요소 (4)___________를 삽입한다.

 */

Array.prototype.splice.apply(arr1, [1, 0].concat(arr2));

console.log(arr1); // (5) ?
```