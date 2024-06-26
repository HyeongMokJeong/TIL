- 선형 자료구조 중 하나로, 연결 리스트라고도 한다.
### 핵심 요소
- 노드 : 기본 단위. **데이터 필드**와 **링크 필드**로 구성
- 헤드 : 가장 처음에 위치하는 노드
- 테일 : 가장 마지막에 위치하는 노드

### 특징
- 데이터의 동적 추가, 삭제에는 효율적이다.
	- 배열과 달리 기존 데이터의 재할당이 필요가 없다.
		- ArrayList는 내부적으로 배열을 사용해서 추가, 삭제를 하려면 메모리 재할당이 필요하다.
	- 새로운 노드를 추가하고 링크만 수정해주면 된다.

- Random access가 불가능하고, Sequential access(순차 접근)만 가능하다.

- 다양한 형태로 확장될 수 있다.
	- 단방향 연결 리스트
	- 양방향(이중) 연결 리스트
	- 원형 연결 리스트

### 질문
- JAVA에서 같은 순차 접근 방식을 사용할 때, Linked List와 Array List 어느 것이 더 빠를까
	- 캐시의 참조 지역성
	- 연속적으로 데이터를 저장하는 ArrayList가
	 비 연속적으로 데이터를 저장하는 Linked List 보다 빠르다. 

- 일반 배열과 링크드 리스트를 비교하라
	- 배열
		- 배열은 크기가 고정되어 있다.
		- 배열의 요소는 메모리 상에서 연속적으로 할당된다. -> 참조 지역성을 활용할 수 있다.
		- 인덱스를 이용한 O(1)의 랜덤 접근이 가능하다.
	- 링크드 리스트
		- 링크드 리스트는 크기가 고정되어 있지 않다. -> 동적으로 필요한 만큼만 사용가능하다.
		- 각 요소가 노드로 구성되며, 필요에 따라 노드가 추가, 삭제된다.
			- 추가, 삭제에 대해서는 O(1)의 복잡도를 가진다.
		- 접근에 대해서는 비교적 느린 성능을 보인다.
		- 하나의 노드가 데이터와 포인터를 모두 가져야 하므로 추가적인 메모리 공간이 필요하다.

- 링크드 리스트로 구현할 수 있는 자료구조는?
	- Stack
	- Queue : JAVA에서 Linked List는 Queue의 구현체
	- Deque : 양방향 Linked List
	- Graph
	- Hash Table : 동일한 해시를 갖는 여러 키를 저장할 때 사용
	- Tree