# web_xml의 개요, 기능, 활용
## Web.xml개요
#### web.xml이란?
  + Web Application의 Deployment Descriptor(환경파일 : 배포서술자, DD파일)로서 XML 형식의 파일
  + 모든 Web application은 반드시 하나의 web.xml 파일을 가져야 함
  + 위치 : WEB-INF 폴더 아래
  + web.xml 파일의 설정들은 Web Application 시작시 메모리에 로딩됨. (수정을 할 경우 web application을 재시작 해야함.)
  
#### Web.xml에 작성되는 내용
  + ServletContext의 초기 파라미터
  + Session의 유효시간 설정
  + Servlet/JSP에 대한 정의
  + Servlet/JSP 매핑
  + Mime type 매핑
  + Welcome File List
  + Error Pages 처리
  + 리스너/필터 설정
  + 보안

#### xml 작성시 주의점
  + 대소문자를 구분
  + attribute 값은 반드시 " " 또는 ' ' 으로 감싸야 한다.
  + 태그는 반드시 닫아야 한다. **content가 없는 태그의 경우 -> ex) <br/>
  + 
#### 서블릿 설정
  + servlet-name : 아래 servlet-mapping에 기술주기 위한 식별자
  + servlet-class : 실제 서블릿 클래스, 패키지까지 정확하게 기술
<XMP>
<servlet> : 서블릿 객체 설정

<servlet-name> : 객체의 이름    </servlet-name>

<servlet-class> : 객체를 생성할 클래스    </servlet-class>

</servlet>
</XMP>
  + servlet-name : 위에 servlet에 명시한 이름
  + url-pattern : 어떠한 URL경로로 접근할 수 있는지를 명시
<servlet-mapping>

<servlet-name> 이름 </servlet-name> 일할 서블릿 객체의 이름

<url-pattern>패턴</url-pattern> 클라이언트가 요청할 url 패턴

</servlet-mapping>

  + 기타요소
<!-- 세션 기간 설정 -->
    <session-config>
      <session-timeout>
        30
      </session-timeout>
    </session-config>

    <!-- mime 매핑 -->
    <mime-mapping>
      <extension>txt</extension>
      <mime-type>text/plain</mime-type>
    </mime-mapping>

    <!-- 시작페이지 설정 -->
    <welcome-file-list>
      <welcome-file>index.jsp</welcome-file>
      <welcome-file>index.html</welcome-file>
    </welcome-file-list>

    <!-- 존재하지 않는 페이지, 404에러시 처리 페이지 설정 -->
    <error-page>
      <error-code>404</error-code>
      <location>/error.jsp</location>
    </error-page>

    <!-- 태그 라이브러리 설정 -->
    <taglib>
      <taglib-uri>taglibs</taglib-uri>
      <taglib-location>/WEB-INF/taglibs-cache.tld</taglib-location>
    </taglib>

    <!-- resource 설정 -->
    <resource-ref>
      <res-ref-name>jdbc/jack1972</res-ref-name>
      <res-type>javax.sql.DataSource</res-type>
      <res-auth>Container</res-auth>
    </resource-ref>














