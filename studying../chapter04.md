# chapter04 request 기본 객체 
웹브라우저에 웹 사이트의 주소를 입력하면, 웹브라우저는 해당 웹 서버에 연결한 후 요청 정보를 전송하는데   
이 요청정보를 제공하는 것이 request 기본 객체이다.   

## 기능  
- 클라이언트(웹 브라우저)와 관련된 정보 읽기 기능 
- 서버와 관련된 정보 읽기 기능 
- 클라이언트가 전송한 요청 파라미터 읽기 기능
- 클라이언트가 전송한 요청 헤더 읽기 기능 
- 클라이언트가 전송한 쿠키 읽기 기능 
- 속성 처리 기능 

___

### 1. 클라이언트 정보 및 서버 정보 읽기  
String getRemoteAddr() : 웹 서버에 연결한 클라이언트의 IP 주소를 구한다.  
long getContentLength() : 클라이언트가 전송한 요청 정보의 길이를 구한다. (알수없는 경우 -1을 리턴)  
String getCharacterEncoding() : 클라이언트가 요청 정보를 전송할 때 사용한 캐릭터의 인코딩을 구한다.  
String getContentType() : 클라이언트가 요청 정보를 전송할 때 사용한 컨텐츠의 타입을 구한다.  
String getProtocol() : 클라이언트가 요청한 프로토콜을 구한다.  
String getMethod() : 웹 브라우저가 정보를 전송할 때 사용한 방식을 구한다.  
String getRequestURI() : 웹 브라우저가 요청한 URL에서 경로를 구한다.  
String getContextPath() : JSP 페이지가 속한 웹 어플리케이션의 컨텍스트 경로를 구한다.  
String getServerName() : 연결할 때 사용한 서버 이름을 구한다.  
int getServerPort() : 서버가 실행중인 포트 번호를 구한다.  
 > lecture1/WebContent/chap03/requestInfo.jsp 참고  
 
 ### 2. 요청 파라미터 처리  
 ① HTML 폼과 요청 파라미터   
 HTML 폼의 각 입력 요소는 이름을 갖는다.  
 아래의 코드를 보면, text1 입력을 위한 input태그의 name속성은 "param1"이고    
 text2 입력을 위한 input태그의 name속성은 "param2"이다.   
   
 <img width="648" alt="2019-01-30 10 16 26" src="https://user-images.githubusercontent.com/33855307/51984593-1af3c100-24df-11e9-940f-a660878b18d2.png">  
   
입력 요소의 이름은 웹브라우저가 서버에 전송하는 요청 파라미터의 이름으로 사용된다.    
    
<img width="1359" alt="2019-01-30 10 29 32" src="https://user-images.githubusercontent.com/33855307/51984871-c7ce3e00-24df-11e9-8ee8-ca9e99b3fa5b.png">  
  
② request 기본 객체의 요청 파라미터 관련 메소드  
String getParameter(String name) : 이름이 name인 파라미터의 값을 구한다. 존재하지 않을 경우 null 리턴  
String[] getParameterValues(String name) : 이름이 name인 모든 파라미터의 값을 배열로 구한다. 존재하지 않을 경우 null 리턴  
java.util.Enumeration getParameterNames() : 웹 브라우저가 전송한 파라미터의 이름 목록을 구한다.  
java.util.Map getParameterMap() : 웹 브라우저가 전송한 파라미터의 맵을 구한다. 맵은 <파라미터 이름, 값> 쌍으로 구성된다.   

③ 요청 파라미터 인코딩    
웹 브라우저는 웹 서버에 파라미터를 전송할 때 알맞은 캐릭터 셋을 이용해서 파라미터 값을 제공한다.  
반대로 웹 서버는 알맞은 캐릭터 셋을 이용해서 웹 브라우저가 전송한 파라미터 데이터를 디코딩한다.  
입력 폼이 전송될 때, url encoding과 url decoding은 이렇게 웹 브라우저와 웹 서버에 의해 자동으로 처리된다.  
