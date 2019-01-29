# chapter04 request 기본 객체 
웹브라우저에 웹 사이트의 주소를 입력하면, 웹브라우저는 해당 웹 서버에 연결한 후 요청 정보를 전송하는데 
이 요청정보를 제공하는 것이 request 기본 객체이다.   

**기능**  
- 클라이언트(웹 브라우저)와 관련된 정보 읽기 기능 
- 서버와 관련된 정보 읽기 기능 
- 클라이언트가 전송한 요청 파라미터 읽기 기능
- 클라이언트가 전송한 요청 헤더 읽기 기능 
- 클라이언트가 전송한 쿠키 읽기 기능 
- 속성 처리 기능 

### 1. 클라이언트 정보 및 서버 정보 읽기  
string getRemoteAddr() : 웹 서버에 연결한 클라이언트의 IP 주소를 구한다.  
long getContentLength() : 클라이언트가 전송한 요청 정보의 길이를 구한다. (알수없는 경우 -1을 리턴)  
string getCharacterEncoding() : 클라이언트가 요청 정보를 전송할 때 사용한 캐릭터의 인코딩을 구한다.  
string getContentType() : 클라이언트가 요청 정보를 전송할 때 사용한 컨텐츠의 타입을 구한다.  
string getProtocol() : 클라이언트가 요청한 프로토콜을 구한다.  
string getMethod() : 웹 브라우저가 정보를 전송할 때 사용한 방식을 구한다.  
string getRequestURI() : 웹 브라우저가 요청한 URL에서 경로를 구한다.  
string getContextPath() : JSP 페이지가 속한 웹 어플리케이션의 컨텍스트 경로를 구한다.  
string getServerName() : 연결할 때 사용한 서버 이름을 구한다.  
int getServerPort() : 서버가 실행중인 포트 번호를 구한다.  
 > lecture1/WebContent/chap03/requestInfo.jsp 참고
