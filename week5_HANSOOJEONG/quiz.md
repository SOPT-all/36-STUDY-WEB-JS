## Q1. 아래에서 버튼 클릭하면 어떻게 출력 되는지 순서대로 작성해주세요.
```js
<div id="div">
  <p id="p">
    <button id="button">Click me</span>
  </p>
</div>

<script>
  const log = (msg) => console.log(msg);

  document.getElementById('div').addEventListener('click', () => log('DIV - bubbling'));
  document.getElementById('p').addEventListener('click', () => log('P - bubbling'));
  document.getElementById('button').addEventListener('click', () => log('BUTTON- bubbling'));

  document.getElementById('div').addEventListener('click', () => log('DIV - capturing'), true);
  document.getElementById('p').addEventListener('click', () => log('P - capturing'), true);
  document.getElementById('button').addEventListener('click', () => log('BUTTON- capturing'), true);
</script>
```

## Q2. 해당 콘솔이 찍히는 순서와 그 이유를 작성해주세요.
```js
console.log('Start');

setTimeout(() => {
  console.log('Timeout');
}, 0);

console.log('End');
```

## Q3. 디바운스와 쓰로틀링의 차이점을 작성해주세요.

## Q4. 디바운스와 스로틀은 각각 어떠한 상황에서 사용하면 유리한지 작성해주세요. 

## Q5. 타이머 함수
```js
const id = setInterval(() => {
  console.log('자스정자스정');
}, 1000);

// 5초 후 타이머 종료
```
### 1. 위 코드에서 타이머를 5초 후 종료하기 위한 코드를 작성해주세요.

### 2. setTimeout과 setInterval의 차이점을 설명해주세요.
