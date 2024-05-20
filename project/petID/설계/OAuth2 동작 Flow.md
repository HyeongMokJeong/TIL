1. url 요청 
   http://localhost:8080/oauth2/authorization/google
   http://localhost:8080/oauth2/authorization/kakao
   http://localhost:8080/oauth2/authorization/naver
   http://localhost:8080/oauth2/authorization/apple (추후 구현)
   ![](스크린샷%202024-05-20%20오후%2010.20.44.png)

2. 소셜 로그인

3. 로그인 이후 Query param으로 Access token, Refresh token 전달해서 redirect
![](스크린샷%202024-05-20%20오후%2010.21.58.png)