서블릿 컨테이너 동작 방식 설명


내장 톰캣 서버 생성


![image](https://user-images.githubusercontent.com/90680271/154494773-6ec77d18-eca9-4ae9-9921-873718652836.png)

![image](https://user-images.githubusercontent.com/90680271/154494846-159d953d-f0c5-4250-9bf5-e3651e29a026.png)



HTTP 요청 데이터 - 개요


GET - 쿼리 파라미터
/url?username=hello&age=20
메시지 바디 없이, URL의 쿼리 파라미터에 데이터를 포함해서 전달
예) 검색, 필터, 페이징등에서 많이 사용하는 방식

POST - HTML Form
content-type: application/x-www-form-urlencoded
메시지 바디에 쿼리 파리미터 형식으로 전달 username=hello&age=20
예) 회원 가입, 상품 주문, HTML Form 사용


HTTP message body에 데이터를 직접 담아서 요청
HTTP API에서 주로 사용, JSON, XML, TEXT
데이터 형식은 주로 JSON 사용
POST, PUT, PATCH


POST- HTML Form

![image](https://user-images.githubusercontent.com/90680271/154495616-2c452f4d-1312-4fcc-96ff-01768e7002f7.png)




서블릿과 JSP의 한계


서블릿으로 개발할 때는 뷰(View)화면을 위한 HTML을 만드는 작업이 자바 코드에 섞여서 지저분하고 복잡했다.

JSP를 사용한 덕분에 뷰를 생성하는 HTML 작업을 깔끔하게 가져가고, 중간중간 동적으로 변경이 필요한

부분에만 자바 코드를 적용했다. 그런데 이렇게 해도 해결되지 않는 몇가지 고민이 남는다.

회원 저장 JSP를 보자. 코드의 상위 절반은 회원을 저장하기 위한 비즈니스 로직이고, 나머지 하위 절반만

결과를 HTML로 보여주기 위한 뷰 영역이다. 회원 목록의 경우에도 마찬가지다.

