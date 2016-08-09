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
<br><br>
<XMP>
<servlet> : 서블릿 객체 설정<br><br>

<servlet-name> : 객체의 이름    </servlet-name><br><br>

<servlet-class> : 객체를 생성할 클래스    </servlet-class><br><br>

</servlet><br><br>
</XMP><br><br>
  + servlet-name : 위에 servlet에 명시한 이름
  + url-pattern : 어떠한 URL경로로 접근할 수 있는지를 명시
<br><br>
<XMP>
<servlet-mapping><br><br>

<servlet-name> 이름 </servlet-name> 일할 서블릿 객체의 이름<br><br>

<url-pattern>패턴</url-pattern> 클라이언트가 요청할 url 패턴<br><br>

</servlet-mapping>
</XMP><br><br>
  + 기타요소
<br><br>
<XMP>
<!-- 세션 기간 설정 --><br>
    <session-config><br>
      <session-timeout><br>
        30<br>
      </session-timeout><br>
    </session-config><br><br>

    <!-- mime 매핑 --><br>
    <mime-mapping><br
      <extension>txt</extension><br>
      <mime-type>text/plain</mime-type><br>
    </mime-mapping><br><br>

    <!-- 시작페이지 설정 --><br>
    <welcome-file-list><br>
      <welcome-file>index.jsp</welcome-file><br>
      <welcome-file>index.html</welcome-file><br>
    </welcome-file-list><br><br>

    <!-- 존재하지 않는 페이지, 404에러시 처리 페이지 설정 --><br>
    <error-page><br>
      <error-code>404</error-code><br>
      <location>/error.jsp</location><br>
    </error-page><br><br>

    <!-- 태그 라이브러리 설정 --><br>
    <taglib><br>
      <taglib-uri>taglibs</taglib-uri><br>
      <taglib-location>/WEB-INF/taglibs-cache.tld</taglib-location><br>
    </taglib><br><br>

    <!-- resource 설정 --><br>
    <resource-ref><br>
      <res-ref-name>jdbc/jack1972</res-ref-name><br>
      <res-type>javax.sql.DataSource</res-type><br>
      <res-auth>Container</res-auth><br>
    </resource-ref><br><br>

</XMP><br><br>












