---
layout: post
title: 메이븐 웹 개발 강좌_01. 기본 메이븐 웹 프로젝트 생성
comments : true
---

> # 메이븐 기본 프로젝트 생성

    웹 프로젝트의 빌드툴에는 딱히 정해진 개념이 없습니다.
    기본적인 빌드툴에는 메이븐과 그레이들 이라는 빌드툴이 있고 각자 사용하고 싶으신 빌드툴을
    선택하시면 됩니다.

    저는 빌드툴로 메이븐을 쓸거라 메이븐 프로젝트를 생성하겠습니다.

    메이븐에 대해서 아직 잘 모르신다면 메이븐에 관한 강좌를 보고 오시는 것을 추천드립니다.



![springProjectMavenCreate_01](/assets/springProjectMavenCreate_01.png)

> # 이클립스를 실행하여 새 프로젝트를 생성한다.

    이클립스를 실행하여 새 프로젝트를 생성합니다.
    저희는 메이븐 프로젝트로 생성하도록 하겠습니다.
    탐색기 창에서 우측 마우스 버튼을 클릭하여 New = other 로 들어갑니다.




![springProjectMavenCreate_02](/assets/springProjectMavenCreate_02.png)



    처음에 other 프로젝트 생성을 클릭하면 위와같은 화면이 뜹니다.




![springProjectMavenCreate_03](/assets/springProjectMavenCreate_03.png)


    그렇다면 Maven 폴더를 찾아 다음과 같이 Maven Project 를 클릭해줍시다.


![springProjectMavenCreate_04](/assets/springProjectMavenCreate_04.png)


    work directory 는 default 로 설정해주시면 됩니다.


![springProjectMavenCreate_05](/assets/springProjectMavenCreate_05.png)



    위 화면은 메이븐 프로젝트를 생성할 때 어떤 Templete를 쓰겠느냐고 묻는 겁니다.
    저희는 메이븐 웹 프로젝트로 공부를 할 것이기에 기본 웹 프로젝트 템플릿을 선택해주시면 됩니다.
    GroupID : org.apache.maven.archetypes
    ArtifactId : maven-achetype-webapp



__우선 간단히 말하자면 ArtifactId 하나하나의 단위 모듈이고 GroupID 는 하나하나의 Artifact 들이__
__모여있는 그룹집단의 ID입니다. Next를 눌러줍시다.__


    스프링을 예로들자면 SpringContext 모듈이나 Spring JDBC 는 하나의 Artifact 모듈들이고
    그러한 모듈들을 모아놓은 그룹이 SpringFramework 가 있겠습니다.




![springProjectMavenCreate_06](/assets/springProjectMavenCreate_06.png)



    똑같이 GroupId 는 자신의 하나하나의 프로젝트인 Artifact들을 그룹단위로 구별할 아이디를
    지정해줍시다. 예를들어 자신의 블로그 주소라던가 사이트 주소라던가..
    ArtifactId 는 자신의 프로젝트 명을 적어줍시다.
    그렇게 해서 Finish 를 눌러줍시다.

    제가 mokaimSpring 이라고 프로젝트 이름을 적은건 추후에 해당 프로젝트로
    스프링 프로젝트도 작성해볼것이기에 미리 이름을 지어놓은 것입니다.



![springProjectMavenCreate_07](/assets/springProjectMavenCreate_07.png)



    그렇게되면 위와같은 기본적인 메이븐 프로젝트 폴더구조가 잠시동안 만들어지겠는데요.
    조금만 기다리시면 됩니다. 왜냐하면 저희는 아까 ArtifactId : maven-achetype-webapp 이라는
    템플릿을 선택하였기에  이클립스에서 해당 템플릿을 불러오기까지 몇 초의 시간이 걸리기 때문입니다.



![springProjectMavenCreate_08](/assets/springProjectMavenCreate_08.png)



    몇 초간의 시간이 지나게 되면 위와같은 폴더 구조가 만들어지게 되는데요.
    아까 설정해두었던 ArtifactId : maven-achetype-webapp 의 템플릿 구조입니다.

__하지만 어딘가의 설정이 잘못되었는지 빨간색 액티브 표시로 프로젝트를 사용할 수 없다는 표시가 뜹니다.__

    이유는 웹 프로젝트에 필요한 기본적인 Servlet 라이브러리를 불러오지 못하여 생기는 표시입니다.




![springProjectMavenCreate_09](/assets/springProjectMavenCreate_09.png)



> # 서블릿 라이브러리를 불러옵시다

    프로젝트에서 우측 마우스버튼 -> Build Path -> Configuration Build Path 를 선택합시다.


![springProjectMavenCreate_10](/assets/springProjectMavenCreate_10.png)


    그런 다음 해당 항목에서 Add Libary를 클릭하시면 됩니다.


![springProjectMavenCreate_11](/assets/springProjectMavenCreate_11.png)



    어떤 종류의 라이브러리를 불러올 것이냐는 창이 뜨면 Servlet 라이브러리가
    포함되있는 Tomcat 서버를 통하여 Servlet 라이브러리를 가져올 것이기에
    Server Runtime 을 선택하여줍시다.

#### 아직까지 Servlet과 톰캣이 무엇인지 모르시는 분이 계시다면 JSP 서블릿 강좌를 먼저 보고 오시기 바랍니다.



![springProjectMavenCreate_12](/assets/springProjectMavenCreate_12.png)




    Apache Tomcat 을 선택하고 Finish




![springProjectMavenCreate_13](/assets/springProjectMavenCreate_13.png)



    그리고 마지막 Apply and Close 를 클릭하시게 되면 정상적으로 기본 프로젝트 설정은 모두
    끝나게 되었습니다.




![springProjectMavenCreate_14](/assets/springProjectMavenCreate_14.png)




> ## 모든 개발 준비를 마치게 되었습니다.
    메이븐 웹 프로젝트라고 해봐야 기존의 Dynamic Web Project 의 구조에서 pom.xml 파일과
    배포(deploy)를 위한 target 폴더가 추가 된 것 이외에는 차이가 크게 업습니다.
