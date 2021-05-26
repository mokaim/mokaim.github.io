---
layout : post
title : 메이븐 웹 개발 강좌_02. Servlet과 web.xml
comments : true
---

> # Servlet 이란
>> ##### Servlet이란 기본적으로 Java 파일입니다. WAS에서 사용자의 Request 와 Response 를 Java 파일내에서 효과적으로 처리하기 위한 하나의 개념정도로 숙지하시면 될 것 같습니다.




![mavenWebCrreate_01](/imgs/mavenWebCreate_01/mavenWebCrreate_01.png)



#### 이전 강좌에서 만든 프로젝트에서 새로운 Servlet 파일을 만들겠습니다.
##### 위와같이 src/main/java 에서 우측마우스 클릭 후 New - Other 를 클릭해줍니다.



![mavenWebCrreate_02](/imgs/mavenWebCreate_01/mavenWebCrreate_02.png)



#### 자바 패키지와 클래스 이름을 입력
##### 위와같이 자신의 패키지명과 Servlet Class 파일의 이름을 적어줍니다.
##### SuperClass 는 HttpServlet 그대로 사용하시면 됩니다. 앞으로 배울 서블릿 핵심기능들이 HttpServlet에 의해 구현이 되기 때문이죠.



![mavenWebCrreate_03](/imgs/mavenWebCreate_01/mavenWebCrreate_03.png)


##### 위와같이 자신의 패키지명과 Servlet Class 파일의 이름을 적어줍니다.



![mavenWebCrreate_04](/imgs/mavenWebCreate_01/mavenWebCrreate_04.png)


##### 위와같이 기본적인 메소드로는 doPost와 doGet 메소드만 체크합니다.



![mavenWebCrreate_05](/imgs/mavenWebCreate_01/mavenWebCrreate_05.png)


##### 그럼 위와같은 화면이 나오실겁니다. 기본적으로 서블릿에는 생명주기가 있는데 doGet과 doPost 역시 그러한 생명주기의 일부분입니다. 생명주기에 관해서는 추후에 설명하도록 하겠습니다. 우선 지금은 가장중요한 doGet과 doPost가 생성이 되어있는 것을 확인하시면 됩니다.


![mavenWebCrreate_06](/imgs/mavenWebCreate_01/mavenWebCrreate_06.png)


#### 먼저 프로젝트를 실행하여 확인해봅시다.
>> * ##### 위와같이 프로젝트에서 우측마우스 클릭 후 Run As 에서 톰캣서버로 실행하여 줍시다.


![mavenWebCrreate_07](/imgs/mavenWebCreate_01/mavenWebCrreate_07.png)


##### 그렇게 되면 화면은 지금과 같이 페이지를 찾을수 없다고 나올 것입니다. 당연한 겁니다. 방금만든 서블릿에 해당하는 URI로 접속하지 못하였으니까요.
##### 주소창에 보시면 localhost:8080/mokaimSpring(자신의 프로젝트 명) 으로 되어있는데  localhost:8080/ 뒤에 오는 자신의 프로젝트명이 현 프로젝트의 Context Path(컨텍스트 경로)가 되는것입니다.
#### 컨텍스트 경로란 간단하게 말해서 서버의 관점에서 보는 현 프로젝트의 실행위치?! 정도로 생각하시면 될 것 같습니다.

![mavenWebCrreate_08](/imgs/mavenWebCreate_01/mavenWebCrreate_08.png)

##### web.xml 파일에서 서블릿에 매핑되는 uri를 지정해줍시다.

<div class="colorscripter-code" style="color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; position:relative !important;overflow:auto"><table class="colorscripter-code-table" style="margin:0;padding:0;border:none;background-color:#fafafa;border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px 0;text-align:left"><div style="margin:0;padding:0;color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important;line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#066de2">!DOCTYPE</span>&nbsp;<span style="color:#0a9989">web-app</span>&nbsp;<span style="color:#0a9989">PUBLIC</span></div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#0a9989"></span>&nbsp;<span style="color:#df5000">"-//Sun&nbsp;Microsystems,&nbsp;Inc.//DTD&nbsp;Web&nbsp;Application&nbsp;2.3//EN"</span><span style="color:#0a9989"></span></div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#0a9989"></span>&nbsp;<span style="color:#df5000">"http://java.sun.com/dtd/web-app_2_3.dtd"</span><span style="color:#0a9989"></span>&nbsp;<span style="color:#0a9989"></span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#066de2">web-app</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span>Archetype&nbsp;Created&nbsp;Web&nbsp;Application<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">description</span><span style="color:#010101">&gt;</span><span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">description</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-class</span><span style="color:#010101">&gt;</span>io.github.mokaim.MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-class</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-mapping</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">url-pattern</span><span style="color:#010101">&gt;</span>/MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">url-pattern</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-mapping</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">web-app</span><span style="color:#010101">&gt;</span></div></div><div style="text-align:right;margin-top:-13px;margin-right:5px;font-size:9px;font-style:italic"><a href="http://colorscripter.com/info#e" target="_blank" style="color:#e5e5e5text-decoration:none">Colored by Color Scripter</a></div></td><td style="vertical-align:bottom;padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none;color:white"><span style="font-size:9px;word-break:normal;background-color:#e5e5e5;color:white;border-radius:10px;padding:1px">cs</span></a></td></tr></table></div>


> * ##### 기본적인 코드는 이렇게 작성되어있을겁니다. url-pattern 에 적혀있는 것이 방금 만든 서블릿과 매핑되는 uri입니다.


![mavenWebCrreate_09](/imgs/mavenWebCreate_01/mavenWebCrreate_09.png)
##### url-pattern 에 적혀있는 uri를 서블릿컨텍스트 뒤에 적으시면 보시는 바와 같이 위의 서블릿에 접근한 것을 확인하실 수 있으실겁니다.
##### 하지만 일일히 MainServlet 이라는 uri를 입력하고 들어가야 하는 것이 귀찮으니 uri-pattern을 기본 '/' 로 바꾸어 놓겠습니다.

<div class="colorscripter-code" style="color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important; position:relative !important;overflow:auto"><table class="colorscripter-code-table" style="margin:0;padding:0;border:none;background-color:#fafafa;border-radius:4px;" cellspacing="0" cellpadding="0"><tr><td style="padding:6px 0;text-align:left"><div style="margin:0;padding:0;color:#010101;font-family:Consolas, 'Liberation Mono', Menlo, Courier, monospace !important;line-height:130%"><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#066de2">!DOCTYPE</span>&nbsp;<span style="color:#0a9989">web-app</span>&nbsp;<span style="color:#0a9989">PUBLIC</span></div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#0a9989"></span>&nbsp;<span style="color:#df5000">"-//Sun&nbsp;Microsystems,&nbsp;Inc.//DTD&nbsp;Web&nbsp;Application&nbsp;2.3//EN"</span><span style="color:#0a9989"></span></div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#0a9989"></span>&nbsp;<span style="color:#df5000">"http://java.sun.com/dtd/web-app_2_3.dtd"</span><span style="color:#0a9989"></span>&nbsp;<span style="color:#0a9989"></span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#066de2">web-app</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span>Archetype&nbsp;Created&nbsp;Web&nbsp;Application<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">display-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">description</span><span style="color:#010101">&gt;</span><span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">description</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-class</span><span style="color:#010101">&gt;</span>io.github.mokaim.MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-class</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-mapping</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span>MainServlet<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-name</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#066de2">url-pattern</span><span style="color:#010101">&gt;</span>/<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">url-pattern</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;<span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">servlet-mapping</span><span style="color:#010101">&gt;</span></div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%">&nbsp;</div><div style="padding:0 6px; white-space:pre; line-height:130%"><span style="color:#010101">&lt;</span><span style="color:#010101">/</span><span style="color:#066de2">web-app</span><span style="color:#010101">&gt;</span></div></div><div style="text-align:right;margin-top:-13px;margin-right:5px;font-size:9px;font-style:italic"><a href="http://colorscripter.com/info#e" target="_blank" style="color:#e5e5e5text-decoration:none">Colored by Color Scripter</a></div></td><td style="vertical-align:bottom;padding:0 2px 4px 0"><a href="http://colorscripter.com/info#e" target="_blank" style="text-decoration:none;color:white"><span style="font-size:9px;word-break:normal;background-color:#e5e5e5;color:white;border-radius:10px;padding:1px">cs</span></a></td></tr></table></div>

##### url-pattern 에서 MainServlet 부분을 지워주시고 url-pattern 태그사이에 '/'를 작성해주시면 되겠습니다.

![mavenWebCrreate_10](/imgs/mavenWebCreate_01/mavenWebCrreate_10.jpg)

> * ##### 그럼 정상적으로 서블릿 컨텐스트 까지만 입력하여도 MainServlet 에 접근한 걸 확인하실수 있으십니다.
