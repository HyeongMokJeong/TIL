### Stack
- 후입선출 자료구조
- 'top'을 통해서만 데이터를 삽입, 제거할 수 있다.
	- push, pop
- 비어있는 스택에서 pop -> stack underflow
- 가득 찬 스택에 push -> stack overflow
- 방문기록, 실행취소 등

### Queue
- 선입선출 자료구조
- 'front'를 통해 데이터를 제거하고, 'rear'를 통해 데이터를 삽입한다.
	- enqueue, dequeue

- 대표적인 종류
	- 선형 큐
	- 우선순위 큐
		- 우선순위 -> 순서 순으로 삭제된다.
		- 우선순위로 정렬해야할 필요가 있다.
			- 주로 [Heap](Heap.md) 자료구조로 구현한다.
	- 원형 큐
		- 모듈러 연산을 통해 고정된 크기의 원형 큐를 구현한다.
		- front, rear가 순환하며 데이터를 삽입, 삭제한다.

### 질문
- 스택 2개로 큐를, 큐 2개로 스택을 만드는 방법과, 그 시간복잡도에 대해 설명해 주세요.
	- 스택 -> 큐
		- Stack A는 push만, Stack B는 pop만 수행한다.
		- enqueue : O(1)
			- Stack A에 push한다.
		- dequeue : O(n) / O(1)
			- 만약 B가 비어있다면 A의 모든 데이터를 pop해서 B에 push한다. -> O(n)
			- B가 비어있지 않다면 pop한다. -> O(1)
	- 큐 -> 스택
		- 큐를 번갈아가며 사용한다.
		- push : O(1)
			- 현재 사용중인 큐에 데이터를 삽입한다.
		- pop : O(n)
			- 1개 데이터가 남을 때까지 다른 큐에 dequeue, enqueue한다.
			- 마지막 데이터를 return 한다.

- 시간복잡도를 유지하면서, 배열로 스택과 큐를 구현할 수 있을까요?
	- 포인터 변수를 활용해서 구현할 수 있다. -> O(1)

- Prefix, Infix, Postfix 에 대해 설명하고, 이를 스택을 활용해서 계산하는 방법에 대해 설명해 주세요.
	- 연산자의 위치 차이
		- infix : 연산자를 중심으로 양쪽에 피연산자 배치 (a + b)
			- postfix로 변환한 후 계산한다.
				- 피연산자는 바로 출력한다.
				- 연산자의 경우
					- 우선순위가 높거나 같은 연산자들은 모두 pop해서 출력하고 push한다.
				- 괄호의 경우
					- '('는 stack에 push한다.
					- ')'는 여는 괄호가 나올때까지 pop한다.

		- prefix : 연산자를 앞에 배치 (+ a b)
			- 수식을 오른쪽에서 왼쪽으로 읽는다.
			- 피연산자가 나오면 스택에 push한다.
			- 연산자가 나오면 스택에서 2개의 피연산자를 pop하고 계산해서 스택에 push한다.

		- postfix : 연산자를 뒤에 배치 (a b +)
			- 수식을 왼쪽에서 오른쪽으로 읽는다.
			- 피연산자가 나오면 스택에 push한다.
			- 연산자가 나오면 스택에서 2개의 피연산자를 pop하고 계산해서 스택에 push한다.

- Deque는 어떻게 구현할 수 있을까요?
	- 배열과 포인터 변수로 구현할 수도 있다.
	- front, rear 2개의 포인터 변수와 모듈러 연산으로 원형 덱을 구현할 수 있다.