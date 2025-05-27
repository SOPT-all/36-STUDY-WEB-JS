## 타이머

### 호출 스케줄링
함수를 명시적으로 호출하면 함수가 즉시 실행된다. 함수를 명시적으로 호출하지 않고 일정 시간이 경과된 이후에 호출되도록 함수 호출을 예약하기 위해서는 타이머 함수를 사용해야 한다. 
이를 호출 스케줄링이라고 한다. 

타이머 함수 setTimeout과 setInterval이 생성한 타이머가 만료되면 콜백 함수가 호출된다. 

- 자바스크립트 엔진은 싱글 스레드로 동작
- setTimeout과 setInterval은 비동기 처리 방식으로 동작

### 타이머 함수
- setTimeout / clearTimeout

const timeoutId = setTimeout(func|code[, delay, param1, param2, ... ]);

setTimeout 함수는 단 한 번 동작하는 타이머를 생성

clearTimeout 함수는 호출 스케줄링을 취소 

- setInterval / clearInterval

const timerId = setInterval(func|code[, delay, param1, param2, ... ]);

setInterval 함수는 전달받은 시간으로 반복 동작하는 타이머를 생성

clearInterval 함수는 호출 스케줄링을 취소 

### 디바운스와 스로틀
디바운스와 스로틀은 scroll, resize, input 같이 짧은 시간 간격으로 연속해서 발생하는 이벤트를 그룹화해서 과도한 이벤트 핸들러의 호출을 방지하는 프로그래밍 기법이다. 

### 디바운스 
debounce는 짧은 시간 간격으로 발생하는 이벤트를 그룹화해서 마지막에 한 번만 이벤트 핸들러가 호출되도록 한다. 

### 스로틀
스로틀은 짧은 시간 간격으로 연속해서 발생하는 이벤트를 그룹화해서 일정 시간 단위로 이벤트 핸들러가 호출되도록 호출 주기를 만든다. 