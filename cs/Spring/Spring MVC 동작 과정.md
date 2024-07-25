
1. DispatcherServlet이 요청을 받는다.
2. DispathcerServlet은 HandlerMapping으로부터 주어진 요청을 처리할 수 있는 Handler 객체를 가져온다.
3. Handler를 실행시킬 수 있는 HandlerAdapter 객체를 가져온다.
	1. Handler 객체에 인터셉터가 존재한다면 인터셉터의 preHandle 메서드 호출
4. HandlerAdapter 객체를 통해 Controller 메서드 실행 후, ModelAndView 객체를 받는다.
	1. Handler 객체에 인터셉터가 존재한다면 postHandle 메서드 호출
5. DispathcerServlet은 ModelAndView를 통해 view name을 얻고, ViewResolver에게 전달하여 응답에 필요한 View 객체를 얻어온다.
6. DispathcerServlet은 받아온 View 객체에, ModelAndView의 Model을 전달하여 render 메서드를 호출, 페이지 렌더링을 수행한다.
7. DispathcerServlet이 렌더링된 페이지를 response로 사용자에게 응답한다.