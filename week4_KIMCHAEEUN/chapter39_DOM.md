# 39장 - DOM

## ✅ 핵심 개념 정리

DOM은 HTML 문서의 계층적 구조와 정보를 표현하며 이를 제어할 수 있는 API, 즉 프로퍼티와 메서드를 제공하는 트리 자료구조다.

### 39-1. 노드

HTML 요소는 HTML 문서를 구성하는 개별적인 요소를 의미한다.

트리 자료구조는 노드들의 계층 구조로 이뤄진다. 즉, 트리 자료구조는 부모 노드와 자식노드로 구성되어 노드 간의 계층적 구조를 표현하는 비선형 자료구조를 말한다.

노드 객체들로 구성된 트리 자료구조를 DOM이라 한다.

DOM은을 구성하는 노드 객체는 자신의 구조와 정보를 제어할 수 있는 DOM API를 사용할 수 있다.

### 39-2. 요소 노드 취득

요소 노드의 취득은 HTML 요소를 조작히는 시작점이다. 이를 위해 D○M은 요소 노드를 취득할 수 있는 다양한 메서드를 제공한다.

- id를 이용한 요소 노드 취득 : Document.prototype.getEIementByld 메서드는 인수로 전달한 id 어트리뷰트 값(이하 id 값)을 갖는 하나의 요소 노드를 탐색하여 반환한다. getEIementByld 메서드는 Document.prototype의 프로퍼티다. 따라서 반드시 문서 노드인 document를 통해 호출해야 한다.

- 태그 이름을 이용한 요소 노드 취득 : Document.prototype/Element.prototype.getElementsByTagName 메서드는 인수로 전달한 태그 이름을 갖는 모든 요소 노드들을 탐색하여 반환한다. 메서드 이름에 포함된 EIements가 복수형인 것에서 알 수 있듯이 getEIementsByTagName 메서드는 여러 개의 요소 노드 객체를 갖는 DOM 컬렉션 객체인 HTMLCollectlon 객체를 반환한다.

- class를 이용한 요소 노드 취득 : Document.prototype/Element.prototype.getElementsByClassName 메서드는 인수로 전달한 class 어트리뷰트 값을 갖는 모든 요소 노드들을 탐색하여 반환한다. 인수로 전달한 class 값은 공백으로 구분하여 여러 개의 class를 지정할 수 있다. getElementsByTagName 메서드와 마찬가지로 getElementsByClassName 메서드는 여러 개의 요소 노드 객체를 갖는 DOM 컬렉션 객체인 HTMLCollectlon 객체를 반환한다.

- CSS 선택자를 이용한 요소 노드 취득 : CSS 선택자는 스타일을 적용하고자 하는 HTML 요소를 특정할 때 사용하는 문법이다.

- 특정 요소 노드를 취득할 수 있는지 확인 : Element.prototype.matches 메서드는 인수로 전달한 CSS 선택자를 통해 특정 요소 노드를 취득할 수 있는지 확인한다.

- HTMLCollection과 NodeList : DOM 컬렉션 객체인 HTMLCollection과 NodeList는 DOM API가 여러 개의 결과값을 반환하기 위한 DOM 컬렉션 객체다. HTMLCollection과 NodeList는 모두 유사 배열 객체이면서 이터러블이다. 

### 39-3. 노드 탐색

요소 노드를 취득한 디음, 취득한 요소 노드를 기점으로 DOM 트리의 노드를 옮겨 다니며 부모, 형제. 자식 노드 등을 탐색해야 할 때가 있다.
DOM 트리 상의 노드를 탐색할 수 있도록 Node. Element 인터페이스는 트리 탐색 프로퍼티를 제공
한다.

- 공백 텍스트 노드
- 자식 노드 탐색
- 자식 노드 존재 확인
- 요소 노드의 텍스트 노드 탐색
- 부모 노드 탐색
- 형제 노드 탐색

### 39-4. 노드 정보 취득

노드 객체에 대한 정보를 취득하려면 Node,prototype.nodeType, Node.prototype.nodeName과 같은 노두 정보 프로퍼티를 사용한다.

### 39-5. 요소 노드의 텍스트 조작

- nodeValue
- textContent

### 39-6. DOM 조작

DOM 조작은 새로운 노드를 생성하여 DOM에 추가하거나 기존 노드를 삭제/교체하는 것을 말한다. 이는 리플로우와 리페인트가 발생하는 원인이 되므로 성능에 영향을 준다. 따라서 복잡한 콘텐츠를 다루는 DOM 조작은 성능 최적화를 위해 주의해서 다루어야 한다.

- innerHTML
- insertAdjacentHTML 메서드
- 노드 생성과 추가
- 복수의 노드 생성과 추가
- 노드 삽입
- 노드 이동
- 노드 복사
- 노드 교체
- 노드 삭제

### 39-7. 어트리뷰트

- 어트리뷰트 노드와 attributes 프로퍼티
- HTML 어트리뷰트 조작
- HTML 어트리뷰트 vs. DOM 프로퍼티
- data 어트리뷰트와 dataset 프로퍼티

### 39-8. 스타일

- 인라인 스타일 조작
- 클래스 조작
- 요소에 적용되어 있는 CSS 스타일 참조