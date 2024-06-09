
- Java 8
1. LocalDateTime과 같은 새로운 날짜, 시간 API 제공
2. lambda
3. Stream API
4. 인터페이스 default method
5. Optional
6. 일부 콜렉션의 성능 개선
	1. HashMap
		1. 기본 해시 충돌 전략은 링크드 리스트
		2. 해시 충돌이 8회 이상이면 트리 구조로 변환
		3. 6회 이하로 줄어들면 다시 링크드 리스트 사용
	2. ConcurrentHashMap
		1. 이전까지는 내부적으로 여러 개의 세그먼트를 나누고 세그먼트 별로 분할 락을 걸어 동시성 해결
		2. 자바 8 이후에서는 volatile 키워드로 가시성 확보 & CAS 알고리즘으로 원자성 확보하여 해결

- Java 17
7. recode 키워드
8. 애플 실리콘 지원
9. Stream.toList()
10. 스프링부트 3.0 최소 버전