# chapter03 JSP로 시작하는 웹 프로그래밍 
**1. jsp과 html**  

- .html 실행 과정 설명 (eclipse)   
html은 정적인 문서(static document)이다.   
① 이클립스에서 작성중이던 프로젝트가 컴파일되어 톰캣 서버에서 실행될 수 있도록 배치(public) 된다.    
② 이클립스의 내부 창에서 웹 브라우저가 실행된다.  
③ 이 웹 브라우저는 이클립스 편집창에서 편집 중이던 파일에 대한   
서버 URL을 인터넷을 통해서 톰캣 서버에 요청한다. (http request)    
톰캣 서버가 웹 브라우저와 같은 컴퓨터에 있어도 이 둘은 인터넷을 통해서 통신한다.  
④ 톰캣 서버는 요청된 URL의 파일을 찾는다.  
⑤ 요청된 파일(html)이 정적인 문서이므로 톰캣 서버는 파일의 내용을   
그대로 웹 브라우저에게 인터넷을 통해서 전달한다. (http response)   
⑥ 파일의 내용을 전달받은 웹 브라우저는 그 내용을 웹 브라우저 창에 그린다.   
✓ 웹 브라우저는 웹 서버의 디스크에 저장된 html 파일의 내용을 알지 못한다.    
그저 웹 서버가 인터넷을 통해 보내온 내용을 받아서 웹 브라우저 창에 그린다.    
✓ 웹 브라우저가 웹 서버와 같은 컴퓨터에서 실행되지 않아도 상관없다.    
만약 웹 서버가 다른 컴퓨터에서 실행되고 있다면, URL에 서버의 IP주소가 들어가 있어야 한다.   
예) http://서버IP주소:8080/~

- .jsp 실행 과정 설명  
jsp 파일은 동적인 문서(dynamic document)이다.  
① 이클립스에서 작성 중이던 프로젝트가 컴파일되어 톰캣 서버에서 실행될 수 있도록 배치(public) 된다.    
② 이클립스의 내부 창에서 웹 브라우저가 실행된다.  
③ 이 웹 브라우저는 이클립스 편집창에서 편집 중이던 파일을 실행하기 위해서  
그 파일에 대한 URL을 인터넷을 통해 톰캣 웹 서버에 요청한다.    
④ 톰캣 웹 서버는 요청된 URL의 파일을 찾는다.   
⑤ 요청된 파일이 동적이므로 톰캣 웹 서버는 그 파일의 내용 중에서 java 코드에 해당하는 부분을 실행한다.  
⑥ 웹 서버는 확장자가 jsp인 파일의 내용을 다음과 같이 구분하여 웹 브라우저에 전달한다.   
✓ java 코드에 해당하지 않는 부분은 읽은 그대로 전달  
✓ java 코드에 해당하는 부분은 그 java 코드가 out 객체의 print 메소드를 호출하여    
출력한 내용만 웹 브라우저에게 전달한다. java 코드는 웹 브라우저에 전달하지 않는다.     
⑦ 파일의 내용을 전달받은 웹 브라우저는 그 내용을 웹 브라우저 창에 그린다.  

**2. jsp 페이지 구성**  
‑ 디렉티브 (Directive)  
‑ 스크립트 : 스크립트릿(Scriptlet), 표현식(Expression), 선언부(Declaration)  
‑ 표현 언어   
‑ 기본 객체 (Implicit object)  
‑ 정적인 데이터  
‑ 표준 액션 태그  
‑ 커스텀 태그와 표준 태그 라이브러리(JSTL)  

2.1 디렉티브 (Directive), jsp 선언 태그  
디렉티브는 jsp 페이지에 대한 설정 정보를 지정할 때 사용되며, 다음곽 같은 구문을 통해서 선언한다.   
```<% 디렉티브 이름 속성1 = "값1" 속성2 = "값2" ... %>```  
이 부분은 출력되지 않는다.

2.2 스크립트 요소   
① 스크립트릿(Scriptlet)    
스크립크릿은 jsp 페이지에서 자바 코드를 실행할 때 사용되는 코드 블록이다.   

```
<%
     자바 코드 1;
     자바 코드 2;
     ...
%>
```

② 표현식(Expression)   
표현식은 어떤 값을 출력 결과에 포함시키고자 할 때 사용된다.   

```<%= 값 %>```    

③ 선언부(Declaration)  
jsp 페이지의 스크립트릿이나 표현식에서 사용할 수 있는 메서드를 작성할 때 선언부를 사용한다.  

```
<%!
  public 리턴타입 메서드이름(파라미터 목록){
      자바코드...
      return 값;
  }
%>
```

2.3 기본 객체 (implicit object)   
jsp는 웹 어플리케이션 프로그래밍을 하는 데 필요한 기능을 제공해주는 '기본 객체'를 제공한다.  
request, response 등 다수의 기본 객체가 존재한다.  

2.4 표현 언어 
jsp의 스크립트 요소는 자바 문법 그대로 사용할 수 있는 장점이 있다.  
하지만, 스크립트 요소를 사용하면 다소 복잡해진다.  
표현 언어 사용 시 아래와 같이 간단하게 작성할 수 있다.  

```a * b = ${param.a * param.b}```

2.5 표준 액션 태그와 태그 라이브러리 - 생략  
  
  
*** 
  
  
# request 기본 객체 
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

# response 기본 객체
response 기본 객체는 request 기본 객체와 반대의 기능을 수행한다.  
request 기본 객체 : 웹 브라우저가 전송한 요청 정보   
response 기본 객체 : 웹 브라우저에 보내는 응답 정보  

## response 기본 객체가 응답 정보와 관련해 제공하는 기능  
- 헤더 정보 입력  
- 리다이렉트 하기    

1. 웹 브라우저에 헤더 정보 전송하기 - 생략  

2. 리다이렉트를 이용해서 페이지 이동하기  
response 기본 객체에서 많이 사용되는 기능 중 하나는 리다이렉트 기능이다.  
리다이렉트는 웹 서버가 웹 브라우저에게 다른 페이지로 이동하라고 응답하는 기능이다.  
입력폼#2.md 참고...  
  
**response 기본 객체는 다음의 메서드를 사용해서 웹 브라우저가 리다이렉트를 하도록 지시할 수 있다.**    
```response.sendRedirect(String location)```  

주로 다음과 같은 형태로 사용된다.  
```
<% page import = "java.sql.*" %>
...
<% 
     // JSP 페이지에서 필요한 코드를 실행한다.  
     ...
     response.sendRedirect("이동할 페이지");
 %>
```

**chap03/login.jsp 참고**  













