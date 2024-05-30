- Not Only SQL
- 문서, 그래프 DB, Key-Value 저장소와 같은 비관계형 데이터 구조를 사용하여 데이터를 관리
- RDB보다 속도가 빠르다
	- 배열을 사용하는 RDB와 다르게 HashMap 구조를 통해 데이터를 저장
- 확장성이 좋다
	- RDB는 수평적 확장이 어렵다. -> DB가 2개가 되면 생기는 문제들
	- 반면 NoSQL은 수직, 수평 확장이 용이하다.
- 각각 필요한 경우
	- RDB 
		- 관계를 맺고 있는 데이터가 자주 수정되는 경우
		- 스키마 구조가 명확하고 변경되지 않는 경우
	- NoSQL
		- 정확한 데이터 구조를 알 수 없거나 변경 / 확장될 수 있는 경우
		- 조회가 자주 발생하고 수정이 적은 경우