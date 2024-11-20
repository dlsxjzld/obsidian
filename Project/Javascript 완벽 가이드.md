# 함수 (섹션 6)
언제 `bind()`가 유용할까요?
* 함수의 인자를 '사전 구성' 하려는 상황에서 함수를 직접 호출하지 않을 때. 

함수 선언문
함수 표현식
화살표 함수
rest parameter
arguments
bind
call, apply

# JavaScript에서 DOM으로 작업하기 (섹션 7)

### "DOM"이란 무엇인가?
### document 와 window 객체
- window는 현재 로드된 탭에 접근 권한이 있다.
- window는 브라우저의 최상위 객체이다.
- document는 html 문서 객체이며 window에 포함된다.

### DOM과 생성 방식 이해하기
### 노드 & 요소 - DOM 쿼리하기 개요
### DOM에서 요소 선택하기
	1. document.querySelector(<CSS selector>);
	2. document.getElementById(<ID>);
	3. document.querySelectorAll(<CSS selector>);
	4. document.getElementsByClassName(<CSS CLASS>);
	5. document.getElementsByTagName(<HTML TAG>);
### Attributes vs Properties
- Properties : 생성된 DOM 객체들에 자동으로 추가됨
- Attributes : 엘리멘트 태그의 HTML 코드에 위치한다.
	- `<input id = "input-1" class="input-default" value="Enter text...">`
	- `const input
	- 1:1 (+ live-sync) 매핑 -> input.id
	- different names (but live-sync) -> input.className
		- ex) input의 class(Attribute)는 DOM 객체의 className 프로퍼티로 변환된다. 
	- 1:1 mapping( 1-way live-sync) -> input.value
		- 입력값을 바꿔도 속성에 반영되지 않고, 속성을 바꾸는 경우에만 프로퍼티 값이 변한다.

- DOM 탐색 
	- 자식, 자손, 부모, 조상 요소들.
	- children : HTML에 존재하는 하위 엘리먼트 태그들에 접근 가능
	- childNodes: text와 엘리먼트들에 접근 가능
	- parentElement: 가장 가까운 부모 요소 노드에 접근
	- parentNode: 가장 가까운 부모 노드에 접근
		- document.documentElement.parentElement 는 null이 나온다.
		- document.documentElement.parentNode 는 document가 나온다.
	- closest: 요소 트리에 있는 아무 조상을 선택할 때 좋다.
	- nextSibling: 다음 텍스트 노드가 선택됨
	- previousSibling: 이전 텍스트 노드가 선택됨
	- nextElementSibling: 다음 엘리먼트 태그가 선택됨
	- previousElementSibling: 이전 엘리먼트 태그가 선택됨
- DOM 탐색과 쿼리 메서드
	- DOM 탐색 프로퍼티를 사용하는 것은 좋지만 주의를 기울여야 한다. HTML 이 바뀌면 언제든 바뀔 수 있기 때문이다.
		- 탐색하는 관계가 동일하게 유지될 경우에 사용하자.
	- 쿼리 메서드 사용도 두려워하지 말자. 
- styling DOM Elements
	- style Property
	- className
	- classList
- Creating & Inserting Elements
	- innerHTML: 
		- 요소의 모든 HTML 콘텐츠를 변경할 때 유용하다.
		- 기존 콘텐츠에 뭔가를 추가할 때는 좋지 않다. 
			- 많은 HTML을 다시 렌더링 해서 성능이 좋지 않다.
	- insertAdjacentHTML
		- 위치와 값을 입력해서 추가할 수 있다. 
		- innerHTML 대신 쓰자.
		- 브라우저에 렌더링 할 요소나 콘텐츠를 알려줘서 모든 HTML 콘텐츠가 될 수 있고 단일 요소가 필요 없으며 HTML 코드를 원하는 만큼 복잡해진다는 단점이 있다. 새로 렌더링 된 콘텐츠에 직ㅈ겁 액세스할 수 없다. 
	- createElement
		- createElement('태그명')
		- appendChild: 1개 가능
		- append: 여러개 가능
		- prepend
		- after
		- before
		- replaceWith
		- cloneNode
- 라이브 노드 리스트 vs 정적 노드 리스트
	- querySelectorAll : 정적 노드 리스트
	- getElementsBy~ : 라이브 노드 리스트
	- createElement 등으로 태그 만들어서 추가시 
		- 정적 노드 리스트는 추적 안됨. 추가 되기 전의 스냅샷만 가지고 있음.
		- 라이브 노드 리스트는 추적 됨. 
- 요소 제거하기
	- 지우고 싶은 노드 선택 후 삭제
		- list.remove()
	- 지우고 싶은 노드 선택 후 부모 노드로 가서 remove
		- list.parentElement.removeChild(list)
- replaceWith 으로 노드 교체.
- cloneNode는 addEventListener로 추가된 이벤트 리스너를 복사하지 않는다. 
	- cloneNode()
	- cloneNode(deep)
		- deep이 true이면 하위 텍스트 노드에 있을 수 있는 텍스트를 포함하여 노드와 해당 하위 트리 전체도 복사됩니다.
		- deep이 false이면 노드만 복제됩니다. 노드에 포함된 텍스트를 포함한 하위 트리는 복제되지 않습니다.