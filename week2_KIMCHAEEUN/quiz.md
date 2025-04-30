## Q1. 다음 코드의 출력 결과는?

```js
const user = {
  name: 'Jae',
  greet() {
    return `Hello, ${this.name}`;
  },
  arrow: () => `Hi, ${this.name}`,
};

console.log(user.greet());
console.log(user.arrow());
```

## Q2. 자바스크립트의 배열이 "진짜 배열"이 아닌 이유를 서술하고, 아래 코드의 출력 결과를 구하세요.

```js
const arr = [];
arr[2] = 'a';
arr['foo'] = 'bar';

console.log(arr.length);
console.log(Object.keys(arr));
console.log(arr);
```

## Q3. 다음 코드 출력 결과는?

```js
const user = {
  name: 'Chaeeun',
  hobbies: ['코딩', '독서'],
  list() {
    return this.hobbies.map(hobby => `${this.name} likes ${hobby}`);
  }
};

console.log(user.list());
```


## Q4. 다음 중 스프레드 문법과 관련 없는 특징은?

a. 복사 시 얕은 복사(shallow copy)이다.
b. 객체 리터럴에서 중복 키는 나중 값으로 덮어쓴다.
c. 배열 요소를 개별로 펼쳐준다.
d. 함수 내에서 가변 인자들을 배열로 받을 수 있다.