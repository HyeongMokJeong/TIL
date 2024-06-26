- 단방향 암호화 기법
	- 해시함수를 통해 고정된 길이의 문자열로 암호화
- 임의 길이의 데이터를 고정 길의의 데이터로 매핑한다.
  -> 고정 크기의 테이블을 정해둘 수 있어서 공간을 효율적으로 사용할 수 있다.

### 질문
- 값이 주어졌을 때, 어떻게 하면 충돌이 최대한 적은 해시 함수를 설계할 수 있을까요?
테이블 크기를 소수로 설정합니다.
해시 함수의 출력 크기를 크게 설정합니다.

- 해시값이 충돌했을 때, 어떤 방식으로 처리할 수 있을까요?
체이닝을 통해 연결 리스트로 연결하는 방식도 있고,
개방 주소법으로 테이블 내의 다른 빈 공간을 찾는 방식도 있습니다.
	1. 선형 탐사법 
		- 선형으로 탐사하여 빈 공간에 배정
		- 일차 군집화 문제 : 같은 해시가 여러번 나올수록 데이터 크기가 커지고, 충돌 가능성도 높아진다.
	2. 제곱 탐사법
		- 해시 충돌 횟수의 제곱만큼 탐사 스텝을 키운다.
		- 이차 군집화 문제 : 같은 해시가 여러번 나오면 계속 충돌이 발생하는 것은 동일하다.
	3. 더블 해싱
		- 해시 함수를 이중으로 사용한다.

- 본인이 사용하는 언어에서는, 어떤 방식으로 해시 충돌을 처리하나요?
java에서는 기본적으로 체이닝을 이용해서 해시 충돌을 처리합니다.
java8부터는 해시 충돌이 많이 발생하는 경우(8개 이상일 때 트리로 변환, 6개 이하로 줄면 다시 링크드 리스트) 내부적으로 링크드 리스트에서 트리 구조로 최적화합니다.
이를 통해 최악의 탐색 시간을 O(n)에서 O(log n)으로 줄일 수 있습니다.
보조 해시 함수 사용 : 기본적으로 크기를 2배를 늘린다.

- Double Hashing 의 장점과 단점에 대해서 설명하고, 단점을 어떻게 해결할 수 있을지 설명해 주세요.
장점
1. 별도의 링크드 리스트, 트리 공간을 사용하지 않아서 효율적입니다.
2. 다른 개방 주소법과 비교했을 때 군집화 발생 가능성이 적어 탐색이 효율적입니다.
단점
1. 서로 다른 해시 함수가 필요하므로 구현 복잡도가 증가합니다.
2. 조사 위치가 무한 반복될 수 있다. -> 테이블 크기를 소수로 설정해야 한다.

- Load Factor에 대해 설명해 주세요. 본인이 사용하는 언어에서의 해시 자료구조는 Load Factor에 관련한 정책이 어떻게 구성되어 있나요?
용량이 어느 정도 찼을 때 사이즈 확장하는지에 대한 개념입니다.
요소 수 / 테이블 용량
java의 HashMap은 기본적으로 0.75로 설정되어 있습니다.
Load Factor를 초과하게 되면 내부적으로 재해싱을 수행하고 테이블 크기를 2배로 늘립니다.

- 다른 자료구조와 비교하여, 해시 테이블은 멀티스레드 환경에서 심각한 수준의 Race Condition 문제에 빠질 위험이 있습니다. 성능 감소를 최소화 한 채로 해당 문제를 해결할 수 있는 방법을 설계해 보세요.
java의 ConcurrentHashMap을 사용합니다.결
- 동시성 문제를 해결하기 위한 키워드 : 가시성 + 원자성 확보
  자바7에서는 분할락(세그먼트 락), 자바8에서는  가시성, 원자성 확보를 볼라틸  + CAS 알고리즘
조회는 비동기로 처리하고, 수정의 경우 내부적으로 여러 개의 세그먼트를 나누어서 락의 범위를 최소화하여 성능을 확보할 수 있습니다.

- 편향을 줄이기 위한 트리 방법
Red-Black Tree
B Tree, B+ Tree

- 왜 DB에서는 B Tree 구조를 사용하나
다른 구조 Red-Block Tree 등은 이진 트리이다.