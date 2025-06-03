# 40장 - 이벤트

## ✅ 핵심 개념 정리

### 40-1. 이벤트 드리븐 프로그래밍

브라우저는 처리해야 할 특정 사건이 발생하면 이를 감지하여 이벤트를 발생시킨다. 이벤트가 발생했을 때 호출될 함수를 이벤트 핸들러라 하고, 브라우저에게 이벤트 핸들러의 호출을 위임하는 것을 이벤트 핸들러 등록이라 한다.

```html
<!DOCTYPE html>
<html>
  <body>
    <button>Click me!</button>
    <script>
      const $button = document.querySelector("button");
      // 사용자가 버튼을 클릭하면 함수를 호출하도록 요청
      $button.onclick = () => {
        alert("button click");
      };
    </script>
  </body>
</html>
```

이벤트와 이벤트 핸들러를 통해 사용자와 애플리케이션은 상호작용을 할 수 있고, 이와 같이 프로그램의 흐름을 이벤트 중심으로 제어하는 프로그래밍 방식을 이벤트 드리븐 프로그래밍이라 한다.

### 40-2. 이벤트 타입

이벤트 타입은 이벤트의 종류를 나타내는 문자열이다.

1. 마우스 이벤트

| 이벤트 타입 | 이벤트 발생 시점                                       |
| ----------- | ------------------------------------------------------ |
| click       | 마우스 버튼을 클릭했을 때                              |
| dblclick    | 마우스 버튼을 더블 클릭했을 때                         |
| mousedown   | 마우스 버튼을 눌렀을 때                                |
| mouseover   | 마우스 커서를 HTML 요소 안으로 이동했을 때(버블링된다) |

2. 키보드 이벤트

| 이벤트 타입 | 이벤트 발생 시점                             |
| ----------- | -------------------------------------------- |
| keydown     | 모든 키를 눌렀을 때 발생한다.                |
| keypress    | 문자 키를 눌렀을 때 연속적으로 발생한다.     |
| keyup       | 누르고 있던 키를 놓았을 때 한 번만 발생한다. |

3. 포커스 이벤트

| 이벤트 타입 | 이벤트 발생 시점                                  |
| ----------- | ------------------------------------------------- |
| focus       | HTML 요소가 포커스를 받았을 때(버블링되지 않는다) |
| blur        | HTML 요소가 포커스를 잃었을 때(버블링되지 않는다) |
| focusin     | HTML 요소가 포커스를 받았을 때(버블링된다)        |
| focusout    | HTML 요소가 포커스를 잃었을 때(버블링된다)        |

focusin, focusout 이벤트 핸들러는 addEventListener 메서드 방식을 사용해 등록해야 한다.

4. 폼 이벤트

5. 값 변경 이벤트

6. DOM 뮤테이션 이벤트

7. 뷰 이벤트

8. 리소스 이벤트

### 40-3. 이벤트 핸들러 등록

1. 이벤트 핸들러 어트리뷰트 방식

이벤트 핸들러 어트리뷰트의 이름은 onclick과 같이 on 접두사와 이벤트의 종류를 나타내는 이벤트 타입으로 이루어져 있다. 이벤트 핸들러 어트리뷰트 값으로 함수 참조가 아닌 함수 호출문 등의 문을 할당하면 이벤트 핸들러가 등록된다.

```html
<!DOCTYPE html>
<html>
  <body>
    <button onclick="sayHi('Lee')">Click me!</button>
    <script>
      function sayHi(name) {
        console.log(`Hi! ${name}.`);
      }
    </script>
  </body>
</html>
```

2. 이벤트 핸들러 프로퍼티 방식

window 객체와 Document, HTMLElement 타입의 DOM 노드 객체는 이벤트에 대응하는 이벤트 핸들러 프로퍼티를 가지고 있다.

```html
<!DOCTYPE html>
<html>
  <body>
    <button>Click me!</button>
    <script>
      const $button = document.querySelector("button");

      // 이벤트 핸들러 프로퍼티 방식은 하나의 이벤트에 하나의 이벤트 핸들러만을 바인딩할 수 있다.
      // 첫 번째로 바인딩된 이벤트 핸들러는 두 번째 바인딩된 이벤트 핸들러에 의해 재할당되어 실행되지 않는다.
      $button.onclick = function () {
        console.log("Button clicked 1");
      };

      // 두 번째로 바인딩된 이벤트 핸들러
      $button.onclick = function () {
        console.log("Button clicked 2");
      };
    </script>
  </body>
</html>
```

3. addEventListener 메서드 방식

```html
<!DOCTYPE html>
<html>
  <body>
    <button>Click me!</button>
    <script>
      const $button = document.querySelector("button");

      // 이벤트 핸들러 프로퍼티 방식
      //   $button.onclick = function () {
      //     console.log("button click");
      //   };

      // addEventListener 메서드 방식
      $button.addEventListener("click", function () {
        console.log("button click");
      });
    </script>
  </body>
</html>
```

### 40-4. 이벤트 핸들러 제거

addEventListener 메서드로 등록한 이벤트 핸들러를 제거하려면 EventTarget.prototype.removeEventListener 메서드를 사용한다. 단, addEventLIstener 메서드에 전달한 인수와 removeEventLIstener 메서드에 전달한 인수가 일치하지 않으면 이벤트 핸들러가 제거되지 않는다.

단, 기명 이벤트 핸들러 내부에서 removeEventListener 메서드를 호출하여 이벤트 핸들러를 제거하는 것은 가능하다. 기명 함수를 이벤트 핸들러로 등록할 수 없다면 호출된 함수, 즉 함수 자신을 가리키는 arguments.callee를 사용할 수도 있다.

### 40-5. 이벤트 객체

이벤트가 발생하면 이벤트에 관련한 다양한 정보를 담고 있는 이벤트 객체가 동적으로 생성된다. 생성된 이벤트 객체는 이벤트 핸들러의 첫 번째 인수로 전달된다.

1. 이벤트 객체의 상속 구조

2. 이벤트 객체의 공통 프로퍼티

3. 마우스 정보 취득

4. 키보드 정보 취득

### 40-6. 이벤트 전파

DOM 트리 상에 존재하는 DOM 요소 노드에서 발생한 이벤트는 DOM 트리를 통해 전파된다. 이를 이벤트 전파라고 한다.

### 40-7. 이벤트 위임

이벤트 위임은 여러 개의 하위 DOM 요소에 각각 이벤트 핸들러를 등록하는 대신 하나의 상위 DOM 요소에 이벤트 핸들로를 등록하는 방법을 말한다.

이벤트 위임을 통해 상위 DOM 요소에 이벤트 핸들러를 등록하면 여러 개의 하위 DOM 요소에 이벤트 핸들러를 등록할 필요가 없고, 동적으로 하위 DOM 요소를 추가하더라도 일일이 추가된 DOM 요소에 이벤트 핸들러를 등록할 필요가 없다.

### 40-8. DOM 요소의 기본 동작 조작

1. DOM 요소의 기본 동작 중단
   이벤트 객체의 preventDefault 메서드는 이러한 DOM 요소의 기본 동작을 중단시킨다.

2. 이벤트 전파 방지
   이벤트 객체의 stopPropagation 메서드는 이벤트 전피를 중지시킨다.

### 40-9. 이벤트 핸들러 내부의 this

1. 이벤트 핸들러 어트리뷰트 방식
   벤트 핸들러 어트리뷰트 방식에 의해 임묵적으로 생성된 이벤트 핸들러 내부의 this는 이벤트를 바인딩힌 DOM 요소를 가리킨다. 이는 이벤트 핸들러 프로퍼 티 방식과 동일하다.

2. 이벤트 핸들러 프로퍼티 방식과 addEventListener 메서드 방식
   이벤트 핸들러 내부의 this는 이벤트 객체의 currentTarget 프로퍼티와 같다.

### 40-10. 이벤트 핸들러에 인수 전달
