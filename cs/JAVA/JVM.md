Java는 자바 가상 머신(JVM) 덕분에 OS 독립적인 특징을 가진다.

- 컴파일 과정
1. 자바 소스 코드를 작성한다.
2. 자바 컴파일러가 바이트 코드(클래스 파일)로 컴파일한다.
3. 컴파일된 바이트 코드를 JVM의 클래스 로더에 전달한다.
4. 클래스 로더는 동적으로 필요한 클래스들을 JVM 메모리에 적재한다. (Runtime Data area)
	1. 클래스 파일을 가져온다.
	2. 자바와 JVM 명세에 맞게 작성되었는지 검증한다.
	3. 클래스가 필요로 하는 메모리 공간을 할당한다.
	4. 클래스의 모든 심볼릭 레퍼런스를 다이렉트 레퍼런스로 변경한다.
	5. 클래스 변수들을 초기화한다.
5. 실행 엔진은 JVM 메모리에 적재된 바이트 코드를 명령어 단위로 한 줄씩 가져와서 실행한다.
	- 실행 엔진 구성
		1. 인터프리터
		2. JIT 컴파일러
		3. 가비지 콜렉터

- Runtime Data area
	- 모든 스레드 공유 - GC 대상
		1. Method 영역 : static 변수 등
		2. Heap 영역
	- 스레드 별 사용
		1. Stack 영역
		2. PC Register
		3. Native Method Stack 영역