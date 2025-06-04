# 45장 - 프로미스

## ✅ 핵심 개념 정리

### 45-1. 비동기 처리를 위한 콜백 패턴의 단점

1. 콜백 헬
   콜백 함수를 통해 비동기 처리 결과에 대한 후속 처리를 수행하는 비동기 함수가 비동기 처리 결과를 가지고 또다시 비동기 함수를 호출해야 한다면 콜백 함수 호출이 중첩되어 복잡도가 높아지는 현상이 발생하는데, 이를 콜백 헬이라 한다.

2. 에러 처리의 한계

### 45-2. 프로미스의 생성

프로미스의 상태는 resolve 또는 reject 힘수를 호출하는 것으로 결정된다.

### 45-3. 프로미스의 후속 처리 메서드

1. Promise.protitype.then
2. Promise.prototype.catch
3. Promise.prototype.fianlly

### 45-4. 프로미스의 에러 처리

에러 처리는 then 메서드가 아닌 catch 메서드에서 하는 것을 권장한다.

### 45-5. 프로미스 체이닝

### 45-6. 프로미스의 정적 메서드

1. Promise.resolve / Promise.reject
Promise.resolve와 Promise.reject 메서드는 이미 존재하는 값을 래핑하여 프로미스를 생성하기 위해 사용한다.

2. Promise.all
Promise.all 메서드는 여러 개의 비동기 처리를 모두 병렬 처리할 때 사용한다.

3. Promise.race
Promise.race 메서드는 Promise.all 메서드와 동일하게 프로미스를 요소로 갖는 배열 등의 이터러블을 인수로 전달받는다. Promise.race 메서드는 Promise.all 메서드처럼 모든 프로미스가 fulfilled 상태가 되는 것을 기다리는 것이 아니라 가장 먼저 fulfilled 상태가 된 프로미스의 처리 결과를 resolve하는 새로운 프로미스를 반환한다.

4. Promise.allSettled
Promise.allSettled 메서드는 프로미스를 요소로 갖는 배열 등의 이터러블을 인수로 전달받는다.

### 45-7. 마이크로태스크 큐

콜백 함수나 이벤트 핸들러를 일시 저장한다는 점에서 태스크 큐와 동일하지만 마이크로태스크 큐는 태스크 큐보다 우선순위가 높다.

### 45-8. fetch

fetch 함수는 HTTP 응답을 나타내는 Response 객체를 래핑한 Promise 객체를 반환한다.