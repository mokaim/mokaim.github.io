---
layout : post
title : AzureSQL JDBC
comments : true
---


전편에서 강의를 이어서 하도록 하겠습니다.

https://mokaim.github.io/2020-07-06-AzureSQL_Create/  

전편의 AzureSQL 만들기 강좌를 참조해주세요.

![AzureJDBC_01.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_01.png)

만들어 두었던 샘플 DB의 테이블 목록을 열어보시면 샘플DB에서 만들어두었던

여러가지 테이블을 보실 수 있겠습니다.

그 중에서 저희가 사용할 TEST Table 을 생성하여 봅시다.

![AzureJDBC_02.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_02.png)

위와 같이 테이블 이름은 test로 해주시고 Column 은 간단하게 id 와 name을 적어줍니다.

<script src="https://gist.github.com/mokaim/bb3b40510d2a2c9be01ce9aa6ad4f1f6.js"></script>



![AzureJDBC_03.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_03.png)


그리고 JDBC 연결을 위한 URL을 얻기위해 연결문자열을 클릭해주셔서 JDBC 탭을

눌러줍니다.

그리고 길게 나열되어 있는 URL을 전부 복사하여 줍니다.


![AzureJDBC_04.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_04.png)

그리고 이클립스에서 메이븐 프로젝트를 생성합니다.

![AzureJDBC_05.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_05.png)

워크스페이스를 디폴트로 잡아줍니다.


![AzureJDBC_06.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_06.png)

그리고 메이븐 quickstart 템플릿으로 프로젝트를 생성해줍니다.

![AzureJDBC_07.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_07.png)

Finish를 눌러줍니다.

![AzureJDBC_08.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_08.png)

그리고 프로젝트가 생성된 후 pom.xml 파일을 열어줍니다.

그러면 기본적인 설정값이 적혀져있을겁니다.



![AzureJDBC_09.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_09.png)


MS SqlServer jdbc 드라이버 의존성 코드를
Dependencis 태그안에 새로운 의존성을 추가해줍니다.


그리고 quickstart 템플릿의 자바버젼은 1.5 version으로 맞추어져 있을텐데

1.8버젼으로 맞추어주기위해 위의 properties 안에 compile 설정도 잡아줍니다.


![AzureJDBC_10.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_10.png)

그리고 좌측의 프로젝트 이름을 우측 마우스 클릭 -> Maven Update를 눌러줍니다.

그러면 pom.xml에 명시된 대로 저희의 메이븐 프로젝트가 업데이트 될 겁니다.

![AzureJDBC_11.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_11.png)
![AzureJDBC_12.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_12.png)


그러면 위와같이 mssql-jdbc가 성공적으로 추가되었고 Java 버젼도 1.5에서
1.8 버젼으로 바뀌는 것을 보실 수 있겠습니다.

![AzureJDBC_13.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_13.png)

그리고 프로젝트의 App.java를 클릭해주시고 main 메소드 안의 내용을 위와 같이 적어줍니다.

## 그리고 아까 복사하였던 연결문자열을 url 변수안에 넣어주세요.
### 그리고 password 부분을 자신의 SQL Server 관리자 비밀번호를 입력해주세요.


참고 : https://www.microfocus.com/documentation/enterprise-developer/ed232/Eclipse/GUID-B08BD2EA-EC2A-447D-B3D6-ABF277BAD3B1.html


<script src="https://gist.github.com/mokaim/355602a31b01cafa31bc8620d0e64bf6.js"></script>


그리고 위 사진에 빨간색으로 표시되어있는 부분에 전 강좌에서 설정해두었던

SQL Server 관리자 비밀번호를 입력해줍니다.


![createAzure_06.png](/assets/AzureSQL_Create/createAzure_06.png)


https://mokaim.github.io/2020-07-06-AzureSQL_Create/  
이 때 설정해주셨던 비밀번호를 입력해주시면 되겠습니다.


![AzureJDBC_14.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_14.png)

그리고 실행을 눌러주신다면 콘솔창에 다음과 같은 내용을 확인하실 수 있겠습니다.

![AzureJDBC_15.png](/assets/AzureSQL_JDBC_Connect_01/AzureJDBC_15.png)


그리고 다시 AzureSQL 쿼리편집기에서 다음과 같이 SELECT 시키게 된다면

JAVA 코드에서 넣었던 1과 'test' 라는 두 개의 데이터가 JDBC쿼리를 통해

성공적으로 저장된 걸 보실 수 있겠습니다.

이것으로 이번 강좌를 마치겠습니다.


Sample 코드는 밑의 링크를 참조해 주시면 되겠습니다.

https://github.com/mokaim/azureSQL-JDBC
