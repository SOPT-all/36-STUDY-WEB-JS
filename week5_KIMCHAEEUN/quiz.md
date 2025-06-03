## Q1. 빈칸에 알맞은 말을 쓰세요.

1. 마우스 커서가 요소 안으로 진입할 때 발생하는 이벤트는 __________이다.

2. 이벤트 위임은 이벤트를 상위 요소에 등록해서 _______ 요소의 이벤트까지 처리할 수 있게 하는 방식이다.

3. 이벤트의 기본 동작을 막으려면 event._______()을 호출한다.

4. addEventListener로 이벤트를 등록할 때, 이벤트 핸들러에 전달되는 첫 번째 인자는 ___________ 객체이다.

5. DOM 요소에 직접 onclick 속성을 써서 이벤트를 등록하는 방식은 ___________ 방식이라고 한다.

## Q2. 아래 코드의 실행 결과는?

```js
<button id="btn">Click me!</button>
<script>
  const $btn = document.getElementById("btn");

  $btn.addEventListener("click", function () {
    console.log(this.id);
  });
</script>
```

## Q3. 아래 코드에서 removeEventListener가 작동하지 않는 이유는?

```js
const btn = document.querySelector("button");

btn.addEventListener("click", function () {
  console.log("clicked!");
});

btn.removeEventListener("click", function () {
  console.log("clicked!");
});
```

## Q4. O / X

1. setInterval은 콜백이 실행되기 전까지 기다렸다가 주기를 시작한다. O / X

2. 이벤트 객체의 currentTarget은 이벤트를 실제로 발생시킨 요소를 가리킨다. O / X

3. stopPropagation()을 호출하면 이벤트 전파가 완전히 차단된다. O / X

4. keypress 이벤트는 모든 키 입력에 대해 발생한다. O / X
