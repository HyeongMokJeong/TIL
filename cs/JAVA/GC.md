
- 자바의 메모리 관리 기법 중 하나
- Heap 영역에서 동적으로 할당된 메모리 중 사용되지 않는 부분을 자동으로 할당 해제하여 공간을 확보한다.
- 참조 상태를 기준으로 삭제 여부를 결정한다.
	- Mark and Sweep
		- Mark : Root Space(Heap 영역을 참조하는 Method area, Stack area 등)로부터 그래프 탐색으로 참조되는 Heap 영역의 객체들 Mark
		- Sweep : 참조되지 않는 객체들을 제거

- Heap 메모리 구조
	- Young : 새롭게 생성된 객체가 할당되는 영역 / minor GC
		- Eden
		- Survival 0
		- Survival 1
		- 특징
			- 물리적인 공간이 작기 때문에 minor GC가 발생해도 상대적으로 적은 시간이 걸린다.
	- Old : Young 영역에서 살아남은 객체들이 할당되는 영역 / major GC, full GC 
		- Major GC가 발생하면 모든 스레드가 멈추는 Stop-The-World 문제 발생