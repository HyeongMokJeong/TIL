
1. DispatcherServlet이 요청을 받는다.
2. DispathcerServlet은 HandlerMapping으로부터 주어진 요청을 처리할 수 있는 Handler 객체를 가져온다.
3. Handler를 실행시킬 수 있는 HandlerAdapter 객체를 가져온다.
	1. Handler 객체에 인터셉터가 존재한다면 인터셉터의 preHandle 메서드 호출
4. HandlerAdapter 객체를 통해 