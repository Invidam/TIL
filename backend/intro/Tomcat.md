# Tomcat

## Tomcat이란?

- **자바 서블릿, JSP**의 구현이며,  Java EE 플랫폼의 일부.
    - Tomcat 10 이후 JavaEE가 아닌 Jakarta EE(Java EE의 새로운 명칭) 의 일부를 구현
- 일반적으로 **WAS**에 속한다.
    - 정확히는 JavaEE의 모든 스펙을 지원하지 않고 일부만 지원하여  WAS가 아니지만 Servlet, JSP를 지원하기에 WAS라고 부른다.

## Web Server와 WAS

- 둘 다 서버의 일종이다.
    - 서버는 클라이언트 요청에 대해 응답을 하는 역할을 한다.
- Web Server는 정적 컨텐츠를 주로 처리한다.
- WAS는 동적 컨텐츠를 주로 처리한다.

### Web WAS 분리하는 이유

- Web Server도 동적 컨텐츠의 처리가 가능하며, WAS도 정적 컨텐츠의 처리가 가능하다.
    - 하지만, 분리함으로써 얻을 수 있는 이점이 있어 분리하여 사용한다.
1. WAS의 성능 유지
    1. 정적 컨텐츠는 Web Server가 처리함.
    2. WAS가 정적 컨텐츠를 처리하지 않아, 속도 ↓ X
2. 여러 대의 WAS 사용 가능
    1. 로드밸런싱 가능
    2. 서버 무중단 가능
3. 리소스 관리 효율적 
    1. 동적 리소스 사용 ↑ → WAS 증축
    2. 정적 리소스 사용 ↑ → Web Server 증축

## Tomcat 구성요소

- Catalina
    - 서블릿 컨테이너의 구현.
    - 설정 파일들
        - `catalina.policy`
        - `[catalina.properties](http://catalina.properties)`
        - `[logging.properties](http://logging.properties)`
        - `content.xml`
        - `server.xml`
        - `tomcat-users.xml`
        - `web.xml`
- Coyate
    - 웹 서버의 역할을 한다.
    - 요청을 수신하여 Tomcat 엔진에게 처리를 맡기고, 그 결과를 클라이언트에 반환한다.
- Jasper
    
    톰캣의 JSP 엔진이다.
    
    - JSP 파일을 컴파일하여 서블릿 코드로 컴파일한다.

- 참고
    - [https://tomcat.apache.org/](https://tomcat.apache.org/)
    - [https://www.samsungsds.com/kr/insights/java_jakarta.html](https://www.samsungsds.com/kr/insights/java_jakarta.html)
    - [https://okky.kr/article/293917](https://okky.kr/article/293917)
    - [https://coding-factory.tistory.com/741](https://coding-factory.tistory.com/741)
    - [https://en.wikipedia.org/wiki/Apache_Tomcat](https://en.wikipedia.org/wiki/Apache_Tomcat#Jasper)
    - [https://www.mulesoft.com/tcat/tomcat-catalina](https://www.mulesoft.com/tcat/tomcat-catalina)
    
