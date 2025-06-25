## Q1. 아래 코드의 문제점을 간단히 설명해주세요.
```js
// sweb.js
var x = 'sweb';
console.log(window.x);

// waveweb.js
var x = 'waveweb';
console.log(window.x);

// html에서 script 태그로 분리해 2개의 js파일을 불러온다. 
<!DOCTYPE html>
<html>
<body>
  <script src="sweb.js"></script>
  <script src="waveweb.js"></script>
</bodv>
</html>
```

## Q2. ox 문제
### (1) 모듈 내에서 선언한 식별자는 모듈 외부에서 참조할 수 있다.
### (2) 변수, 함수, 클래스 등 모든 식별자를 export 할 수 있다. 
### (3) 모든 브라우저는 ESM을 지원한다. 


## Q3. 빈칸 넣기 
### (1) app.mjs 파일이 애플리케이션의 진입점이라고 할 때, 반드시 ( ___ )로 로드해야 한다. 
### (2) ( ___ ) 키워드를 사용하는 경우 var, let, const 키워드는 사용할 수 없다. 
### Babel은 트랜스파일러이고 Webpack은 ( ___ )이다. 

## Q4. Webpack의 장점을 간단히 적어주세요.

